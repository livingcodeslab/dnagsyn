# Hybridization of the fluorescein complement (fluor-tgtaatc) to surface-tethered amino-gattaca

**Date:** 2026-11-11  
**Status:** proposed — written 2026-11-11, not yet run.  
**What we do:** anneal **1 µM fluor-tgtaatc** onto the surface-bound template by heating to **90 °C for 5 min** and cooling **~1 °C per minute to 37 °C**, wash with **1× PBS**, and image the same field under white and blue excitation on the Dino-Lite.

Prerequisite: [attachment and blocking](2026-11-05-amino-gattaca-pbase-graphene.md), and the [2026-11-11 rinse and imaging baseline](2026-11-11-water-rinse-and-dino-lite-imaging.md).

## What this step is for, and what it costs

**For:** a fluorescent readout that the template is on the surface, positioned where we think it is, at a density the Dino-Lite can see. The dye is on the incoming strand, so nothing is labelled until hybridization succeeds; unhybridized surface is invisible.

**Cost:** the complement is the **exact 50 nt reverse complement**, so it duplexes the template from nt 1 to nt 50 — **including the template's 3′ terminus**. A duplexed 3′ end is not a TdT substrate, so **a chip that has been through this protocol cannot be used for enzymatic extension**. Do it on a replicate chip, or accept that the chip is spent for TdT work and keep at least one unhybridized chip aside.

**Second use:** this is the annealing half of the release step in `proposal.tex` (Protocol 1, step 6). Same molecules, same ramp. If the intent is HindIII release rather than imaging, stop after the anneal and the PBS washes and exchange into HindIII buffer — see the last section.

## The two strands

| | Sequence (5′→3′) | Ends | Source |
| --- | --- | --- | --- |
| **amino-gattaca** (template, on surface) | `GATTACACAGGCAAGCTTAGGATGTAGGTCTTAACTCGTCTCTGGTCTCA` | 5′ **amine → PBASE**, 3′ **free OH** | 515766H05, 26.9 µM |
| **fluor-tgtaatc** (complement, in solution) | `TGAGACCAGAGACGAGTTAAGACCTACATCCTAAGCTTGCCTGTGTAATC` | 5′ **fluorescein**, 3′ free OH | 515677F09, 100 µM annotated |

50 nt each, 46% GC, PAGE purified, exact reverse complements — a **blunt 50 bp duplex** with no overhangs.

Where the dye ends up matters for whether it can be seen:

- The complement's **5′ fluorescein pairs with the template's 3′ end**, which is the end **distal** from the graphene. In an upright duplex that puts the dye ~50 bp × 0.34 nm ≈ **17 nm** off the surface.
- **Graphene quenches nearby fluorophores** by distance-dependent energy transfer, strongly within roughly 10–20 nm. At ~17 nm the dye is at the far edge of that range: expect a real but attenuated signal, and expect it to depend on the duplex standing up rather than lying flat. A bright result confirms both hybridization *and* an upright layer; a dim result does not distinguish "no hybridization" from "lying flat" or "quenched".
- Nonspecifically adsorbed complement on bare graphene is quenched far more strongly than a hybridized, standing duplex. That works in our favour, but it is also why a *dark* bare region is not proof that nothing adsorbed there — use the white-excitation partner image and the AFM for that.

## Reagents

| Reagent | Stock | Working |
| --- | --- | --- |
| fluor-tgtaatc | 100 µM (handwritten; **remeasure**) | **1 µM in 1× PBS** |
| 1× PBS, pH 7.4 | — | anneal buffer and all washes |
| ultrapure water | — | only if going on to an enzymatic step |

**Do not use TE or any EDTA-containing buffer here.** EDTA chelates the Mg²⁺ that HindIII needs if this anneal is the prelude to release. PBS has no Mg²⁺ either, so a buffer exchange is required before HindIII in any case.

### Check the complement stock before you use it

