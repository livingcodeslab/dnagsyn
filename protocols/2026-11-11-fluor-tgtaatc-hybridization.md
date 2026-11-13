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
| **fluor-tgtaatc** (complement, in solution) | `TGAGACCAGAGACGAGTTAAGACCTACATCCTAAGCTTGCCTGTGTAATC` | 5′ **fluorescein**, 3′ free OH | 515677F09, annotated 100 µM |

50 nt each, 46% GC, PAGE purified, exact reverse complements — a **blunt 50 bp duplex** with no overhangs.

Where the dye ends up matters for whether it can be seen:

- The complement's **5′ fluorescein pairs with the template's 3′ end**, which is the end **distal** from the graphene. In an upright duplex that puts the dye ~50 bp × 0.34 nm ≈ **17 nm** off the surface.
- **Graphene quenches nearby fluorophores** by distance-dependent energy transfer, strongly within roughly 10–20 nm. At ~17 nm the dye is at the far edge of that range: expect a real but attenuated signal, and expect it to depend on the duplex standing up rather than lying flat. A bright result confirms both hybridization *and* an upright layer; a dim result does not distinguish "no hybridization" from "lying flat" or "quenched".
- Nonspecifically adsorbed complement on bare graphene is quenched far more strongly than a hybridized, standing duplex. That works in our favour, but it is also why a *dark* bare region is not proof that nothing adsorbed there — use the white-excitation partner image and the AFM for that.

## What you need at the bench

Everything below is what one chip costs. Two controls need their own chips, so multiply by the number of chips actually being run.

### Chips

- **One DNA-bearing chip** — the 2026-11-05 attachment. Read the drying caveat below before deciding this is the right chip.
- **PBASE + block only, no template** — the adsorption control. Without it, a signal cannot be called sequence-specific.
- **DNA chip, no complement** — the thermal control for the 90 °C hold, essential rather than optional because the pyrene π-stack is the weakest layer on the chip.
- A **bare graphene area in the same field**, where the coating leaves one.

### Reagents and volumes, per chip

| Reagent | Amount | Note |
| --- | ---: | --- |
| fluor-tgtaatc | 500 pmol = **5.0 µL at 100 µM**, or **25.3 µL at 19.75 µM** | foil-wrapped; settle the stock first |
| 1× PBS, pH 7.4 | **~6 mL** | 1.5 mL re-equilibration + 0.5 anneal + 1.5 first wash + 0.5 stringency + 1.0 final + 0.5 for dilutions and pipette error |
| ultrapure water | not needed before imaging | water before a dry step only, and there is no dry step here |

PBS must be **amine-free and EDTA-free**: no Tris, TE, TAE, or glycine.

### Equipment

| Item | Why | Note |
| --- | --- | --- |
| UV-Vis (NanoDrop or cuvette) + PBS blank | the stock check | the one blocking measurement; nothing else can substitute for it |
| P20, P200, P1000 + tips | 5 µL or 25.3 µL draw, 500 µL exchanges | use the smallest pipette the volume allows |
| 15 mL screw-cap tube, or a 24-well plate + sealing film | the sealed 90 °C chamber | a 50 µL open droplet evaporates in minutes at 90 °C; this is why the anneal volume is 500 µL |
| Water bath reaching 90 °C | the anneal | preferred over a block: uniform, and it cools passively at close to the required ~1 °C/min |
| Thermometer or thermocouple | **the ramp is the experiment** | log the temperature every few minutes; 1 °C/min is currently an assumption about how the bath cools, not a measured fact |
| 37 °C block/incubator | the 15–30 min hold | |
| 45 °C block/bath | the stringency wash | ±2 °C matters at this step |
| Dino-Lite AM4117MT-G2FBW, on its stand | imaging | integral 465 nm excitation and 510–545 nm emission filter; fix **manual** exposure, gain and white balance |
| Foil | light protection | fluorescein photobleaches; costs nothing |
| Balance, optional | evaporation check | weigh the sealed tube before and after the 90 °C hold |

