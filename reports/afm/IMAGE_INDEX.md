# Image index — AFM scans

_Repo home: `reports/afm/IMAGE_INDEX.md` in livingcodeslab/dnagsyn. Dino-Lite scope frames have their own index in `reports/light-microscopy/`._

## 2026-11-10 — graphene_pbase_dna (separate Drive folder)

AFM scans live in their own lab Drive folder (not the DinoCapture folder):
https://drive.google.com/drive/folders/1Uz2bAVWRPzi1JaeH8qIHVXD_MhhLn4yg

One scan of a sample named **graphene_pbase_dna**, run on Nov 10, 2026, after that morning's
rinse and imaging. Six Gwyddion (.gsf) channel files, 1024 × 1024 px, 3.2883 µm × 3.2883 µm
scan area. In this instrument's export (ICSPI nGauge), the **offset channel is the topography
channel**; its values run 1.93–3.07 µm in the forward scan and 1.93–3.05 µm in the
reverse scan.

| File | Name | Size | Link |
|---|---|---|---|
| graphene_pbase_dna phase forward 1794346366346.gsf | AFM phase channel, forward scan (149.6–152.9°) | 4.19 MB | [view](https://drive.google.com/file/d/18LWkHNFTMg73ZEN8t4ggFrIybnyKTfqZ/view?usp=drivesdk) |
| graphene_pbase_dna phase reverse 1794346366346.gsf | AFM phase channel, reverse scan (149.7–152.8°) | 4.19 MB | [view](https://drive.google.com/file/d/1LdtYricvrpMsLBMUzzdG7OL-CT4hMLCP/view?usp=drivesdk) |
| graphene_pbase_dna offset forward 1794346366346.gsf | AFM topography (offset) channel, forward scan | 4.19 MB | [view](https://drive.google.com/file/d/1HqAwix-e9eGOQlIhM_2EbE6rQxDw5GTM/view?usp=drivesdk) |
| graphene_pbase_dna offset reverse 1794346366346.gsf | AFM topography (offset) channel, reverse scan | 4.19 MB | [view](https://drive.google.com/file/d/16cZ5zECJSJF-PDpqY5rIy5ADYWLUshmK/view?usp=drivesdk) |
| graphene_pbase_dna error forward 1794346366346.gsf | AFM error channel, forward scan (feedback error, near zero) | 4.19 MB | [view](https://drive.google.com/file/d/1dj7t1oj4Uar_z9xqGNIupQ4v6jcE9x5w/view?usp=drivesdk) |
| graphene_pbase_dna error reverse 1794346366346.gsf | AFM error channel, reverse scan (feedback error, near zero) | 4.19 MB | [view](https://drive.google.com/file/d/1r32ySpVGetxPk4cdvLHAzBzErf1g7fL1/view?usp=drivesdk) |

**Previews** (rendered from the .gsf originals; raw topography beside a whole-image
plane-subtracted view; no smoothing, masking, line correction, or cropping):

- Topography, forward scan: [afm-topography-offset-forward-preview.png](https://drive.google.com/file/d/185LWp9i9JC74sItsK-gFOLQpBUvaV3Vf/view?usp=drivesdk)
- Topography, reverse scan: [afm-topography-offset-reverse-preview.png](https://drive.google.com/file/d/1IYD4cDsa6MZ1OZGlL-p_3tklkFaZb-3T/view?usp=drivesdk)

The topography shows a broad slope and residual curvature. No identifiable DNA features are
visible at this scale, and nothing in these files by itself establishes a DNA layer thickness
or covalent attachment.

**What the files record:** scan size and pixel dimensions, channel units (topography in
meters, phase in degrees), a header date, and a dwell time of 2500 (the header states no unit
for it). **What they do not record:** instrument, mode, probe, setpoint, or scan rate, and
which physical chip was scanned. The sample name is a file label, not proof of chip identity.
Quantitative heights require the instrument's calibration.

**Readability (verified Nov 12):** the files decode under the GSF format specification (the
binary data begins at the first 4-byte boundary after the header). Two independent parses
agree: forward and reverse topography correlate at 0.9998 raw and 0.9637 after whole-image
plane subtraction, and every file holds exactly 1,048,576 finite values. The error channel
contains 27 discrete levels in the forward scan and 28 in the reverse scan. Feedback error
close to zero is expected; the number of discrete levels does not by itself establish
scan quality.

**How to view .gsf files:** Gwyddion is the recommended viewer.
[Download Gwyddion](https://gwyddion.net/download.php) from its official site.
The PNG previews above cover quick reading.

## Notes and deviations

- Timing has two provenances that do not yet agree. The file headers carry a clock reading of
  Tue Nov 10, 2026, 13:32:45 with no timezone. The filename suffix is a Unix millisecond
  timestamp: Nov 10, 21:32:46 UTC, 15:32:46 in America/Chicago, which matches the Drive
  upload time. Which clock the instrument was on is unconfirmed, so only the date, Nov 10,
  is asserted here.
- Against the lab's own record standard (see the AFM checklist in
  [the rinse and imaging record](../../protocols/2026-11-11-water-rinse-and-dino-lite-imaging.md)):
  scan size is recorded in the files; instrument, mode, probe, setpoint, and rate are not.
- The repo rinse and imaging record says AFM was "reported as run" with no data supplied.
  The exports were in this Drive folder from Nov 10; this index is their repo-side record.

---
Prepared 2026-11-12 by an agent on behalf of Will Clem. Generated from the Drive folder listing
and the lab as-run state file. AFM: 6 channel files, Nov 10, 2026.