The certificate records **19.7 nmol** and the tube is hand-annotated **100 µM with no reconstitution volume** — the annotation has never been verified, and the oligo was made in May 2024. Two readings on 5 µL into 995 µL of 1× PBS (200-fold), blanked against the same buffer:

| Reading | If the tube really is 100 µM | Interpretation |
| --- | --- | --- |
| **A₂₆₀** | **0.29** | 0.29 × 200 / 0.5807 = 100 µM (the printed 580.7 OD/µmol is ε₂₆₀ = 5.807 × 10⁵ M⁻¹cm⁻¹) |
| **A₄₉₅** | **≈ 0.034** | fluorescein ε₄₉₅ ≈ 6.8 × 10⁴ M⁻¹cm⁻¹ at pH > 8, lower at pH 7.4 |
| **A₄₉₅/A₂₆₀** | **≈ 0.12** | the expected ratio for one fluorescein per 50-mer |

A ratio near 0.12 says the dye is intact and attached; near zero says the labelling is gone or bleached, and no amount of washing will produce a signal. A₂₆₀ gives the concentration. Adjust the dilution to hit 1 µM rather than trusting the label.

If the tube is dry, dissolve the 19.7 nmol in **197 µL** of ultrapure water or 1× PBS for 100 µM; if it is already in solution, measure as above.

### Working solution

| Component | Volume |
| --- | ---: |
| fluor-tgtaatc, 100 µM | **5.0 µL** |
| 1× PBS, pH 7.4 | **495 µL** |
| Total | **500 µL at 1.00 µM** |

500 pmol is **2.5% of the 19.7 nmol tube** and covers 10 chips at 50 µL, or one chip in a 500 µL tube. Prepare it fresh, keep it foil-wrapped, and do not refreeze what is left.

**That is 30–60× more molecules than there are surface sites.** 500 pmol is 3.0 × 10¹⁴ molecules; a 1 cm² graphene area carries roughly 10¹²–10¹³ tethered strands at the densities reported for this chemistry. Excess complement is therefore not a limitation, and pushing the concentration higher buys nothing. What limits hybridization on a dense monolayer is **steric and electrostatic crowding**, not supply — which is the argument for the salt concentration below, not for more DNA.

## 1. Re-equilibrate the chip in salt

The chip has just been through six water exchanges and may be dry. **Hybridization does not happen in water:** the surface is a dense polyanion and the incoming strand is another, so at low ionic strength the two repel each other and the duplex never forms.

1. Rinse the chip **3 × 500 µL 1× PBS, pH 7.4**, a few seconds each, keeping it wet throughout.
2. If the chip has been dry since 2026-11-05, allow **10 min** in 1× PBS before adding complement, so the layer rehydrates.
3. Keep the graphene face up in every transfer.

## 2. Anneal — 90 °C, 5 min, then cool ~1 °C/min to 37 °C

**The temperature schedule is the whole experiment**, and the printed Tm values set it:

| Conditions | Na⁺ | Tm of this 50 bp duplex |
| --- | ---: | ---: |
| printed certificate | 50 mM | **79 °C** |
| 1× PBS | 137 mM | **≈ 86 °C** (interpolated: the printed points give ~17 °C per decade of [Na⁺]) |
| printed certificate | 1 M | **101 °C** |

In 1× PBS the perfectly matched duplex melts at about **86 °C**, so a 90 °C hold melts it completely and cooling back through 86 °C is what re-forms it — specifically, and only where the match is full-length.

1. Add **500 µL of the 1 µM complement** to the chip, graphene face up, **in a sealed container** (below).
2. **90 °C for 5 min.** Below 86 °C the pre-existing structure never opens; above ~95 °C the pyrene π-stack that holds PBASE to the graphene is being stressed for no gain. Stay in that window.
3. **Cool to 37 °C at about 1 °C/min** — roughly 50 min from 90 °C. Passive cooling of a bath or a block does this by itself; do not shortcut it with an ice bucket or a cold-room transfer. Fast cooling traps mismatched and partially annealed structures and leaves the layer patchy.
4. **Hold at 37 °C for 15–30 min**, then move to room temperature. Keep it dark: fluorescein photobleaches, and a foil wrap costs nothing.

