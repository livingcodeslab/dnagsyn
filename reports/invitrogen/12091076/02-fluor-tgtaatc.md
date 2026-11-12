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

**What the three tubes actually record.** The two amino oligos were resuspended in **1 mL** and annotated with the concentration that gives — 26.9 nmol/mL = **26.9 µM** and 20.3 nmol/mL = **20.3 µM**. The 1 mL was volume chosen first, before the yield was accounted for, and the concentration then followed from it; it is not a dilution step and there is no evidence of a deliberate 100 µM intermediate. Line 2 is the outlier: it carries **100 µM and no volume**, and 100 µM is not what 1 mL would give — the same 1 mL in this tube is **19.752 µM**.

So there are two accounts, and they are mutually exclusive:

| Account | Tube volume | Concentration | Draw for a 1 µM working solution |
| --- | ---: | ---: | ---: |
| **Annotated 100 µM is right** | **197.5 µL** | 100 µM | 5.0 µL into 495 µL |
| **Resuspended in 1 mL like the others** | ~1 mL | **19.75 µM** | **25.3 µL** into 475 µL |

Each is one measurement away: the volume in the tube decides it, and A₂₆₀ confirms it independently. A 200-fold dilution reads ≈ 0.29 at 100 µM or ≈ 0.057 at 19.75 µM. Both are still in excess of the surface sites (30–60× versus 6–12×), so hybridization is not jeopardized either way — but the draw volume differs five-fold, so the stock must be settled before the complement is aliquoted.

The solvent (water or PBS) and the reconstitution date were never recorded either, and the oligo was manufactured 5/30/2024, so evaporation cannot be excluded on top of the two accounts above.

| Check | If 197.5 µL at 100 µM | If ~1 mL at 19.75 µM |
| --- | --- | --- |
| Volume | 195–205 µL | ~1 mL |
| A₂₆₀ of a 200-fold dilution | ≈ 0.29 | ≈ 0.057 |
| A₄₉₅/A₂₆₀ | ≈ 0.12 | ≈ 0.12 (one intact fluorescein per 50-mer either way) |
| Working solution for 1 µM | 5.0 µL into 495 µL | 25.3 µL into 475 µL |

Record the reading here when it is taken, and see the [hybridization protocol](../../../protocols/2026-11-11-fluor-tgtaatc-hybridization.md) for the dilution procedure.

## Source

- Original photograph filename: `1000162344.jpg`
- Photograph SHA-256: `b4b9e1477c294443063c0825d24fa176e4fc0bbb57ecebc5d16611a78111a955`
- Transcription date: 2026-11-05
