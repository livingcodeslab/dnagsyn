# First attachment of amino-gattaca to PBASE-functionalized graphene

**Date:** 2026-11-05  
**Status:** Proposed starting protocol; not yet experimentally validated on this chip.  
**Target:** 1 µM amino-gattaca (15.57 ng/µL) for **60 min** at room temperature, rinse, then block with **100 mM ethanolamine, pH 9.0, for 30 min**.

Prerequisite: [PBASE in DMF: graphene coating](2026-11-04-pbase-dmf-graphene.md).

## Reagents and stock data

All three oligos are from Invitrogen order **12091076** (PO 4500063351, cat. 10336022), 50 nt, PAGE purified, 46% GC.

| Reagent | Identity | Stock as recorded | Certificate |
| --- | --- | --- | --- |
| **amino-gattaca** | 5′ amine; primer 515766H05 | 26.9 nmol in 1 mL = **26.9 µM** (handwritten) | [COA](../reports/invitrogen/12091076/01-amino-gattaca.md) |
| fluor-tgtaatc | 5′ fluoroscein; primer 515677F09 | 19.7 nmol; **100 µM** (handwritten), reconstitution volume not stated | [COA](../reports/invitrogen/12091076/02-fluor-tgtaatc.md) |
| amino-gattaca-biotin | 5′ amine, 3′ biotin; primer 516489A01 | 20.3 nmol in 1 mL = **20.3 µM** (handwritten) | [COA](../reports/invitrogen/12091076/03-amino-gattaca-biotin.md) |
| **ethanolamine** | Thermo Scientific **149582500**, 99%, CAS 141-43-5, MW 61.08 g/mol, density 1.012 g/mL | 250 mL, neat liquid | product specification |

Use **amino-gattaca** (515766H05) here. Its certificate gives molecular weight **15,571.2 g/mol** and 26.9 nmol in 1 mL.

- Nominal stock mass concentration: 26.9 × 15,571.2 / 1,000 = **418.87 ng/µL**.
- Target mass concentration: 1 × 15,571.2 / 1,000 = **15.5712 ng/µL**.
- Required dilution: **26.9-fold** (1 part stock + 25.9 parts diluent).

The certificate's total mass is 418.79 µg; the 0.08 µg difference from 418.87 µg assumes only rounding of the reported nmol quantity. These calculations assume the handwritten stock label remains correct and that there has been no later dilution, evaporation, or material loss.

The two amino oligos carry the same sequence, but only **amino-gattaca** (no 3′ biotin) has a free 3′ hydroxyl and can be extended by TdT. Treat amino-gattaca-biotin as non-extendable unless its vendor specification says otherwise.

## Working DNA solution

Use **1× PBS, pH 7.4**, without Tris, glycine, ethanolamine, protein, or other primary-amine additives.

Confirm the stock solvent before use. Water or an amine-free phosphate buffer is suitable. If the stock contains Tris (including TE or TAE), exchange it into an amine-free medium and remeasure; dilution does not remove the competing amine.

| Final volume | 26.9 µM stock | 1× PBS added | Final DNA |
| ---: | ---: | ---: | ---: |
| 50 µL | 1.86 µL | 48.14 µL | ~1.00 µM = ~15.6 ng/µL |
| 53.8 µL (convenient batch) | 2.00 µL | 51.80 µL | 1.00 µM = 15.57 ng/µL |
| 100 µL | 3.72 µL | 96.28 µL | ~1.00 µM = ~15.6 ng/µL |
| 200 µL | 7.43 µL | 192.57 µL | ~1.00 µM = ~15.6 ng/µL |

With a DNA stock in water these mixtures are approximately **0.963× PBS**. For exactly 1× in 50 µL, from a water-based stock and 10× PBS: **1.86 µL DNA + 5.00 µL 10× PBS + 43.14 µL water**.

Thaw the aliquot, mix gently, spin down briefly, and prepare the dilution immediately before deposition. Keep the remaining stock separate.

### Preparing from a 10 µL stock draw

Drawing 10 µL rather than 1.86 µL is the recommended route: the volumetric error of a P2 pipette at ~2 µL is several percent, while 10 µL on a P20 is about 1%, and that error propagates undiluted into the surface density. It also makes the batch large enough to serve several chips.

**What a 10 µL draw contains:**

