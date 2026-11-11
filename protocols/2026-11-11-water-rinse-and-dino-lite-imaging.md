# Water rinse and Dino-Lite imaging of the attached chips

**Date:** 2026-11-11  
**Status:** run on 2026-11-11. Rinse and imaging recorded in full; AFM was reported as run in the same session but no scans, images or parameters were supplied, so nothing is recorded for it here.  
**What we do:** re-rinse the blocked, DNA-bearing chips with **6 × 1 mL ultrapure water, 30–60 s each, in a 24-well plate**, then image the same area under **white** and **blue** excitation on a **Dino-Lite AM4117**.

This is a follow-up to [First attachment of amino-gattaca to PBASE-functionalized graphene](2026-11-05-amino-gattaca-pbase-graphene.md). The chips are PBASE + amino-gattaca, blocked with ethanolamine, **with no fluorophore on them yet**.

## Run record — 2026-11-11

| Step | As performed |
| --- | --- |
| Samples | PBASE + amino-gattaca chips, ethanolamine-blocked, no fluorophore |
| Purpose | re-rinse after the dried storage of 2026-11-05; establish the pre-hybridization imaging baseline |
| Rinse | **six rinses, 1 mL ultrapure water each, in a 24-well plate** |
| Rinse duration | **30–60 s per rinse** (incubation, not a flow-through wash) |
| Further rinses | additional rinses before imaging (number and volume not recorded) |
| Imaging | **Dino-Lite AM4117**, after the additional rinses |

### Images

| Image | Magnification | Illumination | What it is |
| --- | --- | --- | --- |
| **36** | low | **white** | reflected-light view of the area |
| **37** | low | **blue** | same area as 36, fluorescence channel |
| **38** | higher, at a corner | **white** | reflected-light view of the corner |
| **39** | higher, at a corner | **blue** | same area as 38, fluorescence channel |

Each excitation pair (36/37, 38/39) is the same field, which is what makes them usable as a before/after baseline rather than as two unrelated micrographs.

**The image files are not in this repository.** Images 36–39 are referred to by the numbers used at the microscope.

## What these four images can and cannot show

There is **no fluorophore on these chips**. Any signal in the blue-excitation frames (37, 39) is therefore **autofluorescence or reflected blue light, not fluorescein** — graphene, the underlying substrate, PBASE and residual organics all contribute.

That is exactly what makes them useful: they are the **zero point** for the [fluor-tgtaatc hybridization](2026-11-11-fluor-tgtaatc-hybridization.md). The readout then becomes a paired comparison on the same chip, same area, same magnification, same camera settings:

- **37 → after hybridization** at low magnification, and **39 → after hybridization** at the corner. A real hybridized layer must be brighter in the blue channel *relative to its own white-excitation partner* (36, 38) than it was before.
- Because 36/37 and 38/39 are the same fields, illumination unevenness across the chip cancels out. Comparing an image from one session against an image from a different session, or a fluorescence frame against a white frame, does not.

Practical cautions for the comparison to mean anything:

1. **Fix the camera settings.** Manual exposure, gain and white balance, identical for all four acquisitions and for the post-hybridization ones. If the scope auto-exposes, the white and blue frames are not comparable and neither are the before/after pairs.
2. **Record what "blue excitation" is on this instrument** — the LED wavelength and whether an emission filter was fitted. An AM4117 with no emission filter passes excitation light straight into the sensor, and bleed-through then swamps a dim fluorescein signal. Note it on the day, since it determines how far the images can be trusted.
3. **Check for photobleaching.** Capture the same blue-excitation field five times in a row. A genuine fluorophore fades under illumination; scattering, reflection and most autofluorescence do not. This is the cheapest specificity test available and it needs no extra reagents.
4. **Keep a bare-graphene area in frame** where the coating allows it, so that "signal" can be referred to an on-chip background.

## Why six rinses rather than three

The protocol for this chip called for three 500 µL water exchanges before dry AFM; here it was six exchanges of 1 mL. Nothing in the earlier reasoning forbids that:

- **Water cannot strip the DNA.** The attachment is a covalent amide to PBASE, so extra water exchanges only remove material that was not covalently held. Six exchanges of 1 mL (>10⁴-fold dilution of a 10–50 µL residual film) leave essentially no carried-over buffer or salt.
- **Longer, gentler exchanges are the safer direction for a delicate surface.** Six short soaks in a plate move less liquid across the graphene than six directed 1 mL streams would, and there is no jet to dislodge the layer.
- **The cost is the risk of drying between steps**, which is the thing to watch: a chip that goes dry between exchanges leaves salt and denatured DNA behind. Keeping every well full and transferring the chip wet is the requirement, not the rinse count.

What the rinse does *not* establish is that the layer survived the 2026-11-05 dry storage and the desiccator weekend. Only the paired white/blue images, and the AFM, speak to that. A uniform, low-contrast surface with no white crystalline patches is the expected appearance; patches would mean salt and more exchanges.

## AFM — pending

Dry AFM was the stated endpoint of the 2026-11-05 run, and it was reported as run in this session. Nothing about it is recorded here because no scans, images or parameters were supplied. When they are, record:

- instrument, mode (**tap** in air, not contact — contact mode drags soft nucleic acid layers) and probe;
- scan size, setpoint, scan rate, and whether the scan crossed **functionalized region and adjacent bare graphene** in one frame (an internal step beats a comparison against another chip);
- the numbers, not just images: height step across the boundary, and Rq/Ra on the coated region versus the bare region;
- which chip, and whether it is the same chip as images 36–39.

At 1 µM attachment the literature expectation is a uniform layer, roughly 1–2 nm for a 50-mer, with **no individually resolvable strands**. A topographic change of that size supports "a layer is present"; it does not prove covalent coupling, and a flat scan does not by itself prove the layer is absent.

## References

1. Ping et al., *ACS Nano* **10**:8700 (2016) — DI water rinse and nitrogen dry before imaging a ~1.2 nm height increase for a 22-mer; 1 µM layers are uniform, not countable.
2. Huang et al., *Nanoscale* **2**:1485 (2010) — DMF and DI water washes before imaging coverage.
3. Attachment run and rinse rationale: [2026-11-05 attachment protocol](2026-11-05-amino-gattaca-pbase-graphene.md).
