# Two interface questions behind the hybridization protocol

**Date:** 2026-11-12
**Status:** notes and literature check — not a bench procedure, nothing here has been measured on our chips.
**Scope:** two questions that decide how the [fluor-tgtaatc hybridization](../protocols/2026-11-11-fluor-tgtaatc-hybridization.md) is run and how its result is read:

1. **Quenching** — is the fluorescein on the incoming complement quenched by the **PBASE carpet**, or only by the **graphene** underneath it?
2. **Drying** — the chips were nitrogen-dried on 2026-11-05 and stored dry over a weekend before being re-wetted on 2026-11-11. Does the pinning/flattening that drying causes get **undone by rehydration**?

Both answers feed back into the protocol; the proposed edits are collected at the end of each section and are **not yet applied**.

## What the system is, and what the citations measured

Every statement below has to be read against the actual stack, because most of the literature on "DNA and graphene" studies a different one:

```text
graphene  →  pyrene (π-stacked)  →  C₃H₆–CO–NH  →  5′ end of the 50 nt strand
             PBASE, 1.15 nm SAM                  amide bond (covalent)
```

**The DNA never touches the graphene.** There is no DNA printed on, adsorbed on or in contact with the basal plane anywhere in this workflow. The strand hangs from the top of the PBASE carpet, and the surface it *can* contact is the carpet itself: pyrene faces, alkyl chains, amide and carboxylate groups from hydrolysed NHS, and ethanolamine caps (blocking measured at ~80% efficiency). That is a heterogeneous, non-conducting, partly charged organic layer — not a graphitic plane, and not a surface on which a strand can lie down and be held by a continuous aromatic sheet.

Three classes of evidence are used in these notes, and they transfer to different degrees:

| Class | What was measured | Examples | Transfers to us? |
| --- | --- | --- | --- |
| **A** | DNA or nucleobases **adsorbed directly on carbon** — graphene, graphite, HOPG, graphene oxide | nucleobase DFT energies; ssDNA adsorption/desorption; peeling force spectroscopy; graphene–mica melting DNA origami; GO displacement sensors | **Only as an upper bound.** Our bases have no route to the basal plane, and some of these mechanisms (spontaneous desorption into solution) are actively impossible for a covalent tether. |
| **B** | DNA **covalently tethered through PBASE** to graphene | the QCM-D linker study (probe density, rinse loss, blocking efficiency); GFET sensor papers; the quenching-distance work that anchors DNA with pyrene | **Directly** — this is our chemistry. |
| **C** | DNA **brushes on other self-assembled monolayers**, e.g. thiol-DNA on gold | hydration-dependent monolayer structure, collapse on drying, re-extension in salt | **Probably the closest analogue, and not yet reviewed.** Flagged as an open task. |

For **Q1 (quenching)** the distinction is already handled correctly: the quencher is the graphene, the carpet is a 1.15 nm spacer, and the dye's distance is measured to the graphene plane.

For **Q2 (pinning)** it was *not* handled, and that was an error in the first version of this note: the per-base adhesion numbers were quoted from class-A measurements and used as if they described our layer. They are corrected and labelled below.

---

## Q1. Does the PBASE carpet quench, or is it the graphene?

### Answer

**The graphene.** A PBASE monolayer is photochemically inert toward fluorescein — it neither absorbs, emits, nor accepts energy from FAM — and it contributes only a **1.15 nm standoff**, which is worth about **7 percentage points** of brightness at our geometry. Nothing about the carpet suppresses or adds quenching; the quenching is long-range non-radiative transfer from the dye into graphene's π electron system.

### Why the carpet cannot quench FAM