**Containers that work:**

- **A 15 mL screw-cap tube** with 500 µL in it, chip flat at the bottom, cap tight, floated in a 90 °C water bath then left to cool with the bath. This is the simplest sealed chamber, and it is why the volume is 500 µL rather than 50 µL.
- **A 24-well plate well**, 1 mL per well, plate sealed with adhesive film, floated in the bath. Matches the [2026-11-11 rinse](2026-11-11-water-rinse-and-dino-lite-imaging.md) handling exactly, at twice the complement.
- **A thermocycler**, if a chip holder can be made to fit — best ramp control, most fiddly.

**What kills this step is evaporation, not the temperature.** At 90 °C a 50 µL open droplet is gone in minutes and leaves the layer dry and salted. If you use a small droplet under a coverslip or a parafilm seal instead of a sealed tube, put a layer of mineral oil over it. After the run, check that the volume is unchanged; a drop in volume means the concentration rose and the layer may have dried at the edge.

**The one non-standard element is the 90 °C hold**, and the pyrene π-stack is the weakest link in the whole stack of layers — it is a non-covalent attachment being heated. If that is a concern, run one chip through the identical schedule with **buffer and no complement** and image it in the white channel: if the template layer survives 90 °C, that chip looks like the pre-hybridization chip. A gentler alternative is 70 °C for 10 min and slow cooling, which anneals the duplex fine but destructures the tethered strand less completely.

## 3. Wash off the unhybridized complement

1. Take off the anneal solution. **3 × 500 µL 1× PBS, pH 7.4, at room temperature**, flowed over the surface from the edge, no direct jet.
2. **One stringent wash: 500 µL 1× PBS at 45 °C for 5 min.** This is ~40 °C below Tm, so a full-length duplex is untouched; it removes complement that is stuck by adsorption or by a partial match. This is the wash that separates "hybridized" from "smeared on".
3. **2 × 500 µL 1× PBS at room temperature.**
4. **Do not water-rinse and do not dry the chip before imaging.** There is no salt artifact to remove if the chip stays wet, drying concentrates buffer at the perimeter into exactly the crystalline ring that ruins a micrograph, and fluorescein is dimmer as the pH drops. Image in PBS.

## 4. Image

Use the **same chip, same fields and same camera settings** as [images 36–39](2026-11-11-water-rinse-and-dino-lite-imaging.md):

1. Match magnification, focus and the **manual** exposure/gain/white balance used for 36–39. If the scope auto-exposes, the blue and white frames are not comparable and neither is the before/after pair.
2. **Low magnification, white then blue**, reproducing **36 → 37**.
3. **Corner, higher magnification, white then blue**, reproducing **38 → 39**.
4. **Five consecutive blue captures of one field.** Fluorescein fades under illumination; reflection, scattering and substrate autofluorescence do not. This is the free specificity test.
5. **Record** the blue LED wavelength and whether an emission filter was fitted. Without a filter the excitation light reaches the sensor directly and a dim signal is uninterpretable.
6. Keep the chip wet and foil-wrapped between acquisitions.

Readout is a **paired ratio, not a brightness**: blue-over-white intensity on the DNA region, after hybridization, compared with the same ratio in 37 and 39. That normalizes out illumination unevenness, dust and scope drift. Report arbitrary units with the settings, and do not compare numbers across sessions.

## Controls