- 10 µL × 26.9 µM = **269 pmol** (0.269 nmol)
- 10 × 418.87 ng/µL = **4.19 µg** of the 50-mer
- **1.0%** of the 1 mL stock tube

**What is required to reach 1 µM:**

| Component | Volume |
| --- | ---: |
| 26.9 µM amino-gattaca stock | **10.0 µL** |
| 1× PBS, pH 7.4 | **259 µL** |
| **Total** | **269 µL at 1.00 µM = 15.57 ng/µL** |

The 4.19 µg drawn is spread over 269 µL, so the mass concentration in the tube is 4188.7 / 269 = **15.57 ng/µL**, identical to the 1 µM target (1 µM × 15,571.2 / 1,000 = 15.5712 ng/µL) because mass is conserved through the dilution.

For exactly 1× PBS from a water-based stock, substitute 10× PBS for part of the diluent: **10.0 µL stock + 26.9 µL 10× PBS + 232.1 µL ultrapure water = 269 µL**.

A 270 µL total (10 µL stock + 260 µL PBS) gives 0.996 µM, 0.4% low, which is roundable at the pipette in practice.

**Consumables:** a low-bind 1.5 mL tube, a P20 for the stock draw, and a P200 or P1000 for the 259 µL diluent. Mix by gentle pipetting or inversion, spin down, and use the same day; do not refreeze the dilution.

**Capacity:** 269 µL covers about **5 chips at 50 µL** or **2 chips at 100–200 µL**, less ~10 µL of dead volume and pipetting loss. Prepare the batch from the number of chips actually planned.

The same arithmetic scales to any draw: final volume (µL) = draw (µL) × 26.9, so a 5 µL draw needs 134.5 µL total (129.5 µL diluent) and a 20 µL draw needs 538 µL total (518 µL diluent).

## Deposition, rinse and block

1. **Start from a clean, well-rinsed PBASE-functionalized surface.** This protocol begins after PBASE deposition and removal of unbound linker and residual organic solvent; see [PBASE in DMF: graphene coating](2026-11-04-pbase-dmf-graphene.md). Couple promptly after surface preparation. Record the coating date, aqueous exposure and storage conditions.

2. **Apply the 1 µM DNA solution.** Use 50 µL only if it covers the intended region. For a full ~1 cm² chip, prepare 100–200 µL and keep the area covered without overflow. Coverage sets the volume. Do not touch or scrape the graphene with the tip.

3. **Incubate 60 min at room temperature (~20–25 °C)** in a covered humid chamber, chip level, surface continuously wet. Keep the chamber's water reservoir separate from the chip. Do not let the droplet dry onto the surface.

4. **Remove unbound DNA.** Take the solution off from the edge and rinse with three fresh portions of 1× PBS, ~0.5–1 mL each for a 1 cm² chip, adjusted to the holder. Flow the rinse over the surface; do not jet it directly at the graphene.

5. **Block only after the DNA rinse.** Cover the same region with **100 mM ethanolamine, pH 9.0** (1 mL recipe below: 234 µL water + 6.1 µL ethanolamine + 760 µL 0.1 M HCl, no pH meter required), incubate **30 min at room temperature**, keep wet, then rinse gently with three fresh PBS portions. Never add ethanolamine before or during DNA coupling: it consumes the NHS sites that the coupling needs.

6. **Choose the endpoint.** For dry AFM, follow with three fresh ultrapure-water rinses to remove PBS salts and dry gently with clean nitrogen. For immediate liquid work, leave the chip in the buffer required by the next step. Keep chip rinsing separate from handling the AFM cantilever.

7. **Record** chip ID, stock solvent and nominal concentration, preparation volumes, deposited volume, incubation start/end, coverage, rinse conditions, and the measurement endpoint.

A 50 µL deposition applies **50 pmol (~779 ng)** of DNA; that is the amount applied, not the amount immobilized.

## Solutions

### 100 mM ethanolamine, pH 9.0 — 1 mL batch, no pH meter (the recipe we mix)

Reagent: Thermo Scientific **149582500**, ethanolamine 99%, neat free base (not a salt, not a pre-made solution).

| Component | Amount |
| --- | ---: |
| Ultrapure water | **234 µL** |
| Ethanolamine, 99% (Thermo 149582500) | **6.1 µL** (6.2 mg) |
| HCl **0.1 M** (Fisher SA54-1, N/10) | **760 µL**, added last and slowly |
| Total | ≈ 1.00 mL |