1. **No spectral overlap in either direction.** Pyrene absorbs at **336 nm** and emits at **384 nm**; fluorescein absorbs 495 and emits 515–525 nm. FAM* → pyrene Förster transfer needs pyrene absorption at 500–550 nm, where pyrene has none (its whole manifold lies below ~360 nm). Transfer *up* into pyrene's ~3.7 eV excited state from a ~2.4 eV excited FAM is energetically impossible. The same fact makes the carpet invisible in the Dino-Lite blue channel (465 nm excitation, 510–545 nm emission): pyrene absorbs nothing there, so there is neither an inner-filter effect nor pyrene emission to confuse a FAM frame.
2. **Photoinduced electron transfer is uphill and geometrically unreachable.** Aromatic molecules are quenched by graphene by electron transfer *to the graphene* — that is where the charge goes. For pyrene to quench FAM*, an electron would have to move from pyrene to excited fluorescein; pyrene's oxidation potential (~+1.2 V vs SCE) sits above fluorescein's excited-state reduction potential (~+0.9–1.0 V), so the reaction is endergonic. It would also need van der Waals contact (<1 nm), and our dye is covalently fixed at the far end of a 50-mer.
3. **The carpet is the quenched party, not the quencher.** Pyrene's own excited state is efficiently quenched once it is π-stacked on graphene — pyrene anchors are read at 275/376 nm precisely because they go dark on the surface. PBASE absorbs its own damage at the graphene interface; it does not relay energy to FAM.
4. **Graphene-only models already fit all the measured data, with no linker term.** Graphene's fluorescence yield is set by the fine-structure constant, the emission wavelength and the distance `z` alone; the transfer rate scales as **d⁻⁴** (not the d⁻⁶ of ordinary FRET). Measured anchors:
   - **d₀ = 17.7 ± 0.5 nm** (distance of 50% transfer efficiency), fitted over **3–58 nm**, with **97% quenching at the smallest distance**; orientation-weighted, 16.8 nm for a parallel dipole and 20.0 nm for a perpendicular one. Literature d₀ values across emitter types span **8–20 nm**, with one report of quenching out to 60 nm.
   - **4 nm → 7 nm gives a 7.5-fold** intensity change, and graphene quenches about **10× more strongly than gold**.
   - Pyrene is used in that same body of work as the *glue* that anchors DNA to graphene, i.e. the anchor is held constant while distance is varied — a pyrene-quenching term would break the design.
   - The graphene-aptasensor literature recovers signal only by lengthening a **DNA spacer** (0/10/20 T; 10/30 bp dsDNA), never by changing the pyrene linker.

### What it means quantitatively on our chip

`I/I₀ = (d/d₀)⁴ / [1 + (d/d₀)⁴]`, with `d₀ = 17.7 nm`; `I/I₀` is the fraction of FAM emission that survives.

| Configuration | d (nm) | Surviving FAM |
| --- | ---: | ---: |
| Upright 50 bp duplex, on a 1.15 nm PBASE carpet | 18.2 | **53%** |
| Same duplex on bare graphene, no carpet | 17.0 | **46%** |
| Duplex tilted ~60° from normal | ~9.7 | 9% |
| Duplex lying flat on the surface | 2–3 | 0.02–0.1% |
| FAM sitting on the carpet with no DNA | 1.2 | 0.002% |

- Geometry: PBASE self-assembled monolayer height **1.15 nm** (AFM); B-DNA rise **0.34 nm/bp**, so 50 bp = **17 nm**; the complement's 5′ fluorescein pairs with the template's 3′ end, which is the distal end.
- The carpet's contribution is the difference between the first two rows: **46% → 53%**. It does not rescue a dye at 1.2 nm either (0.002%), so there is no regime in which the carpet is doing protective work that matters.
- The only *other* quencher within range is **sequence-dependent guanine contact quenching of fluorescein**, worth roughly 10–30% for a G-rich neighbourhood. Our complement is 5′-FAM-**TGA**GACC…, with G at nt 3, 7, 9 — and this effect is identical in free solution, so a free-oligo reference droplet cancels it.

### Caveats

