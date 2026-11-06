# First attachment of amino-gattaca to PBASE-functionalized graphene

**Date:** 2026-11-05  
**Status:** first run; not yet validated on this chip.  
**What we do:** 1 µM amino-gattaca for **60 min** at room temperature, three PBS rinses, then block with **100 mM ethanolamine, pH 9.0, for 30 min**, three more PBS rinses.

Prerequisite: [PBASE in DMF: graphene coating](2026-11-04-pbase-dmf-graphene.md).

**The two batches:**

- **DNA:** a **10 µL** draw of the 26.9 µM stock into **259 µL** of 1× PBS = **269 µL at 1.00 µM = 15.57 ng/µL**.
- **Block:** ethanolamine **weighed, 8.6 mg** (= 0.141 mmol), with **330 µL ultrapure water + 1070 µL of 0.1 M HCl** added last and slowly, **≈ 1.41 mL** at 100 mM, pH calculated not measured.

## Reagents

All three oligos are from Invitrogen order **12091076** (PO 4500063351, cat. 10336022), 50 nt, PAGE purified, 46% GC.

| Reagent | Identity | Stock | Certificate |
| --- | --- | --- | --- |
| **amino-gattaca** | 5′ amine, 515766H05 | 26.9 nmol in 1 mL = **26.9 µM** (handwritten) | [COA](../reports/invitrogen/12091076/01-amino-gattaca.md) |
| fluor-tgtaatc | 5′ fluoroscein, 515677F09 | 100 µM (handwritten, no volume recorded — remeasure) | [COA](../reports/invitrogen/12091076/02-fluor-tgtaatc.md) |
| amino-gattaca-biotin | 5′ amine, 3′ biotin, 516489A01 | 20.3 nmol in 1 mL | [COA](../reports/invitrogen/12091076/03-amino-gattaca-biotin.md) |
| **ethanolamine** | Thermo **149582500**, 99%, MW 61.08, density 1.012 g/mL | 250 mL neat | product spec |

Use **amino-gattaca**. Its certificate gives 15,571.2 g/mol, so the stock is 26.9 × 15,571.2 / 1,000 = **418.87 ng/µL** and 1 µM is 15.5712 ng/µL.

The two amino oligos share a sequence but only **amino-gattaca** has a free 3′ hydroxyl; the 3′ biotin oligo cannot be extended by TdT and is not a template. `fluor-tgtaatc` is the release complement, not part of this step.

## 1. DNA working solution — 10 µL draw

| Component | Volume |
| --- | ---: |
| 26.9 µM amino-gattaca | **10.0 µL** |
| 1× PBS, pH 7.4 | **259 µL** |
| Total | **269 µL at 1.00 µM = 15.57 ng/µL** |

A 10 µL draw is 269 pmol (4.19 µg) and consumes 1% of the tube. Drawing 10 µL on a P20 rather than 1.86 µL on a P2 keeps volumetric error near 1% instead of several percent, and that error goes straight into surface density. For exactly 1× PBS from a water-based stock, use 10.0 µL stock + 26.9 µL 10× PBS + 232.1 µL ultrapure water.

PBS must be amine-free: no Tris, TE, TAE, glycine, or protein. Mix gently, spin down, use the same day, do not refreeze. 269 µL covers about 5 chips at 50 µL, less dead volume.

## 2. Deposit and incubate

1. Start from a clean, freshly PBASE-coated surface; unbound linker and residual DMF gone. Couple promptly and record the coating date, aqueous exposure and storage.
2. Apply the 269 µL to the exposed graphene, enough to cover the region without overflow. **Do not touch the graphene with the tip.**
3. **60 min at room temperature (~20–25 °C)**, covered humid chamber, chip level, surface continuously wet. Keep the water reservoir off the chip and never let the droplet dry.
4. Take the solution off from the edge and rinse **three times with fresh 1× PBS**, ~0.5–1 mL each, flowed over the surface — no direct jet.

A 50 µL deposit is 50 pmol (~779 ng) applied, not immobilized.

## 3. Block — 8.6 mg weighed, ≈ 1.41 mL, no pH meter

| Component | Amount |
| --- | ---: |
| Ethanolamine, 99% (Thermo 149582500) | **8.6 mg weighed** (= 8.5 µL) |
| Ultrapure water | **330 µL** |
| HCl **0.1 M** (Fisher SA54-1, N/10) | **1070 µL**, last and slowly |
| Final volume | **≈ 1.41 mL** |

