# physical-ai-portfolio

Portfolio of physical-AI and edge-autonomy projects: multi-sensor fusion tracking, Jetson edge sensing, RF signal ML, air-gapped edge LLMs, secure Rust firmware, and edge MLOps. Each is measured, not just demoed: latency, power, accuracy, and failure modes. Public data and unclassified scenarios only. Receive-only RF.

## Thesis

Few ML engineers can show a model running on real hardware, inside a tested system, under a latency or power budget. Each project here is built to produce that evidence: a headline benchmark, a reproducible setup, and an honest account of where it fails.

## Projects

Status is stated plainly. **Planned** means nothing is built yet. Results appear only once measured.

| # | Project | Core problem | Language | Hardware | Status |
| --- | --- | --- | --- | --- | --- |
| 3 | [FuseTrack](https://github.com/PCSchmidt/fusetrack) | Multi-sensor fusion tracker for counter-UAS; learned vs. classical association | Rust | None (simulated sensors) | In progress (v0.4: GNN tracker with IMM, clutter-robust confirmation; JPDA built and measured, no better than GNN here) |
| 1 | [Sentinel Node](https://github.com/PCSchmidt/sentinel-node) | Detect → track → publish on a 15 W edge budget | Python (C++ later) | Desktop GPU first, then Jetson Orin Nano | In progress (scaffold + desktop-GPU detector precision result; no device results) |
| 6 | [TriageBox](https://github.com/PCSchmidt/triagebox) | Air-gapped distilled, quantized LLM/VLM for ISR triage | Python / C++ | Desktop GPU first, then Jetson Orin Nano | In progress (quantisation ladder, faithfulness judge, a locked ISR-style test set and an unsupported-answer detector, all measured on a laptop GPU; no edge-device results yet) |
| 2 | [SpectrumSentry](https://github.com/PCSchmidt/spectrumsentry) | Open-set RF drone-link classification from raw IQ | Python (C++ later) | Public datasets first (no SDR yet) | In progress (two public datasets; leak-aware splits, simulated-shift sweeps and open-set recognition measured; nothing live or on a device) |
| 7 | [Sustain-IQ](https://github.com/PCSchmidt/sustain-iq) | TinyML vibration classification from public bearing data to a microcontroller | Python / Rust | Microcontroller board (planned) | In progress (phase 1 on a PC: honest evaluation and a bit-exact Rust inference engine; nothing on a microcontroller yet) |
| 4 | [IronBoot](https://github.com/PCSchmidt/ironboot) | Verified boot, signed A/B update, rollback protection | Embedded Rust | RP2350 (planned) | In progress (update logic and threat model tested by exhaustive power-cut injection on a simulated flash; nothing on a chip, no on-MCU anomaly detection yet) |
| 5 | WILCO | Language-tasked drone autonomy inside a safety envelope | C++ / Python | PX4 SITL + Jetson | Planned |
| 8 | FleetForge | Signed model OTA, canary rollout, on-device eval | Go or Rust | Reuses devices above | Planned |

Numbers follow the original project slate; rows are listed in build order. Each project lives in its own repository and is linked here once it has a first commit.

## How the pieces connect

- **Common track format.** The sensing projects (Sentinel Node, SpectrumSentry) publish detections as Cursor-on-Target (CoT) messages, and FuseTrack consumes and emits the same format.
- **Common device.** The Jetson used for Sentinel Node is reused for TriageBox and WILCO hardware-in-the-loop work.
- **Common method.** Every project reports a headline measurement first (latency/energy, accuracy vs. SNR, quality vs. joules), then a limitations section.

See [docs/roadmap.md](docs/roadmap.md) for the build order and milestones.

## Scope and safety

- **Passive RF only.** No transmitting, jamming, or spoofing. RF projects receive only.
- **Defensive and sustainment scope.** Sensing, tracking, search, inspection, and maintenance. No weapons release, terminal guidance, or targeting code.
- **Public data only.** Public datasets and synthetic or unclassified scenarios. No employer, program, or controlled information.
- **Flight.** Any real flight is subject to FAA Part 107 and local rules.

See [SECURITY.md](SECURITY.md) for reporting issues.

## Conventions

Every project README follows the same skeleton: Problem, Architecture, Results, Reproduce, Limitations and failure modes. CI runs tests from the first commit.

## License

MIT. See [LICENSE](LICENSE).