- d₀ is measured for ATTO 542 (562 nm emission); FAM emits at ~520 nm, on the blue side, so its d₀ is plausibly a little **smaller** — treat 15–18 nm as the working band rather than 17.7 exactly. The table's conclusions do not depend on that.
- All of the above is single-molecule or dilute-ensemble photophysics on graphene in buffer. A **dense** 1 µM monolayer adds inter-strand effects (self-quenching at high local dye density is small for fluorescein, which does not form ground-state dimers readily, but homo-FRET can depolarize and slightly redistribute emission) — not enough to change the readout logic.
- **Quenching is gate-tunable.** It depends on graphene's interband transitions, so electrostatically doping the graphene blocks the transfer and brightens the dye. On a GFET, fluorescence brightness therefore moves with liquid-gate voltage with no chemistry changing. Compare only frames taken at the same gate state, ideally floating.

### What changes in the protocol

1. `protocols/2026-11-11-fluor-tgtaatc-hybridization.md` line ~29 says the dye at ~17 nm is "at the far edge of that range: expect a real but attenuated signal". It is at the **midpoint**, by definition of d₀: **~47% is quenched and about half of solution brightness survives**. Being too pessimistic here is the difference between reading a half-bright result as success and as failure.
2. Add: **fix the gate state** (floating, or a recorded bias) for all fluorescence frames, white and blue, before and after.
3. The dim/bright logic still holds — a bright result confirms both hybridization *and* an upright layer; a dim result does not distinguish "no hybridization" from "lying flat" or "quenched". Q2 makes that ambiguity worse, not better.

---

## Q2. Does rehydration undo the pinning caused by drying?

### Answer

**Partly, and not the part that matters.** The theory "it fully rehydrates, so the damage reverses" is half right. Water returns to the film within seconds to minutes, and every segment of strand that is **not** in contact with the carpet regains solution-like freedom — secondary structure, base pairing, B-form geometry all recover. What water does **not** do is lift base segments that have stacked onto **the PBASE carpet**. There is no force available to do it, so drying leaves a **flattened fraction that is kinetically trapped**, and the fraction can only shrink by end-unpeeling and by being captured by the complement.

Note what that sentence does and does not claim. It claims stacking onto the **carpet**. It does not claim contact with graphene, and it does not import class-A adhesion energies — see the section on transfer below.

### What drying actually does

Three separate things, only one of which is reversible:

1. **Mechanical.** The meniscus recedes and capillary force pulls the strand down onto the surface, flattening it (the same effect that combs DNA straight at a drying droplet edge). This is the "pinching/pinning" everyone worries about, and it acts on the whole strand at once.
2. **Hydrational.** Removing the hydration shell traps the strand in a non-native conformation — the classic mica result is air-dried DNA stuck in a **mixture of A-form and B-form**, and high-humidity imaging shows conformational switching that is **irreversible**. So the trapped state is not simply "B-DNA waiting for water".
3. **Ionic.** Residual buffer concentrates as the last water leaves, which is why the protocol insists on water exchanges before drying. Ours got 3 × 500 µL (2026-11-05) and then 6 × 1 mL (2026-11-11), so salt is not the main worry for this particular chip.

### Numbers: why water alone will not unstack a base — class A, an upper bound for us

Every number in this subsection was measured with **nucleobases or ssDNA in direct contact with graphite or graphene**. They bound our case from above; they are not measurements of a PBASE-tethered strand.

- **Gas phase**, a nucleobase on **graphene** binds at roughly **0.5–1.2 eV** by vdW-corrected DFT (0.5 eV ≈ 19 kT at 300 K). Sequence order is G > A > T ≈ C.
- **In buffer**, water and ions compete, and the effective adhesion drops to roughly **0.07–0.2 eV per base**. My conversion from single-molecule peeling force spectroscopy **on graphite**: reported peeling forces are ~30–90 pN depending on base (85.3 ± 4.7 pN for the poly-C case), and at ~0.7 nm of contour released per nucleotide, `E ≈ F × 0.7 nm` gives **5–15 kT per base**. Peeling is a finite-rate measurement, so this is an upper bound on the equilibrium value — the honest range is **~3–15 kT per base**.
- Consequence: a contiguous contact patch of 10 bases is **30–150 kT**, i.e. an equilibrium dissociation constant of e⁻³⁰ to e⁻¹⁵⁰. On any experiment timescale that is permanent. **Only one base at a time comes off**, and only from a free end, because unpeeling an interior base means breaking two neighbours' stacking at once.
- There is also **no wetting force to help**: an aromatic face is a poor surface for water to squeeze under, and graphene itself is microscopically hydrophobic (contact angles reported ~40–90° depending on support and contamination, with a strong argument that pristine graphene is intrinsically hydrophobic and not wetting-transparent), with only **1–3 hydration layers** on it. Water does not intercalate under a stacked base, because doing so costs the base's adhesion and buys nothing. The carpet is more wettable than graphene — it carries amides and carboxylates — but the same argument applies to a base stacked on a pyrene face.

