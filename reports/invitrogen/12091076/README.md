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
| 1 | [amino-gattaca](01-amino-gattaca.md) | 515766H05 | 26.9 | 418.79 | 14.69 | 26.9 µM | 1 mL | 1 mL → 26.9 µM (consistent) |
| 2 | [fluor-tgtaatc](02-fluor-tgtaatc.md) | 515677F09 | 19.7 | 314.43 | 11.47 | 100 µM | not stated | 197.5 µL → 100 µM; **1 mL → 19.75 µM** |
| 3 | [amino-gattaca-biotin](03-amino-gattaca-biotin.md) | 516489A01 | 20.3 | 327.82 | 11.09 | 20.3 µM | 1 mL | 1 mL → 20.3 µM (consistent) |

### Line 2 is the only tube with a volume that is not recorded — or consistent

The two amino oligos were resuspended in **1 mL** and annotated with the concentration that gives (26.9 nmol/mL = 26.9 µM; 20.3 nmol/mL = 20.3 µM). The 1 mL was the volume chosen first, before the yield was accounted for, so it is a starting volume rather than a dilution step.

Line 2 breaks that pattern. Its printed quantity and its handwritten concentration imply a volume:

```text
11.47 OD ÷ 580.7 OD/µmol = 19.752 nmol
19.752 nmol ÷ 100 µM      = 197.5 µL
```

but the same **1 mL** that the other two tubes received would make it **19.75 µM**, five-fold below the annotation. So "100 µM in 197.5 µL" is a derivation from the annotation, not a record: either the tube holds ≈197.5 µL and the annotation is right, or it holds ~1 mL like its siblings and the annotation is wrong. **This is settled by measuring the volume, and confirmed independently by A₂₆₀** — see the [line-2 report](02-fluor-tgtaatc.md) and the [hybridization protocol](../../../protocols/2026-11-11-fluor-tgtaatc-hybridization.md), which carries both readings and both working-solution draws (5.0 µL versus 25.3 µL).

All three certificates state:

- Primer length: **50**
- GC content: **46%**
- Purification: **PAGE**
- Tm (1M Na+): **101**
- Tm (50 mM Na+): **79**

## Transcription checks

The nucleotide sequences were visually checked against the supplied photographs. Each normalized sequence contains 50 A/C/G/T bases and 23 G/C bases (46% GC).

The two amino oligos have identical nucleotide sequences. The fluorescent oligo is their exact reverse complement. Both sequences match the designs in [`primer.md`](../../../primer.md).

The handwritten stock concentrations are historical annotations, not new concentration measurements. A reconstitution volume is recorded on only two of the three sheets, and it is the third — the fluorescein tube, the one the hybridization depends on — that does not have one. Its 100 µM annotation implies 197.5 µL; the 1 mL used for the other two would give 19.75 µM. No preparation date, solvent, or current stock status is given for any of them.

## Related protocols

[First attachment of amino-gattaca to PBASE graphene](../../../protocols/2026-11-05-amino-gattaca-pbase-graphene.md) includes stock dilution, a 60-minute DNA incubation, and ethanolamine blocking. **Run on 2026-11-05**; the chips were water-rinsed and imaged on 2026-11-11, and the AFM scans are not yet recorded.

[Hybridization of fluor-tgtaatc](../../../protocols/2026-11-11-fluor-tgtaatc-hybridization.md) uses the line-2 certificate's oligo as the fluorescein complement to the tethered template. It is a proposed protocol, not a record of an experiment already performed, and it includes the readings that settle this tube's 100 µM annotation.

Transcribed and checked on **2026-11-05**.