**Why the acid volume is calculated rather than measured.** With no pH probe available, the acid is set from the buffer equation. Ethanolamine's conjugate acid has pKa 9.50, so at pH 9.0 the protonated fraction is 1/(1+10^(9.0−9.50)) = **76%**. For the 0.100 mmol of amine in 1 mL that is **0.076 mmol HCl**, i.e. 760 µL of 0.1 M. Adding the acid slowly to the diluted amine, rather than amine to acid, keeps the local pH from spiking.

Expected true pH is therefore about **8.9–9.1**, limited by activity effects the calculation ignores.

**0.1 M HCl rather than 1 M** is deliberate: 760 µL on a P1000 is a far more accurate delivery than 76 µL on a P100, and the acid volume error has very little effect on the achieved pH, because pH is logarithmic:

| Acid delivered (at 0.100 M) | Resulting pH |
| ---: | ---: |
| 740 µL | 9.05 |
| 760 µL | 9.01 |
| 780 µL | 8.96 |

**The HCl is past its certified expiry (12/2025).** HCl drifts weak with age, which means less acid delivered than assumed, which lands the solution *above* pH 9.0 — the safe direction, because blocking needs the unprotonated amine and a lower pH would leave less of it. The sensitivity is mild:

| If the acid is actually | Achieved pH |
| ---: | ---: |
| 0.095 M | 9.09 |
| 0.090 M | 9.17 |
| 0.080 M | 9.31 |
| 0.070 M | 9.45 |

Even a badly degraded 0.05 M bottle would give pH 9.7, still workable for a 30 min block at room temperature, though NHS hydrolysis accelerates above pH 9.5 and that is the point where a fresh ampoule is worth opening. A 5 µL aliquot on pH paper covering the 8.5–9.5 range is a cheap cross-check if any is on hand.

Mix fresh on the day, use the same day, and apply enough to cover the DNA-treated area, typically 50–200 µL. **Block 30 min at room temperature**, keeping the surface wet.

### 100 mM ethanolamine at other volumes, or with a pH meter

| Final volume | Ethanolamine (99%, by weight) | Approximate volume | From a 1 M stock |
| ---: | ---: | ---: | ---: |
| 5 mL | 30.9 mg | 30.5 µL | 0.50 mL |
| 10 mL | 61.7 mg | 61.0 µL | 1.00 mL |
| 25 mL | 154 mg | 152 µL | 2.50 mL |

1. **Weigh rather than pipette** where the balance allows (~0.1 mg precision): 61.7 mg of the 99% liquid is 1.0 mmol of amine. It is viscous and ~61 µL is an awkward pipetting volume, so weighing is more accurate.
2. Add to about 8 mL (of 10 mL) ultrapure water and mix. The unadjusted solution is strongly alkaline.
3. Adjust to **pH 9.0 with 1 M HCl**, then bring to the final volume with water and **recheck the pH**. Use 1× PBS as the diluent only if a phosphate background is wanted; PBS does not guarantee the final pH on its own.
4. Prepare fresh on the day of use and apply enough to cover the DNA-treated area, typically 50–200 µL.

**Ethanolamine stock handling (250 mL bottle).**

- Neat ethanolamine melts at **10.3 °C**, so it solidifies in a fridge or cold room. Store at room temperature and confirm it is fully liquid and mixed before dispensing.
- It is hygroscopic and absorbs CO₂ to form carbamate, which is unreactive toward NHS esters. Keep it tightly capped, dispense quickly, purge headspace with nitrogen or argon if available, and replace stock that is turbid, discoloured, or long past its opened date.
- It is a combustible, corrosive liquid (flash point ~92 °C). Handle in a fume hood with gloves and eye protection; treat HCl likewise.
- One 250 mL bottle makes roughly **4,000 × 10 mL** batches of blocking solution, so do not accumulate bottles.

### 1× PBS, pH 7.4

Amine-free. Do not substitute TE, TAE, or any Tris-containing buffer at any point before blocking.

## Justifying the 60-minute DNA step

