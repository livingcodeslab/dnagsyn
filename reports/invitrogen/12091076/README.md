# Invitrogen certificates of analysis — order 12091076

Transcriptions of three photographed **Invitrogen Custom Primers** certificates for Erik Garrison, UNIV OF TENNESSEE.

- Order date: **29-May-2024**
- Manufactured: **5/30/2024**
- Order number: **12091076**
- PO: **4500063351**
- Catalogue number: **10336022**

The individual reports preserve printed values and sequence notation, provide continuous 5′-to-3′ DNA sequences, and record handwritten notes separately. Numeric certificate values have not been recalculated or replaced.

“200 N” is retained verbatim as the synthesis scale. Tm values are retained without adding a temperature unit that is not printed on the sheets. Source photograph filenames and SHA-256 checksums are recorded in each report.

## Reports

| Line | Report | Primer number | Yield (nmol) | Yield (µg) | OD | Handwritten stock | Handwritten volume | Volume implied by the stock |
| --- | --- | --- | ---: | ---: | ---: | ---: | ---: | ---: |
| 1 | [amino-gattaca](01-amino-gattaca.md) | 515766H05 | 26.9 | 418.79 | 14.69 | 26.9 µM | 1 mL | 269 µL for 100 µM, then diluted to 1 mL |
| 2 | [fluor-tgtaatc](02-fluor-tgtaatc.md) | 515677F09 | 19.7 | 314.43 | 11.47 | 100 µM | not stated | **197.5 µL — the 100 µM stock volume** |
| 3 | [amino-gattaca-biotin](03-amino-gattaca-biotin.md) | 516489A01 | 20.3 | 327.82 | 11.09 | 20.3 µM | 1 mL | 203 µL for 100 µM, then diluted to 1 mL |

### The 100 µM stock is 19.752 nmol in 197.5 µL

All three oligos were intended at **100 µM**. Two of them were made at that concentration (269 µL and 203 µL) and then diluted to 1 mL, which is where the 26.9 µM and 20.3 µM annotations on lines 1 and 3 come from. Line 2 was left at 100 µM and only the concentration was written down. Its volume is not on the sheet, but it is determined by the sheet's own numbers:

```text
11.47 OD ÷ 580.7 OD/µmol = 19.752 nmol
19.752 nmol ÷ 100 µM      = 197.5 µL
```

So **the fluorescein complement is 19.752 nmol in 197.5 µL**, and that volume is a derivation from the printed quantity and the handwritten concentration rather than something written on the certificate. What remains unverified is the tube as it stands today: the solvent and reconstitution date were never recorded, and the oligo was manufactured 5/30/2024. Measure the volume and A₂₆₀/A₄₉₅ before use — the [hybridization protocol](../../../protocols/2026-11-11-fluor-tgtaatc-hybridization.md) carries the expected values.

All three certificates state:

- Primer length: **50**
- GC content: **46%**
- Purification: **PAGE**
- Tm (1M Na+): **101**
- Tm (50 mM Na+): **79**

## Transcription checks

The nucleotide sequences were visually checked against the supplied photographs. Each normalized sequence contains 50 A/C/G/T bases and 23 G/C bases (46% GC).

The two amino oligos have identical nucleotide sequences. The fluorescent oligo is their exact reverse complement. Both sequences match the designs in [`primer.md`](../../../primer.md).

The handwritten stock concentrations are historical annotations, not new concentration measurements. A reconstitution volume is recorded on only two of the three sheets; the third follows from its own printed quantity and annotated concentration (19.752 nmol ÷ 100 µM = 197.5 µL). No preparation date, solvent, or current stock status is given for any of them.

## Related protocols

[First attachment of amino-gattaca to PBASE graphene](../../../protocols/2026-11-05-amino-gattaca-pbase-graphene.md) includes stock dilution, a 60-minute DNA incubation, and ethanolamine blocking. **Run on 2026-11-05**; the chips were water-rinsed and imaged on 2026-11-11, and the AFM scans are not yet recorded.

[Hybridization of fluor-tgtaatc](../../../protocols/2026-11-11-fluor-tgtaatc-hybridization.md) uses the line-2 certificate's oligo as the fluorescein complement to the tethered template. It is a proposed protocol, not a record of an experiment already performed, and it includes the readings that confirm the 197.5 µL / 100 µM stock still holds today.

Transcribed and checked on **2026-11-05**.
