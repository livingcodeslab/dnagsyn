# primer design

Goal: multi-purpose oligo that will get synthesized with various end chemistries for integration into the GFET microfluidic platform.

Basic idea is to have several overlapping Cas9-targetable sites with nested restriction sites.
This lets us cut the DNA in a lot of places.
Release from the surface is done with an internal **HindIII** cut on a deliberately duplexed substrate (see *Release strategy* below).
The Type IIS sites (FokI, Esp3I/BsmBI, Eco31I/BsaI) are retained for nested cuts made *in solution* on the released, re-duplexed product, not for the on-chip release step.

```txt
5' GATTACACAGGCAAGCTTAGGATGTAGGTCTTAACTCGTCTCTGGTCTCA 3'
   |-----| |-| |----| |---| |-| |----| |----| |----|
   GATTACA NGG AAGCTT GGATG NGG CTTAAC CGTCTC GGTCTC #<-- cuts after end of oligo 
           PAM Hind3  FokI  PAM spacer Esp3I  Eco31I
              |---20bp Guide 1---|
                               |---20bp Guide 2---|
```

I manually filled in the gaps to balance sequence composition and avoid any △G-favorable folds.
The spacer is a near match for EcoRI (CTTAAG), but I couldn't get a positive Gibbs free energy fold without modifying it.

Note the spacer is *only* a near match: there is no `GAATTC` in this molecule, so EcoRI cannot be used for release (see below).

## Release strategy: duplex + internal HindIII

The molecule is single-stranded both when tethered to the graphene and during TdT extension, because TdT needs a single-stranded 3'-OH to extend.
So the release cut has to be made by an enzyme that we make duplex on demand at the release step only.

`AAGCTT` sits at nt 13–18 (single occurrence in the molecule) and is cut `A^AGCTT`, leaving a 4 nt 5'-AGCT overhang.
The cut is internal, so the released molecule is nt 14–50 (**37 nt**) plus whatever TdT appended.
That gives a clean internal length standard: 37 nt when synthesis is blocked, 37+n nt when synthesis proceeds.

Complement for the release step:

```txt
template 5'-GATTACACAGGCAAGCTTAGGATGTAGGTCTTAACTCGTCTCTGGTCTCA-3'
                       |||||||||||||||||||||
comp     3'-GACCTACATCCTAAGCTTGCCTG-5'    23 nt, anneals to nt 8-30, Tm ~57 C
         5'-GACCTACATCCTAAGCTTGCCTG-3'    5' fluorophore -> CE readout + release control
```

That leaves 5 bp of flanking duplex upstream of the site and 12 bp downstream; a bare 6 bp duplex will not hold a dimeric enzyme with a ~20 bp footprint.
If the complement is pre-annealed *before* TdT extension (rather than at the release step), its own 3' end must be blocked (3'-ddC / 3'-phosphate / inverted dT), because a free 3' end is itself a TdT substrate.
Labeling the complement rather than the template is deliberate: the released product inherits the fluorophore, and the signal recovered in the wash is a release-efficiency control, which matters because a failed cut and a blocked synthesis look identical in the CE trace otherwise.

## Single-strand activity of these sites

REBASE ssDNA activity (`rebase.neb.com/cgi-bin/hybcombolist`), under canonical enzyme names:

| Site | Motif | Position | Cleavage | ssDNA activity |
|---|---|---|---|---|
| HindIII | `AAGCTT` | 13–18 | `A^AGCTT` (Type IIP) | **no** — must be duplexed |
| FokI | `GGATG` | 20–24 | 9/13 | no (BstF5I, its isoschizomer) |
| Esp3I (BsmBI) | `CGTCTC` | 37–42 | 1/5 | no/partial |
| Eco31I (BsaI) | `GGTCTC` | 44–49 | 1/5 | **no** |

The Type IIS enzymes are wrong for an ssDNA substrate for a structural reason, not only an empirical one: the ssDNA cleavage that Type II enzymes do show proceeds through transiently formed duplex "canonical structures" built from two inverted copies of a **palindromic** site (Nishigaki 1985, *NAR* 13:5747).
These Type IIS sites are non-palindromic by construction, so they cannot form such structures, and their recognition itself requires the complementary strand.
FokI additionally requires a duplex recognition site plus recruitment of a second monomer to cut (Halford 2011, *Biochem Soc Trans* 39:584; Waugh & Sauer 1993, *PNAS* 90:9596).

Two positioning problems to fix before the Type IIS sites are used on a released, duplexed molecule in solution:

- Eco31I/BsaI is `(1/5)^` but `GGTCTC` has only **1 nt** downstream at the 3' end of the oligo, so it can only nick the top strand there. A full cut needs 5 nt downstream: ligate an adaptor or redesign.
- The Esp3I `(1/5)^` top-strand cut lands at nt 44, the first base of the `GGTCTC` site, so the two Type IIS sites are not independent cut positions.

Validation is still required in practice: REBASE values are defined-oligo data, and a 50-mer tethered to a surface is a much worse substrate than a free oligo.

```bash
s=GATTACACAGGCAAGCTTAGGATGTAGGTCTTAACTCGTCTCTGGTCTCA; echo $s; echo $s | RNAfold -P DNA; echo $s | awk '{print "A:", gsub(/A/,"A"), "T:", gsub(/T/,"T"), "G:", gsub(/G/,"G"), "C:", gsub(/C/,"C"), "N:", gsub(/N/,"N")}' 
GATTACACAGGCAAGCTTAGGATGTAGGTCTTAACTCGTCTCTGGTCTCA
WARNING: stacking enthalpies not symmetric
WARNING: stacking enthalpies not symmetric
WARNING: stacking enthalpies not symmetric
WARNING: stacking enthalpies not symmetric
GAUUACACAGGCAAGCUUAGGAUGUAGGUCUUAACUCGUCUCUGGUCUCA
.................................................. (  0.00)
A: 12 T: 15 G: 12 C: 11 N: 0
```

I then put this through unafold web DNA folding. The strongest fold has Tm = 35.7 °C.

We can get the reverse complement with this one cool trick:

```bash
echo GATTACACAGGCAAGCTTAGGATGTAGGTCTTAACTCGTCTCTGGTCTCA | rev | tr 'ATCG' 'TAGC'
TGAGACCAGAGACGAGTTAAGACCTACATCCTAAGCTTGCCTGTGTAATC
```

It's also free of any secondary structures:

```
TGAGACCAGAGACGAGTTAAGACCTACATCCTAAGCTTGCCTGTGTAATC
.................................................. (  0.00)
A: 15 T: 12 G: 11 C: 12 N: 0
```

