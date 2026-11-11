# Protocols

Dated bench procedures in the order they are run. These are the operative protocols.

| Date | Protocol | Covers | Status |
| --- | --- | --- | --- |
| 2026-11-04 | [PBASE in DMF: graphene coating](2026-11-04-pbase-dmf-graphene.md) | ~5 mM PBASE in dry DMF, 100 min wet, DMF + water rinse, N₂ dry, AFM endpoint | first run |
| 2026-11-05 | [First attachment of amino-gattaca](2026-11-05-amino-gattaca-pbase-graphene.md) | 1 µM amine-DNA, 60 min RT, 100 mM ethanolamine pH 9.0 for 30 min, rinses 3 × 500 µL | run 2026-11-05; re-wetted and imaged 2026-11-11; AFM data not yet recorded |
| 2026-11-11 | [Water rinse and Dino-Lite imaging](2026-11-11-water-rinse-and-dino-lite-imaging.md) | 6 × 1 mL ultrapure water in a 24-well plate, white vs blue excitation (images 36–39) | run 2026-11-11; pre-hybridization baseline |
| 2026-11-11 | [Hybridization of fluor-tgtaatc](2026-11-11-fluor-tgtaatc-hybridization.md) | 1 µM fluorescein complement, 90 °C → 37 °C anneal at 1 °C/min, PBS washes, fluorescence readout | proposed, not yet run |

Oligo and reagent records: [`reports/`](../reports/), including the [Invitrogen certificates for order 12091076](../reports/invitrogen/12091076/README.md).

**Order matters, and one step is one-way.** The complement is the exact 50 nt reverse complement, so it duplexes the template's 3′ terminus and **blocks TdT**. Hybridization is therefore the last thing done to a chip that is being extended, or it is done on a replicate chip; keep an unhybridized chip aside. The same anneal is also the first half of the HindIII release step.

`proposal.tex` in the repository root is the system description and experimental plan (hypothesis, GFET setup, Protocols 1 and 2, release chemistry). It contains no bench procedure: its former inline functionalization section (1 mM PBASE dried by solvent evaporation for 15–30 min, 50 mM ethanolamine in PBS) was never executed and has been removed, with the text left in the history.

## Where these procedures sit against published practice

Every published PBASE/amine-DNA graphene protocol uses the same four steps: PBASE in DMF → rinse → 5′-amine DNA → optional block. Concentration and time trade off against each other, so PBASE exposure is easiest to compare as concentration × time.

| Study | PBASE | PBASE exposure | Amine-DNA step | Block |
| --- | --- | ---: | --- | --- |
| Ping et al., *ACS Nano* 10:8700 (2016) | 1 mM, DMF, 20 h soak | 20 mM·h | 1 µM in water, 3 h | none |
| Xu et al., *Nat Commun* 8:14902 (2017) | 10 mM, DMF, 1 h RT | 10 mM·h | 1 µM in 1× PBS, flowed 1 h | 100 mM ethanolamine (pH and time not stated) |
| Huang et al., *Nanoscale* 2:1485 (2010) | 5 mM, DMF, 2 h RT | 10 mM·h | enzyme in carbonate pH 9.0, 4 °C, overnight (not DNA) | 0.1 M ethanolamine, pH 9.0, 30 min |
| Deng et al., *Biosensors* 16(2):125 (2026) | 7.8 mM, anhydrous DMF, 1 h RT | 7.8 mM·h | 1–2 µM in PBS pH 7.8, 40 min, dark | none |

**Our coating protocol** (5 mM × 100 min ≈ 8.3 mM·h) sits inside that 7.8–20 mM·h range, closest to Huang, and like all four published protocols it keeps the surface wet and rinses with DMF rather than drying the solvent onto the graphene.

**Our attachment protocol** matches on every axis: 1 µM amine-DNA (Ping, Xu), 60 min (between Deng's 40 min and Xu's 1 h), PBS pH 7.4 (Xu's 1× PBS, Deng's pH 7.8), and 100 mM ethanolamine at pH 9.0 for 30 min, which is Huang's blocking recipe exactly.

Two honest gaps:

- Blocking is not universal. Ping and Deng skip it entirely; it is standard in the enzyme/antibody literature (Huang, capping NHS before the next layer) and in Xu. We block because Xu and Huang do, not because every DNA-GFET protocol does.
- No published protocol drops 50 µL on a 1 cm² chip. All four flow or immerse, so mass transport is the one variable the literature does not cover, and no precedent was found for a 5–10 min coupling step.
