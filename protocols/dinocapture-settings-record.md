# DinoCapture settings record — Living Codes Lab

Purpose: capture the settings tried at the bench, in the exact form they will be
published to GitHub. Fill one trial row per attempt while tuning. When the lab
settles on the standard, fill the FINAL STANDARD block at the bottom and mark it
decided; that block is what gets committed to the repo, verbatim.

Rules: write the value exactly as DinoCapture shows it (if a control shows a
number, write the number; if it shows a position or a word, write that). Leave a
field blank rather than guessing; blanks get flagged, not filled in later.

Scope: AM4117MT-G2FBW. Software: DinoCapture 3.0. Resolution 1280 x 960, PNG.

## Trials

| # | Date/time | Channel | LED level (1-6) | Exposure | Gain | White balance | Magnification | Front cap | Room lights | Reference reading | Verdict / notes |
|---|-----------|---------|-----------------|----------|------|---------------|---------------|-----------|-------------|-------------------|-----------------|
| 1 |           | white   |                 |          |      |               |               |           |             | n/a               |                 |
| 2 |           | blue    |                 |          |      |               |               |           |             |                   |                 |
| 3 |           |         |                 |          |      |               |               |           |             |                   |                 |
| 4 |           |         |                 |          |      |               |               |           |             |                   |                 |
| 5 |           |         |                 |          |      |               |               |           |             |                   |                 |
| 6 |           |         |                 |          |      |               |               |           |             |                   |                 |

Reference reading: the peak brightness of the fluorescence reference (dot of
streptavidin fluorescein conjugate or dilute fluor-oligo on a spare slide/chip),
as a value out of 255 or a percentage of full scale, read from the same frame
used to judge the setting. Target about 180-210 of 255 for the blue channel.

Also record, for each trial: brightness / contrast / saturation / sharpness if
any of them were moved off default, and monochrome (should stay OFF).

## FINAL STANDARD (fill when decided)

```
Decided:          date ______  by ______
Resolution:       1280 x 960     Format: PNG
Auto exposure:    OFF

WHITE-LIGHT BLOCK
LED level:        ______
Exposure:         ______
Gain:             ______

FLUORESCENCE BLOCK (465 nm excitation; 510-545 nm emission filter, integral)
LED level:        ______
Exposure:         ______
Gain:             ______

BOTH CHANNELS
White balance:    mode ______
Brightness / contrast / saturation / sharpness: default (changes: ______)
Monochrome:       OFF
Magnifications:   survey ______ x / detail ______ x; calibration done? ______
Front cap:        ______ for fluorescence frames
Room lights:      ______ for fluorescence frames
Saved as DinoCapture startup default on the lab PC: yes / no
```

---
Working form prepared by an agent on behalf of Will Clem, 2026-11-12, matching
Part C of "Procedure — Fixed capture settings for Dino-Lite imaging sessions."
