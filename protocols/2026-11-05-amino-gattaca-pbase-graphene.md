# First attachment of amino-gattaca to PBASE-functionalized graphene

**Date:** 2026-11-05  
**Status:** Proposed starting protocol; not yet experimentally validated on this chip.  
**Target:** 1 µM amino-gattaca = 15.57 ng/µL; **60 min** at room temperature, then rinse and block with **100 mM ethanolamine, pH 9.0, for 30 min**.

## Reagent and concentration calculation

Use **amino-gattaca**, primer **515766H05**, order **12091076**: a 50-base DNA oligonucleotide with a 5′ amine.

Its [certificate transcription](../reports/invitrogen/12091076/01-amino-gattaca.md) reports molecular weight **15,571.2 g/mol** (numerically equivalent to the printed 15,571.2 µg/µmole) and **26.9 nmol** supplied. The handwritten note records **1 mL** and **26.9 µM** stock.

- Nominal stock mass concentration: 26.9 × 15,571.2 / 1,000 = **418.87 ng/µL**.
- Target mass concentration: 1 × 15,571.2 / 1,000 = **15.5712 ng/µL**.
- Required dilution: **26.9-fold** (1 part stock + 25.9 parts diluent).

The certificate's total mass is 418.79 µg; its small difference from the calculated 418.87 µg in 1 mL reflects rounding of the reported nmol quantity.

These calculations assume the handwritten stock label remains correct and there has been no subsequent dilution, evaporation, or material loss.

## Prepare the working solution

Use **1× PBS, pH 7.4**, without Tris, glycine, ethanolamine, protein, or other primary-amine additives.

Confirm the DNA stock solvent before use: water or an amine-free phosphate buffer is suitable. If the stock contains Tris (including TE or TAE), exchange it into an amine-free medium and remeasure concentration; do not assume dilution removes the competing amine.

| Final volume | 26.9 µM DNA stock | 1× PBS added | Final DNA |
| ---: | ---: | ---: | ---: |
| 50 µL | 1.86 µL | 48.14 µL | ~1.00 µM = ~15.6 ng/µL |
| 53.8 µL, convenient small batch | 2.00 µL | 51.80 µL | 1.00 µM = 15.57 ng/µL |
| 100 µL | 3.72 µL | 96.28 µL | ~1.00 µM = ~15.6 ng/µL |
| 200 µL | 7.43 µL | 192.57 µL | ~1.00 µM = ~15.6 ng/µL |

If the DNA stock is in water, these mixtures contain approximately **0.963× PBS**, rather than exactly 1× PBS.

For exactly 1× PBS using a water-based DNA stock and 10× PBS, a 50 µL preparation is:

- **1.86 µL DNA stock**
- **5.00 µL 10× PBS**
- **43.14 µL ultrapure water**

Thaw the DNA aliquot, mix gently, and briefly spin down before pipetting. Prepare the working dilution immediately before deposition. Keep the remaining stock separate from the working solution.

## Deposition and rinse

1. **Use a clean, well-rinsed PBASE-functionalized graphene surface.** This protocol begins after PBASE deposition and removal of unbound linker and residual organic solvent. Prefer coupling promptly after surface preparation. Record the coating date, aqueous exposure, and storage conditions.

2. **Apply the 1 µM DNA solution.** Use 50 µL only if it covers the intended region. For a full approximately 1 cm² chip, prepare 100–200 µL and use enough to maintain coverage without overflow. Coverage determines the volume required. Do not touch or scrape the graphene with the tip.

3. **Incubate for 60 min at room temperature (approximately 20–25 °C)** in a covered humid chamber, with the chip level and the surface continuously wet. Keep the chamber's water reservoir separate from the chip. Do not allow the DNA droplet to dry onto the surface.

4. **Remove unbound DNA.** Gently remove the solution from the edge and rinse with three fresh portions of 1× PBS. For a bare 1 cm² chip, approximately 0.5–1 mL per rinse is a practical starting volume, adjusted to the holder. Flow the rinse over the surface without directing a strong jet at it.

5. **Block after the DNA rinse.** Cover the same region with **100 mM ethanolamine, pH 9.0**, and incubate **30 min at room temperature**, keeping the surface wet. Rinse gently with three fresh PBS portions. Do not add ethanolamine before or during DNA coupling: it consumes NHS sites and stops further attachment through those sites.

6. **Choose the endpoint.** For dry AFM, follow with three fresh ultrapure-water rinses to remove PBS salts, then dry gently with clean nitrogen. For immediate liquid work, leave the chip in the buffer appropriate to that next step. Keep chip rinsing separate from handling the AFM cantilever.

7. **Record** chip ID, stock solvent and nominal concentration, preparation volumes, deposited volume, incubation start/end, surface coverage, rinse conditions, and imaging or measurement endpoint.

A 50 µL deposition contains **50 pmol (~779 ng)** DNA; this is the amount applied, not the amount immobilized.

## Prepare ethanolamine blocking solution

Check whether the bottle contains neat ethanolamine, a known-molarity solution, or an ethanolamine salt. Do not use the neat-liquid recipe for a solution or salt.

For **10 mL of 100 mM ethanolamine, pH 9.0**:

