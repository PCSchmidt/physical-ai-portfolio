# Roadmap

Order of work. Dates are targets, not commitments; status in the README is the source of truth.

| Phase | Project | Gate to move on |
| --- | --- | --- |
| 1 | FuseTrack (3) | Simulator, IMM + GNN/JPDA tracker, GOSPA/OSPA benchmark, learned-vs-classical comparison, CoT output |
| 2 | Sentinel Node (1) | INT8 detector at 30 FPS, latency/energy table at 7/15/25 W, tracker on device, CoT into ATAK/WinTAK |
| 3 | TriageBox (6) | Quantization ladder benchmarked on 3 runtimes, citation-faithfulness eval, quality-vs-joules plot |
| 4 | SpectrumSentry (2) **or** Sustain-IQ (7) | Chosen based on target employers |
| 5 | IronBoot (4), WILCO (5), FleetForge (8) | Only after devices and models exist to build on |

## Rules

- Finish and benchmark a project before starting the next.
- Hardware is bought when its project is about to start, not before.
- A project is "Complete" only when its README leads with measured results and documents limitations.

## Shared infrastructure to build once

- CoT (Cursor-on-Target) encoder/decoder used by Projects 1, 2, 3.
- Benchmark harness for latency and power on Jetson.
- README skeleton and CI template.