### Settle these five things before the chip goes into the tube

1. **Is the stock 100 µM or 19.75 µM?** Measure the volume and A₂₆₀ (§ *Check the complement stock*). It changes the draw by 5×.
2. **Is this chip the right chip?** If it is the chip that was dried on 2026-11-05 and stored dry, a dim result will be uninterpretable — drying flattens and traps the layer and rehydration does not reverse it. A never-dried replicate, hybridized alongside, is the only way to read this run. See [the drying note](../notes/2026-11-12-fluorescence-quenching-and-drying.md).
3. **Imaging only, or the prelude to HindIII?** If release: HindIII and its Mg²⁺ buffer must be on hand **and HindIII is not recorded anywhere in this repository** — check it exists, is in date, and has a buffer without Co²⁺.
4. **Are the camera settings fixed and written down?** [The settings record](dinocapture-settings-record.md) still has its FINAL STANDARD block blank. With auto-exposure on, the before/after blue-over-white ratio that the whole readout rests on is not a measurement.
5. **Who logs the ramp, and where?** Chip ID, stock readings, bath temperature every few minutes, wash volumes, and the four image numbers — in the run record, at the time.

## Reagents

| Reagent | Stock | Working |
| --- | --- | --- |
| fluor-tgtaatc | annotated **100 µM** — 197.5 µL tube, or 19.75 µM if it was made up in 1 mL (**measure**) | **1 µM in 1× PBS** |
| 1× PBS, pH 7.4 | — | anneal buffer and all washes |
| ultrapure water | — | only if going on to an enzymatic step |

**Do not use TE or any EDTA-containing buffer here.** EDTA chelates the Mg²⁺ that HindIII needs if this anneal is the prelude to release. PBS has no Mg²⁺ either, so a buffer exchange is required before HindIII in any case.

### Check the complement stock before you use it

The certificate records **19.752 nmol** (11.47 OD ÷ 580.7 OD/µmol) and the tube is annotated **100 µM**. No reconstitution volume was written down, and the other two oligos in the same order were resuspended in **1 mL** — which, in this tube, would be **19.75 µM**. So the annotation implies a volume rather than recording one:

```text
19.752 nmol ÷ 100 µM   = 197.5 µL   →  the annotation is right
19.752 nmol ÷ 1 mL     =  19.75 µM  →  the annotation is wrong
```

Both cannot be true, and the tube itself decides. The solvent and the date were never recorded either, and the oligo was made in May 2024. **Measure the volume, then A₂₆₀ and A₄₉₅ on 5 µL into 995 µL of 1× PBS (200-fold), blanked against the same buffer:**

| Reading | If the tube is 197.5 µL at 100 µM | If the tube is ~1 mL at 19.75 µM |
| --- | --- | --- |
| **A₂₆₀** | **0.29** — 0.29 × 200 / 0.5807 = 100 µM (580.7 OD/µmol is ε₂₆₀ = 5.807 × 10⁵ M⁻¹cm⁻¹) | **≈ 0.057** |
| **A₄₉₅** | **≈ 0.034** | ≈ 0.0068 |
| **A₄₉₅/A₂₆₀** | **≈ 0.12** | **≈ 0.12** — the ratio is concentration-independent |

A ratio near 0.12 says the dye is intact and attached; near zero says the labelling is gone or bleached, and no amount of washing will produce a signal. A₂₆₀ gives the concentration, and the volume tells you which of the two accounts above you are in. Record both before diluting anything.

If the tube turns out to be dry — it should not be — dissolve the **19.752 nmol in 197.5 µL** of ultrapure water or 1× PBS for 100 µM. If it holds some other volume, that volume is the measurement and the concentration follows from 19.752 nmol ÷ V: 150 µL means 132 µM, 1 mL means 19.75 µM. Adjust the working-solution draw rather than trusting the label.