### How much of this transfers to a PBASE-tethered strand

**Much less, and this is the weakest link in the whole of Q2.** The honest position:

- **Some stacking does survive the carpet.** Pyrene faces are aromatic, so a nucleobase can π-stack on them, and the carpet is not perfectly ordered after ethanolamine blocking.
- **But the adhesion is smaller and the geometry forbids long contact patches.** The carpet is ~1.15 nm of mixed chemistry — aromatic heads, aliphatic chains, amides, residual carboxylates, ethanolamine caps — so a base contacts one ring face, not a continuous conducting plane. Adjacent bases cannot all lie on the same smooth surface, so contact patches are short. A 3-base patch at even 3 kT per base is ~9 kT: slow, but no longer astronomical.
- **Electrostatics pushes the wrong way for pinning.** Hydrolysed NHS leaves carboxylates, the strand is a polyanion, and both push the DNA off the carpet at pH 7.4.
- **Nobody has measured it.** Searches found no study of base adsorption onto a PBASE monolayer and no study of dry/wet cycling of a PBASE-tethered DNA brush. So the correct statement is: **pinning onto the carpet should be substantially weaker than onto graphene, so rehydration should recover more than the class-A literature implies — but that is an untested assumption.**
- **It is testable with a control we already planned.** The attachment protocol's *bare graphene + DNA* control is exactly the class-A case; run it through the same dry/wet cycle and compare the FAM signal and AFM height against the PBASE-tethered chip. The difference between those two chips *is* the carpet's protective effect, measured rather than assumed.

### What *does* de-pin, in decreasing order of usefulness

1. **Hybridization itself.** Two things happen here and only one is the class-A mechanism. Our strand is **covalently anchored**, so it never desorbs — unlike an adsorbed probe in the GO sensors, which is displaced into solution by its target. What hybridization does instead is pair bases so they no longer present a face to **the carpet**, and pairing is strongly cooperative: one nucleated duplex zips the rest off. So the complement is both label and de-pinner, but by zippering a tethered strand off the carpet, not by displacing it.
2. **Heat, i.e. the 90 °C hold we already have.** At 363 K, kT = 31 meV, so a 3–6 kT base becomes thermally accessible at an end, and end-unpeeling accelerates by orders of magnitude. With 1 µM complement present, each base captured is removed from the surface irreversibly. **The melt-and-ramp is doing double duty: it is the de-pinning step, not only the anneal.** That is a strong argument for keeping the 90 °C hold and not shortening the 37 °C hold.
3. **Longer, warmer pre-soak.** The protocol's 10 min in PBS at room temperature is enough to wet the film, not to relax it. 30–60 min at 45–50 °C in PBS (no denaturant) is free and moves in the right direction.
4. **Chemical competitors** — formamide, SDS/Triton, urea — will compete for the surface, but formamide lowers Tm (~0.6–0.7 °C per %), which breaks the 90 °C assumption, and surfactants foul the surface for the later HindIII step. **Not recommended here.**

The one genuinely strong mitigation is upstream: **do not dry the chip at all** between attachment and hybridization. The chip can stay wet from the attachment rinse through the anneal, which removes drying, the desiccator, and the AFM from the critical path. If dry AFM is needed on the same chip, put it **after** release, not between attachment and hybridization.

### Consequences for the 2026-11-05 chip (and for how we read it)