1. **Weigh the ethanolamine rather than pipetting it.** 8.6 mg on the balance is far more accurate than ~8.5 µL of a viscous liquid, and the batch size then follows from the mass instead of being chosen: 0.141 mmol at 100 mM requires 1.41 mL.
2. Water in first, then the weighed ethanolamine, mix (strongly alkaline). Add the acid slowly last.
3. No probe, so the acid is calculated: pKa of the conjugate acid is 9.50, so at pH 9.0 the protonated fraction is 1/(1+10^(9.0−9.50)) = **76%**; 0.76 × 0.141 mmol = **0.107 mmol**, which is **1070 µL** of 0.1 M HCl. Expect true pH **8.9–9.1**.
4. The 0.141 mmol uses the nominal molecular weight. Correcting 8.6 mg for the 99% assay gives 0.139 mmol, so the real concentration is 99.0 mM rather than 100, and pH 8.98 rather than 9.00. Both are inside the noise of a calculated value; the recipe is unchanged either way.
5. 0.1 M rather than 1 M is deliberate: 1070 µL pipettes accurately, and ±20 µL moves pH only 0.05.
6. The acid is past its 12/2025 expiry and drifts weak, which lands the solution *above* pH 9.0. That is the safe direction, since blocking needs the unprotonated amine: 0.090 M gives pH 9.16, 0.080 M gives 9.31. Above ~9.5 NHS hydrolysis accelerates, so open a fresh ampoule then.
7. Cover the DNA-treated area with the block, **30 min at room temperature**, keep wet, then rinse **three times with fresh PBS**. ≈ 1.41 mL covers 7–28 applications at 50–200 µL.

Never add ethanolamine before or during DNA coupling: it consumes the NHS sites the coupling needs.

Ethanolamine stock: melts at 10.3 °C, so do not refrigerate; hygroscopic and absorbs CO₂ into carbamate, so keep capped and replace if turbid or aged; corrosive and combustible, so handle in a fume hood.

### Storing the prepared block

≈ 1.41 mL is 7 × 200 µL aliquots, more than one session, so it needs storing. Split it into 200 µL single-use aliquots, fill the tubes nearly full, cap tightly and freeze at **−20 °C**; thaw one per session, use it, discard the remainder rather than refreezing.

- **Cold and sealed matter here for a different reason than the acid.** CO₂ from air converts the free amine to carbamate (RNH₂ + CO₂ + H₂O → RNH₃⁺ + HCO₃⁻), which both removes the nucleophile that blocking needs and lowers the pH. That error runs in the **unsafe** direction, unlike the weak expired acid. A sealed, nearly-full tube is effectively protected, because the CO₂ available is only what sits in the headspace: 1 mL of headspace holds about 0.02 µmol, which is 0.05% of the 34 µmol of free amine in the batch.
- **Do not leave it at room temperature for days.** 100 mM ethanolamine in water is a growth medium for organisms that use ethanolamine as a carbon and nitrogen source, and pH 9 only slows them.
- **Fridge-only storage** is acceptable for a week or two if the tube is capped and nearly full, but frozen aliquots are better if the batch is going to sit.
- **The neat 250 mL stock takes the opposite rule:** room temperature, because it melts at 10.3 °C.
- Label each aliquot with the concentration, "pH 9.0 (calculated)" and the date. Warm to room temperature and inspect before use; discard if cloudy or if anything has precipitated.

## 4. Endpoint and record

For dry AFM, three ultrapure-water rinses then gentle N₂. For immediate liquid work, leave the chip in the next step's buffer. Record chip ID, stock concentration, volumes, deposit volume, incubation start/end, coverage, rinses and endpoint.

## Controls

- **PBASE + buffer only**, same incubation, block and rinses, separates NHS-site effects from DNA.
- **Bare graphene + DNA**, separates linker-mediated attachment from nonspecific adsorption.
- Hydrolysed NHS groups cannot be rescued with more DNA; if surface activity is uncertain, coat fresh.
- At 1 µM, coverage is dense enough that individual molecules are not resolved by AFM, so a topographic change does not prove covalent coupling. Ethanolamine caps residual NHS sites but does not prove attachment either.
- Blocking is not universal in this literature (Ping and Deng skip it; Xu and Huang use it); it is included here for the conservative reason.

## Why these numbers

60 min sits between Deng's 40 min and Xu's 1 h, at 1 µM as in both, in PBS as in Xu. The 100 mM ethanolamine at pH 9.0 for 30 min is Huang's recipe verbatim. The one variable no published protocol covers is a 50 µL static drop on a 1 cm² chip — all four flow or immerse — so mass transport is the open risk, and no 5–10 min coupling precedent exists. Parameter-by-parameter comparison against the four studies is in [the protocols index](README.md).

## References

1. Xu et al., *Nat Commun* **8**:14902 (2017). https://doi.org/10.1038/ncomms14902 — 1 µM 5′-amine DNA in 1× PBS, 1 h; 100 mM ethanolamine.
2. Deng et al., *Biosensors* **16**(2):125 (2026). https://doi.org/10.3390/bios16020125 — 1–2 µM amine-DNA in PBS pH 7.8, 40 min, dark; no block.
3. Ping et al., *ACS Nano* **10**:8700 (2016). https://doi.org/10.1021/acsnano.6b04110 — 1 µM amine-DNA in water, 3 h; no block.
4. Huang et al., *Nanoscale* **2**:1485 (2010). https://doi.org/10.1039/C0NR00142B — 0.1 M ethanolamine, pH 9.0, 30 min.
5. Thermo Scientific Chemicals, ethanolamine 99%, cat. 149582500 — MW, density, melting point.
6. Invitrogen certificates of analysis, order 12091076 (primers 515766H05, 515677F09, 516489A01).