### Working solution

| Component | 100 µM stock | 19.75 µM stock |
| --- | ---: | ---: |
| fluor-tgtaatc | **5.0 µL** | **25.3 µL** |
| 1× PBS, pH 7.4 | **495 µL** | **474.7 µL** |
| Total | **500 µL at 1.00 µM** | **500 µL at 1.00 µM** |

500 pmol is **2.5% of the 19.7 nmol tube** and covers 10 chips at 50 µL, or one chip in a 500 µL tube. Prepare it fresh, keep it foil-wrapped, and do not refreeze what is left.

**That is 30–60× more molecules than there are surface sites at 100 µM, and 6–12× at 19.75 µM.** 500 pmol is 3.0 × 10¹⁴ molecules; a 1 cm² graphene area carries roughly 10¹²–10¹³ tethered strands at the densities reported for this chemistry. Excess complement is therefore not a limitation in either case, and pushing the concentration higher buys nothing. What limits hybridization on a dense monolayer is **steric and electrostatic crowding**, not supply — which is the argument for the salt concentration below, not for more DNA.

## 1. Re-equilibrate the chip in salt

The chip has just been through six water exchanges and may be dry. **Hybridization does not happen in water:** the surface is a dense polyanion and the incoming strand is another, so at low ionic strength the two repel each other and the duplex never forms.

1. Rinse the chip **3 × 500 µL 1× PBS, pH 7.4**, a few seconds each, keeping it wet throughout.
2. If the chip has been dry since 2026-11-05, allow **30–60 min at 45–50 °C** in 1× PBS before adding complement. Ten minutes wets the film but does not relax a layer that dried flat: rehydration restores the strand's freedom only where it is not in contact with the surface, and the pinning itself is not reversed by water (see [the drying note](../notes/2026-11-12-fluorescence-quenching-and-drying.md)). The warm soak is the cheapest head start; the 90 °C hold below is the real de-pinning step.
3. Keep the graphene face up in every transfer.

## 2. Anneal — 90 °C, 5 min, then cool ~1 °C/min to 37 °C

**The temperature schedule is the whole experiment**, and the printed Tm values set it:

| Conditions | Na⁺ | Tm of this 50 bp duplex |
| --- | ---: | ---: |
| printed certificate | 1 M | **101 °C** |
| 1× PBS | 137 mM | **≈ 86 °C** |
| printed certificate | 50 mM | **79 °C** |
| interpolated | 10 mM | **≈ 67 °C** |
| interpolated | 1 mM | **≈ 50 °C** |
| interpolated | ultrapure water, ~0.1 mM | **≈ 33 °C** |

The 1 M and 50 mM points are printed and give **~17 °C per decade of [Na⁺]**; every other row is that interpolation, which is a standard approximation and formally weak below ~10 mM, so treat the bottom two rows as ±5 °C. It is enough to make one point: **the water rinse is not a mild step for a duplex.** At 22 °C in ultrapure water the margin is about **11 °C**; in ice-cold water it is about **29 °C**. That is why the final rinse before drying is either 0.15–0.3 M ammonium acetate (volatile, keeps ionic strength, leaves no crystals) or **ice-cold water for 5–10 s per exchange**, and never room-temperature water at leisure.

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

**If a dry step is required — AFM, or storage — the rinse before it is the one place in this protocol where low salt is dangerous, and there is a sequencing rule that nearly removes the risk:**

- **Drying an unhybridized chip is close to free.** A single-stranded tether has no duplex to melt, so water at room temperature costs only base–carpet contacts, which is the weak effect. Rinse in water, N₂ dry, desiccator, and hybridize later.
- **Never water-rinse after hybridization at room temperature.** The duplex exists, and water puts Tm in the 30s. Use ammonium acetate, or ice-cold water fast.
- The 45 °C stringency wash stays in **1× PBS**. In water it would be ~12 °C from this duplex's Tm and would strip the layer it is meant to certify.

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