That chip got the worst case: nitrogen-dried, then a weekend in a desiccator, then re-wetted. Predictions, which should be written down before the run — **conditional on the carpet pinning at all like class-A pinning**:

- The **DNA is not lost** — the attachment is a covalent amide, so the strand count is unchanged and a dry AFM height of 1–2 nm would still look fine. What is lost is **accessibility and orientation**, not material.
- The **3′ end is especially exposed to pinning**, and the 3′ end is exactly where the complement has to nucleate. So hybridization yield should be **reduced and heterogeneous**, and the successful duplexes should sit **flatter** — both effects push the FAM signal down.
- Therefore a dim result on this chip is **ambiguous**: it cannot be attributed to "hybridization failed" or to "no template", because the drying history is a confound. This is the single most important consequence of Q2 for the protocol as written.
- **Unless the carpet protects the strand better than class-A evidence suggests**, in which case a 37 °C-only schedule on a dried chip may be adequate after all. That is the open question above, and the bare-graphene control answers it. Until then, treat the dim-because-pinned reading as a hypothesis, not a fact.

### Cheap decisive tests

- **Parallel control (decisive, one extra chip):** hybridize a **never-dried** replicate alongside the dried chip, same complement, same buffer, same schedule, same camera settings. If the never-dried chip is much brighter, pinning is confirmed and the fix is procedural.
- **Liquid AFM** (or dry AFM after re-wetting) on a re-wetted chip vs a never-dried one: a flattened, featureless layer versus an upright brush is visible as a height distribution.
- **No-complement thermal control** (already in the protocol) separates thermal loss of template from the hybridization signal.
- **45 °C stringency wash** (already in the protocol) is also the natural probe of the "adsorbed vs hybridized" split — a signal that survives it is duplex, a signal that dies was smeared on.

### What changes in the protocol

1. Add to the "Cost" section, as a first item: **this chip's drying history is a confound**; a dim result cannot distinguish failed hybridization from a pinned, flattened layer, and the fix is a never-dried replicate.
2. Replace "If the chip has been dry since 2026-11-05, allow 10 min in 1× PBS before adding complement, so the layer rehydrates" with an honest version: 10 min wets the film; **rehydration does not restore the conformation**, so allow 30–60 min at 45–50 °C, and expect residual pinning.
3. Note in the annealing section that the **90 °C hold is also the de-pinning step**, and that it is the reason not to shorten the ramp.
4. Add to "Common failure modes": *uniformly dim on a previously dried chip, bright on a never-dried replicate → drying-induced pinning, not a chemistry failure.*
5. Standing rule for future chips: **attachment → hybridization with no dry step in between.**

---

## Confidence and open questions

| Claim | Confidence | Basis |
| --- | --- | --- |
| PBASE does not quench FAM; graphene does | high | no spectral overlap; PET energetics; graphene-only d⁻⁴ models fit measured data |
| d₀ ≈ 17.7 nm, d⁻⁴, range 5–30 nm | high (measured), medium for FAM specifically | single-molecule DNA-origami measurement at 562 nm emission; FAM emits bluer |
| Carpet worth ~7 points of brightness at 18 nm | high | arithmetic on the above |
| Quenching is gate-tunable | high as a phenomenon, untested on our setup | ionic-liquid-gated graphene with QDs |
| Our DNA never contacts the graphene; the question is base–**carpet** contact | high that the geometry holds; the energetics are unmeasured | the stack is graphene → PBASE → amide → strand; no route to the basal plane |
| Per-base adhesion 3–15 kT in buffer | medium, **and class A only** | force-spectroscopy peeling on graphite, my own conversion; finite-rate upper bound; does not describe base-on-pyrene |
| Rehydration does not restore a class-A adsorbed layer | medium-high | DNA-on-mica trapping literature, carbon adsorption irreversibility |
| A **PBASE-tethered** strand also stays pinned | **low-medium — the key untested assumption** | inferred from class A by analogy; the carpet is a heterogeneous organic layer with shorter possible contact patches and an electrostatic push-off; no measurement found |
| 90 °C hold de-pins enough to allow nucleation | **low-medium** | inferred from kT scaling and end-unpeeling; untested |