- **From neat free-base ethanolamine:** use **61.08 mg**, approximately **60.4 µL** for 100% material at density 1.012 g/mL. Correct for actual assay if needed. Add to about 8 mL ultrapure water, mix, adjust to **pH 9.0 with HCl**, then bring to **10.00 mL final volume** with water and recheck pH.
- **From a known 1 M solution:** use **1.00 mL**, dilute to less than 10 mL, adjust to pH 9.0 as needed, then bring to **10.00 mL final volume**. For another stock strength use C1V1 = C2V2.

Unadjusted ethanolamine in water is alkaline; PBS does not guarantee the final pH. Use normal corrosive-reagent handling for concentrated ethanolamine and HCl.

Apply enough blocking solution to cover the DNA-treated area, for example 50–200 µL.

## How short can the DNA step be?

| Published DNA coupling condition | Relevance |
| --- | --- |
| 1 µM 5′-amine DNA in 1× PBS, 1 h under flow; Xu et al. (2017) | Direct precedent for 60 min, then 100 mM ethanolamine |
| 1–2 µM amine-DNA in PBS pH 7.8, 40 min; Biosensors (2026) | Reported sub-hour immobilization |
| 1 µM aqueous amine-DNA, 3 h; Ping et al. (2016) | Longer reference condition, not a demonstrated minimum |

Use **60 min** for this first shortened run.

A static drop on a 1 cm² chip has different mass transport from Xu et al.'s flowing microchannel; equivalent coverage is not established. The 40-minute report uses pH 7.8, not the pH 7.4 chosen here.

No directly comparable **5–10-minute** DNA-coupling precedent was identified in this search; it would be an exploratory time point. Short hybridization or PBASE coating times are not evidence for equally short DNA coupling.

## Controls and interpretation

If a second chip is available, process a **PBASE + buffer-only control** with the same incubation, ethanolamine blocking, and rinses. A bare-graphene + DNA control would further distinguish linker-mediated attachment from nonspecific DNA adsorption.

The 5′ amine is intended to react with PBASE's NHS ester to form an amide bond. A surface exposed to water or humidity during storage may have lost reactive NHS groups by hydrolysis. More DNA will not restore those groups; include a freshly prepared PBASE surface if activity of the existing chip is uncertain. Do not interpret a failed deposition as evidence that the DNA concentration was too low.

This starting concentration is intended to establish surface functionalization. Published work at 1 µM produced dense DNA coverage; individual molecules were not resolved by AFM. A topographic change alone does not prove covalent coupling.

Ethanolamine caps residual NHS sites; it does not eliminate all nonspecific adsorption to exposed graphene or prove covalent DNA attachment.

## Evidence and adaptations

1. **Xu et al., Nature Communications (2017), 8:14902.**  
   https://doi.org/10.1038/ncomms14902  
   Methods: **1 µM 5′-amine DNA in 1× PBS flowed for 1 h**, followed by PBS washing and **100 mM ethanolamine**. Blocking time and pH are not specified.

2. **A Suspended Graphene Field-Effect Transistor for Ultra-Sensitive and Label-Free Detection of Cancer Biomarker miR-21, Biosensors (2026), 16(2):125.**  
   https://www.mdpi.com/2079-6374/16/2/125  
   Section 2.2 reports **1–2 µM amine-DNA in PBS pH 7.8 for 40 min** in the dark.

3. **Ping et al., ACS Nano (2016), 10:8700–8704.**  
   https://doi.org/10.1021/acsnano.6b04110  
   **1 µM aqueous 5′-amine DNA (22-, 40-, or 60-mer), 3 h**, then DI-water rinse. Dense coverage prevented individual-molecule resolution by AFM.

4. **Electrochemically-gated graphene broadband microwave waveguides for ultrasensitive biosensing, Nanoscale (2023), 15:15304–15317.**  
   https://doi.org/10.1039/D3NR01239E  
   **0.1 M ethanolamine for 30 min**, in 0.01× PBS, after DNA immobilization.

5. **Nanoelectronic biosensors based on CVD grown graphene, Nanoscale (2010).**  
   https://doi.org/10.1039/C0NR00142B  
   Graphene/PBASE blocking precedent: **0.1 M ethanolamine, pH 9.0, for 30 min** in an enzyme-functionalization system.

6. **Thermo Fisher, Amine-Reactive Crosslinker Chemistry.**  
   https://www.thermofisher.com/us/en/home/life-science/protein-biology/protein-biology-learning-center/protein-biology-resource-library/pierce-protein-methods/amine-reactive-crosslinker-chemistry.html  
   Supports amine-free buffers and explains competition from NHS hydrolysis.

7. **Sigma-Aldrich ethanolamine data, E9508.**  
   https://www.sigmaaldrich.com/US/en/product/sial/e9508  
   Free-base molecular weight **61.08 g/mol**; density **1.012 g/mL at 25 °C**.

8. **User-supplied Invitrogen certificate**, primer 515766H05, manufactured 2024-05-30, and handwritten stock note. Stock buffer and preparation date are not recorded.

The **1 µM / PBS pH 7.4 / 60 min / room-temperature** static-drop DNA step and **100 mM ethanolamine / pH 9.0 / 30 min** block combine distinct precedents. Drop/rinse volumes and rinse counts are practical adaptations for this chip, not a verbatim reproduction of a single published protocol.
