# fluor-tgtaatc — Certificate of Analysis

Transcribed from the supplied photograph `1000162344.jpg` on 2026-11-05. Printed certificate data and handwritten annotations are recorded separately.

## Printed certificate

**Invitrogen Custom Primers**  
**Certificate of Analysis**

| Field | Value as printed |
| --- | --- |
| Institution | UNIV OF TENNESSEE |
| Order Number | 12091076 |
| PO | 4500063351 |
| Order Date | 29-May-2024 |
| Line | 2 |
| Cat No. | 10336022 |
| Manufactured | 5/30/2024 |
| Primer Name | fluor-tgtaatc |
| Researcher | Erik Garrison |
| Primer Number | 515677F09 |
| Primer Length | 50 |
| Scale of Synthesis | 200 N |
| Molecular Weight (µg/µmole) | 15,916.5 |
| Millimolar Extinction Coeff. (OD/µmol) | 580.7 |
| µg per OD | 27.41 |
| nmoles per OD | 1.72 |
| Purity | PAGE |
| % GC Content | 46 |
| Tm (1M Na+) | 101 |
| Tm (50 mM Na+) | 79 |
| OD's | 11.47 |
| µg's | 314.43 |
| nmoles | 19.7 |
| Notes | [blank] |

### Sequence (5′ to 3′), as printed

```text
(DNA) - Fluoroscein - TGA GAC CAG AGA CGA GTT AAG ACC TAC ATC CTA AGC TTG CCT GTG TAA
TC
```

The spelling “Fluoroscein” is retained from the printed sequence label.

### Normalized DNA sequence (5′ to 3′)

Whitespace and modification labels are omitted:

```text
TGAGACCAGAGACGAGTTAAGACCTACATCCTAAGCTTGCCTGTGTAATC
```

Modification: **5′ “Fluoroscein”**, as printed and positioned according to the printed 5′-to-3′ sequence.

### Printed footer

Page 1 of 1 (printed 6/5/2024 at 8:27:40PM)

> For Research Use Only. Not for use in Diagnostic procedures.

> For information regarding COA calculations, primers use, and protocols, please go to www.invitrogen.com and click on Custom Primers.

Brand mark: invitrogen™.

## Handwritten annotation

```text
Stock @ 100 µM
```

Handwriting is normalized to standard unit typography.

| Item | Value |
| --- | --- |
| Reconstitution volume as written | **not stated** |
| Reconstitution volume, derived | **197.5 µL** (see below) |
| Stock concentration | **100 µM** |

The photograph does not state a reconstitution volume.

These are annotations on the photographed sheet; the preparation date, solvent, and current stock status are not recorded.

### Reconstitution volume: derived, not written

The sheet records the concentration but not the volume, and the volume follows from the printed quantity:

| Step | Value |
| --- | --- |
| Printed absorbance | **11.47 OD** |
| Printed extinction coefficient | **580.7 OD/µmol** (= ε₂₆₀ 5.807 × 10⁵ M⁻¹cm⁻¹) |
| Quantity | 11.47 ÷ 580.7 = **19.752 nmol** (printed as 19.7) |
| Annotated concentration | **100 µM** |
| Volume implied | 19.752 nmol ÷ 100 µM = **197.5 µL** |

**This explains the difference between the three tubes.** All three oligos were intended at **100 µM**. Line 1 (26.9 nmol) needed 269 µL for that and line 3 (20.3 nmol) needed 203 µL; both were then topped up to **1 mL**, which is what produced the 26.9 µM and 20.3 µM concentrations written on those two sheets — dilutions of 3.7× and 4.9×. Line 2 was left undiluted at 100 µM, and only the concentration was written beside it. So the annotation is correct as it stands, and the missing volume is missing because this is the one tube that was never diluted.

What the paperwork still cannot establish is whether ≈197.5 µL is what is in the tube today. The solvent (water or PBS) and the reconstitution date were never recorded, and the oligo was manufactured 5/30/2024, so evaporation or loss is possible. Measure the volume, then A₂₆₀ and A₄₉₅ as specified in the [hybridization protocol](../../../protocols/2026-11-11-fluor-tgtaatc-hybridization.md).

| Check | Expected if the tube holds 197.5 µL at 100 µM |
| --- | --- |
| Volume | 195–205 µL |
| A₂₆₀ of a 200-fold dilution | ≈ 0.29 |
| A₄₉₅/A₂₆₀ | ≈ 0.12 (one intact fluorescein per 50-mer) |
| Working solution | 5.0 µL into 495 µL 1× PBS = 1.00 µM |

## Source

- Original photograph filename: `1000162344.jpg`
- Photograph SHA-256: `b4b9e1477c294443063c0825d24fa176e4fc0bbb57ecebc5d16611a78111a955`
- Transcription date: 2026-11-05
