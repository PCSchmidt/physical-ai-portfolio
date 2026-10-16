# physical-ai-portfolio

Portfolio of physical-AI and edge-autonomy projects: multi-sensor fusion tracking, Jetson edge sensing, RF signal ML, air-gapped edge LLMs, secure Rust firmware, and edge MLOps. Each is measured, not just demoed: latency, power, accuracy, and failure modes. Public data and unclassified scenarios only. Receive-only RF.

## Thesis

Few ML engineers can show a model running on real hardware, inside a tested system, under a latency or power budget. Each project here is built to produce that evidence: a headline benchmark, a reproducible setup, and an honest account of where it fails.

## Projects

Status is stated plainly. **Planned** means nothing is built yet. Results appear only once measured.

| # | Project | Core problem | Language | Hardware | Status |
| --- | --- | --- | --- | --- | --- |
| 3 | [FuseTrack](https://github.com/PCSchmidt/fusetrack) | Multi-sensor fusion tracker for counter-UAS; learned vs. classical association | Rust | None (simulated sensors) | In progress (v0.3: GNN tracker, IMM) |
| 1 | Sentinel Node | Detect → track → publish on a 15 W edge budget | C++ / Python | Jetson Orin Nano | Planned |
| 6 | TriageBox | Air-gapped distilled, quantized LLM/VLM for ISR triage | Python / C++ | Jetson Orin Nano / AGX | Planned |
| 2 | SpectrumSentry | Open-set RF drone-link classification from raw IQ | Python / C++ | RTL-SDR | Planned |
| 7 | Sustain-IQ | TinyML predictive maintenance, edge-to-cloud | C / Python | ESP32-S3 | Planned |
| 4 | IronBoot | Verified boot, signed OTA, on-MCU anomaly detection | Embedded Rust | STM32 / nRF | Planned |
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