- **DNA chip + complement** — the test.
- **DNA chip, no complement**, through the full 90 °C schedule — separates thermal loss of the layer from hybridization signal.
- **PBASE + block only + complement** — complement on a surface with no template: this is adsorption, and it sets the false-positive floor. Essential, because the whole claim rests on the complement being *sequence-specifically* captured.
- **A bare-graphene region in frame**, where the coating allows, as an on-chip background.
- No non-complementary fluorescein oligo is in hand, so the sequence-specificity control is the no-template chip above plus the 45 °C wash. If a mismatched oligo is ever ordered, it belongs here.
- **Brightness alone is not proof.** Quenching, uneven illumination and dye adsorbed to the substrate all move the number. A signal that (i) appears only on the templated region, (ii) survives the 45 °C wash and (iii) fades under repeated illumination is the combination worth believing.

## Common failure modes

| Observation | Likely cause |
| --- | --- |
| No signal anywhere, including the no-template control | dye damaged or labelling lost — check A₄₉₅/A₂₆₀; or no emission filter, so excitation swamps everything |
| Signal on template **and** no-template chip | adsorption, not hybridization; salt too high for the wash, or the 45 °C wash was skipped |
| Signal present but disappears after the 45 °C wash | partial or mismatched duplex, or adsorption |
| Patchy signal, bright rim | evaporation during the 90 °C hold; the layer dried at the edge |
| Uniformly dimmer than before hybridization, including white channel | the 90 °C hold cost template — compare against the no-complement thermal control |
| Signal only where the droplet edge was | the chip went dry at some point; keep wet |

## If this is the prelude to HindIII release

The anneal is identical. Then:

1. Skip the stringent wash if it complicates the flow path, but do **not** skip the PBS washes: HindIII needs its own buffer.
2. **Exchange into HindIII buffer containing Mg²⁺**, and with **no Co²⁺** — Co²⁺ inhibits HindIII and can relax its specificity, and it is the ion the TdT reaction would have brought in.
3. Add HindIII, **37 °C**, and collect the wash.

The cut is internal, at `A^AGCTT` (template nt 13|14), so the released product is the 37 nt downstream fragment plus whatever TdT appended, and the complement is split too: the **33 nt** piece paired to template nt 18–50 carries the fluorescein off the surface, the **17 nt** piece stays behind on the surface stub. The dye's length is therefore fixed at 33 nt whatever TdT did — under denaturing CE it reports **how much** was released, not how long the products are. Length distributions need nanopore sequencing of the released material.

## Why these numbers

| Choice | Why |
| --- | --- |
| 1 µM complement | same concentration as the attachment step, 30–60× excess over surface sites |
| 90 °C / 5 min | ~4 °C above the ~86 °C Tm in 1× PBS, so the duplex fully melts; kept below 95 °C to spare the pyrene π-stack |
| 1 °C/min to 37 °C | slow enough to anneal specifically and avoid trapping partial duplexes |
| 1× PBS (137 mM Na⁺) | screens the polyanion repulsion that stops hybridization in water, and is the buffer already in use |
| 45 °C stringency wash | ~40 °C below Tm: removes adsorbed and partial material, cannot melt the full-length duplex |
| 500 µL | fills a 15 mL screw-cap tube over a 1 cm² chip and keeps it sealed at 90 °C |

## References

1. Invitrogen certificates of analysis, order 12091076 — [fluor-tgtaatc](../reports/invitrogen/12091076/02-fluor-tgtaatc.md) (515677F09, 19.7 nmol, 50 nt, 46% GC, ε₂₆₀ 580.7 OD/µmol, Tm 101 °C at 1 M Na⁺ and 79 °C at 50 mM Na⁺) and [amino-gattaca](../reports/invitrogen/12091076/01-amino-gattaca.md).
2. `proposal.tex`, "Release chemistry: duplex formation and internal HindIII cleavage" — duplex orientation, the 37 nt product, and why the fluorophore reports amount rather than length.
3. [`primer.md`](../primer.md) — the HindIII release design and why the Type IIS sites are not used for on-chip release.
4. Xu et al., *Nat Commun* **8**:14902 (2017) and Ping et al., *ACS Nano* **10**:8700 (2016) — 1 µM oligo working concentrations and surface hybridization on graphene.