Open questions worth naming rather than assuming:

- **Does a PBASE-tethered strand pin at all on drying, and how hard?** No measurement exists. This is the assumption the drying argument rests on, and the bare-graphene + DNA control measures the difference directly.
- Is the closest analogue actually **class C** — DNA on an alkanethiol SAM on gold, where hydration-dependent monolayer structure and collapse-on-drying are well studied? That literature has not been reviewed here and should be, before the pinning claim is treated as settled.

- Does the PBASE carpet measurably lower the effective per-base adhesion compared with bare graphene? A re-wetted-chip vs bare-graphene adsorption comparison would answer it, and it also decides whether the no-template control is a good false-positive floor.
- How much of the FAM signal on a densely hybridized monolayer is lost to inter-strand effects (homo-FRET, crowding) as distinct from graphene quenching?
- Does the 90 °C hold cost template (pyrene π-stack is the weakest link)? The no-complement thermal control answers this and should be run before the main comparison, not after.

---

## References

Class labels (**A** = DNA in direct contact with carbon, **B** = DNA covalently tethered via PBASE, **C** = DNA on another SAM) are given where the class is not obvious from the title.
1. Kaminska, Bohlen, Rocchetti, Selbach, Acuna, Tinnefeld. *Distance Dependence of Single-Molecule Energy Transfer to Graphene Measured with DNA Origami Nanopositioners.* Nano Lett. (2019). doi:10.1021/acs.nanolett.9b00172 — d₀ = 17.7 ± 0.5 nm, d⁻⁴ over 3–58 nm, 97% quenching at 3 nm, pyrene as the graphene anchor, d₀ 16.8/20.0 nm for parallel/perpendicular dipoles.
2. Swathi & Sebastian. *Resonance energy transfer from a dye molecule to graphene.* J. Chem. Phys. 129:054703 (2008); *Long range resonance energy transfer from a dye molecule to graphene has (distance)⁻⁴ dependence.* J. Chem. Phys. 130:086101 (2009).
3. Gómez-Santos & Stauber. *Fluorescence quenching in graphene: a fundamental ruler and evidence for transverse plasmons.* arXiv:1108.1160 — yield set by α, λ, z only.
4. Kasry, Ardakani, Tulevski, Menges, Copel, Vyklicky. *Highly Efficient Fluorescence Quenching with Graphene.* J. Phys. Chem. C (2012). doi:10.1021/jp207972f — 4→7 nm gives 7.5×; ~10× stronger than gold.
5. Salihoglu, Kakenov, Balci, Balci, Kocabas. *Graphene as a Reversible and Spectrally Selective Fluorescence Quencher.* Sci. Rep. 6:33911 (2016) — electrostatic gating blocks the non-radiative transfer; 5/10/15 nm QD spacings.
6. *Quenching of fluorescence of aromatic molecules by graphene due to electron transfer.* Chem. Phys. Lett. (2011) — PET from aromatics to graphene.
7. *Graphene as a Quencher of Electronic Excited States of Photochemical Probes.* Langmuir (2012). doi:10.1021/la204023w — pyrene's own excited state quenched on graphene.
8. Zhu, Lin, Zhang et al. *Predicting the Level of Background Current Noise in Graphene Biosensor through a Non-Covalent Functionalization Process.* Crystals 13(2):359 (2023) — PBASE SAM height ≈ 1.15 nm.
9. Ueno. *On-Chip FRET Graphene Aptasensor* — Anal. Sci. 31:875 (2015) (dsDNA spacers) and Anal. Sci. 37:437 (2021) (review; 0/10/20 T ssDNA spacers; pyrene anchor).
10. Crockett & Wittwer. *Fluorescein-labeled oligonucleotides for real-time PCR: using the inherent quenching of deoxyguanosine nucleotides.* Anal. Biochem. (2001); Lietard, Ameur, Somoza. *Sequence-dependent quenching of fluorescein fluorescence on single-stranded and double-stranded DNA.* RSC Adv. (2022). doi:10.1039/D2RA00534D.
11. **[A]** Lee, Choi, Kim et al. *Physisorption of DNA nucleobases on h-BN and graphene: vdW-corrected DFT.* J. Phys. Chem. C (2013). doi:10.1021/jp402403f; Le, Kara, Schröder et al. *Physisorption of nucleobases on graphene: a comparative van der Waals study.* J. Phys. Condens. Matter 24:424210 (2012). Both measure free nucleobases on a bare basal plane — class A, not our geometry.
12. Iliafar, Wagner, Vezenov et al. *Peeling Single-Stranded DNA from Graphite Surface to Determine Oligonucleotide Binding Energy by Force Spectroscopy.* Nano Lett. (2008). doi:10.1021/nl8022143 — 85.3 ± 4.7 pN for the poly-C case; and *Quantifying Interactions between DNA Oligomers and Graphite Surface* (2012); *Direct force measurements on peeling heteropolymer ssDNA from a graphite surface* (2013), doi:10.1039/c3cp54121e.
13. **[A]** Wu, Kempaiah, Huang, Maheshwari, Liu. *Adsorption and Desorption of DNA on Graphene Oxide Studied by Fluorescently Labeled Oligonucleotides.* Langmuir 27:2731 (2011) — ssDNA adsorbs, dsDNA much more weakly; desorption is driven by hybridization, not dilution. Class A: the probe is *adsorbed*, not tethered.
14. **[A]** Lu, Yang, Zhu, Chen, Chen. *A Graphene Platform for Sensing Biomolecules.* Angew. Chem. Int. Ed. (2009) — hybridization displaces an adsorbed probe; ~97% quenching of an adsorbed FAM probe. Class A.
15. **[A]** Fang, Ye, Hoh et al. *Ethanol-induced structural transitions of DNA on mica.* Nucleic Acids Res. 27:1943 (1999) — air-dried DNA trapped in mixed A/B form. PCCP (2010), doi:10.1039/c0cp01347a — humidity-driven conformational change of dried DNA is **irreversible**. Class A (mica, not carbon), used for the trapping mechanism only.
16. Garcia. *Interfacial Liquid Water on Graphite, Graphene, and 2D Materials* (2022) — contact-angle spread and 1–3 hydration layers; Nature Communications (2026) doi:10.1038/s41467-026-71053-3 — pristine graphene intrinsically hydrophobic, not wetting-transparent.
17. **[A]** Pham et al. *Layered graphene-mica substrates induce melting of DNA origami.* Mater. Res. Express 5:045035 (2018) — graphene contact denatures **adsorbed** DNA nanostructures. Cited only as evidence that a bare carbon surface is not passive towards DNA; our strands are tethered through the carpet and never present a base to the basal plane.
18. Our own records: [`protocols/2026-11-05` attachment](../protocols/2026-11-05-amino-gattaca-pbase-graphene.md) (nitrogen dry + desiccator weekend), [`protocols/2026-11-11` re-rinse and imaging](../protocols/2026-11-11-water-rinse-and-dino-lite-imaging.md), [`protocols/2026-11-11` hybridization](../protocols/2026-11-11-fluor-tgtaatc-hybridization.md), [`primer.md`](../primer.md), [`proposal.tex`](../proposal.tex).

## Related

- Quenching determines what the fluorescence channel can and cannot claim: [hybridization protocol, "Where the dye ends up matters"](../protocols/2026-11-11-fluor-tgtaatc-hybridization.md).
- Drying determines how much of the layer is accessible at all: [attachment protocol, "Endpoint and record"](../protocols/2026-11-05-amino-gattaca-pbase-graphene.md) and the [rinse record](../protocols/2026-11-11-water-rinse-and-dino-lite-imaging.md).
- What other people do about storage, and which layer tolerates it: [dry storage and rehydration](2026-11-12-dry-storage-and-rehydration.md).