| Published coupling condition | Relevance |
| --- | --- |
| 1 µM 5′-amine DNA in 1× PBS, 1 h under flow; Xu et al. (2017) | Direct precedent for 60 min, then 100 mM ethanolamine |
| 1–2 µM amine-DNA in PBS pH 7.8, 40 min; Biosensors (2026) | Reported sub-hour immobilization |
| 1 µM aqueous amine-DNA, 3 h; Ping et al. (2016) | Longer reference condition, not a demonstrated minimum |

Use **60 min** for the first run. A static drop on a 1 cm² chip has different mass transport from Xu et al.'s flowing microchannel, so equivalent coverage is not established, and the 40-minute report used pH 7.8 rather than 7.4. No comparable **5–10-minute** coupling precedent was identified; that would be an exploratory time point. Short hybridization or short PBASE coating times are not evidence for equally short coupling.

## Controls and interpretation

- If a second chip is available, run a **PBASE + buffer-only control** through the same incubation, blocking and rinses.
- A **bare-graphene + DNA control** would separate linker-mediated attachment from nonspecific adsorption.
- Exposure to water or humidity during storage hydrolyses reactive NHS groups. More DNA will not restore them; start from a freshly prepared PBASE surface if activity is uncertain. Do not read a failed deposition as "the DNA concentration was too low".
- At 1 µM, published work gives dense coverage in which **individual molecules are not resolved by AFM**. A topographic change alone does not prove covalent coupling.
- Ethanolamine caps residual NHS sites. It does not remove all nonspecific adsorption to exposed graphene and does not by itself prove covalent DNA attachment. Blocking is also not universal in the DNA-GFET literature: Ping et al. (2016) and Deng et al. (2026) attach amine-DNA with no blocking step at all. It is included here because Xu et al. (2017) and Huang et al. (2010) block with 100 mM / 0.1 M ethanolamine, and capping unreacted NHS esters is the conservative choice when the surface will later be in contact with protein or enzyme.

## Evidence

1. **Xu et al., Nature Communications (2017), 8:14902.** https://doi.org/10.1038/ncomms14902 — 1 µM 5′-amine DNA in 1× PBS flowed for 1 h, PBS wash, then 100 mM ethanolamine (blocking time and pH not specified).
2. **Suspended graphene FET for label-free detection of miR-21, Biosensors (2026), 16(2):125.** https://www.mdpi.com/2079-6374/16/2/125 — §2.2, 1–2 µM amine-DNA in PBS pH 7.8 for 40 min in the dark.
3. **Ping et al., ACS Nano (2016), 10:8700–8704.** https://doi.org/10.1021/acsnano.6b04110 — 1 µM aqueous 5′-amine DNA (22-, 40-, 60-mer), 3 h, DI rinse; coverage too dense for single-molecule AFM.
4. **Electrochemically-gated graphene microwave waveguides, Nanoscale (2023), 15:15304–15317.** https://doi.org/10.1039/D3NR01239E — 0.1 M ethanolamine for 30 min in 0.01× PBS after DNA immobilization.
5. **Nanoelectronic biosensors based on CVD grown graphene, Nanoscale (2010).** https://doi.org/10.1039/C0NR00142B — graphene/PBASE blocking with 0.1 M ethanolamine, pH 9.0, 30 min.
6. **Thermo Fisher, Amine-Reactive Crosslinker Chemistry.** https://www.thermofisher.com/us/en/home/life-science/protein-biology/protein-biology-learning-center/protein-biology-resource-library/pierce-protein-methods/amine-reactive-crosslinker-chemistry.html — amine-free buffers, competition from NHS hydrolysis.
7. **Thermo Scientific Chemicals, Ethanolamine 99%, cat. 149582500.** https://www.thermofisher.com/order/catalog/product/149582500 — CAS 141-43-5, MW 61.08 g/mol, density 1.012 g/mL, melting point 10.3 °C.
8. **Invitrogen certificates of analysis**, order 12091076, primers 515766H05, 515677F09, 516489A01, manufactured 2024-05-30, with handwritten stock notes. Stock buffers and preparation dates are not recorded.

The **1 µM / PBS pH 7.4 / 60 min / room-temperature** static-drop DNA step and the **100 mM ethanolamine / pH 9.0 / 30 min** block combine distinct precedents. Drop and rinse volumes and rinse counts are practical adaptations for this chip, not a verbatim reproduction of a single published protocol.
