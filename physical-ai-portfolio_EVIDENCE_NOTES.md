# physical-ai-portfolio: Evidence Notes

Companion to physical-ai-portfolio.md. Labels: Confirmed, Ran it, Per the docs, My reading, Ask the author. Depth: LITE, index repo. Repo state read: main at abd2924 (2026-10-22), read-only fresh clone. Nothing in the clone was modified; nothing was pushed.

## E1 Fact sheet

- Name: physical-ai-portfolio; public GitHub repo PCSchmidt/physical-ai-portfolio; MIT (Confirmed, LICENSE and `gh api`: spdx MIT, private false). 0 stars, 0 forks (gh api). Created 2026-10-16T17:16Z, last push 2026-10-22T12:29Z.
- Contents (Confirmed, file listing): README.md (4,841 bytes), docs/roadmap.md (23 lines), SECURITY.md, LICENSE, .gitignore. No source code, no tests, no `.github` folder.
- Commits: 15, 2026-10-16 to 2026-10-22. 14 carry an AI co-author trailer; the initial commit (LICENSE plus stub README, aec7a53) does not. Commit breakdown: initial, c605c01 (README, roadmap, SECURITY, .gitignore), 13 row edits. No agent instruction files or settings folders.
- CI: `gh run list --repo PCSchmidt/physical-ai-portfolio` returned nothing (no workflow exists). Ran it.
- Outside users: none known (Ask the author).
- Not verified: whether GitHub private vulnerability reporting (named in SECURITY.md) is enabled on the repo.

## E2 What was read

README, docs/roadmap.md, SECURITY.md, git log with trailers. Member guides and evidence files read: fusetrack, sentinel-node, triagebox, spectrumsentry, sustain-iq (.md, .evidence.md, and the fusetrack and sustain-iq .review.md files, and the fusetrack questions file for style). For ironboot, wilco and fleetforge, which have no guide: README read through `gh api repos/.../contents/README.md`, repo metadata, commit counts and `gh run list`. Nothing from those three was built or run.

## E3 CI of the members (gh run list, 2026-10-28)

| Repo | Latest runs | Note |
| --- | --- | --- |
| fusetrack | 3 shown, all success (latest 7f6ea5b, 10-28) | Guide's earlier review: all 11 earlier runs success |
| sentinel-node | all success (latest 9095701, 10-28) | Newer than the guide's b6ceaee |
| triagebox | failure, failure, failure (latest 9eee9fc, 10-28; 70f99ca, 10-23; 440c6ce, 10-17) | Cause in triagebox.evidence.md E7/E8: lock fingerprint of test_corpus.jsonl computed on CRLF; CI sees LF |
| spectrumsentry | all success (latest 093cd6a, 10-28) | |
| sustain-iq | all success (latest 9faca4b, 10-28) | |
| ironboot | 2 runs, both success (10-21, 10-23) | |
| wilco | latest 3 success (10-22, 10-23, 10-23) | |
| fleetforge | latest 3 success (10-22, 10-23, 10-23) | |

Checked in review (2026-10-28): the only commits after 23 October in the five guided members (fusetrack 7f6ea5b, sentinel-node 9095701, spectrumsentry 093cd6a, sustain-iq 9faca4b, triagebox 9eee9fc) add the explainer files and images only; no code changed. Sentinel Node's last code commit is b6ceaee (17 Oct). Triagebox run list: 5 failures (first 0cc037e, 17 Oct 16:25Z) after 7 successes. ironboot, wilco, fleetforge CI success on latest runs; all eight repos public, MIT, 0 stars, 0 forks; all eight README links resolve to existing repos.

## E4 Member repo creation dates (gh api)

fusetrack 2026-10-16 17:44Z; sentinel-node 10-16 19:08Z; triagebox 10-17 00:16Z; sustain-iq 10-17 13:26Z; spectrumsentry 10-17 21:24Z; ironboot 10-21 22:47Z; wilco 10-22 12:26Z; fleetforge 10-22 12:26Z. Index created 10-16 17:16Z.

## E5 Claims check: index statement against member evidence

| ID | Index statement | Evidence | Result |
| --- | --- | --- | --- |
| IX-01 | Opening: "multi-sensor fusion tracking" | fusetrack.md: one simulated radar; camera and RF sensors listed as planned (fusetrack.md, "What problem this solves" and "Strengths, shortcomings") | Describes the goal |
| IX-02 | FuseTrack row: "learned vs. classical association" | fusetrack.md: "There is no machine-learning model in this project"; comparison done is GNN vs JPDA | Learned part absent |
| IX-03 | FuseTrack row: "v0.4 ... JPDA built and measured, no better than GNN here" | fusetrack.md and review: JPDA not better in any scenario, worse in clutter; reviewer re-ran saved results | Supported |
| IX-04 | Sentinel Node row: "scaffold + desktop-GPU detector precision result; no device results" | sentinel-node.evidence.md CL-01 to CL-10, CL-08 (no Jetson code or results) | Supported |
| IX-05 | TriageBox row: "quantisation ladder, faithfulness judge, a locked ISR-style test set and an unsupported-answer detector, all measured on a laptop GPU" | triagebox.evidence.md CL-01 to CL-05, E7 | Supported; locked ISR test n = 42 answerable, 18 unanswerable |
| IX-06 | TriageBox row: "distilled, quantized LLM/VLM"; language "Python / C++" | triagebox.evidence.md: distillation/LoRA listed as not done; no VLM mention anywhere in guide or evidence; `find` for *.cpp and *.cu under the triagebox and sentinel-node clones returned nothing | Row describes the plan; "no VLM / no C++" is absence of evidence, not proof (Ran it for files) |
| IX-07 | SpectrumSentry row: "two public datasets; leak-aware splits, simulated-shift sweeps and open-set recognition measured; nothing live or on a device" | spectrumsentry.evidence.md CL-01 to CL-06, E7; guide names CardRF plus a second dataset | Supported |
| IX-08 | Sustain-IQ row: "phase 1 on a PC: honest evaluation and a bit-exact Rust inference engine; nothing on a microcontroller" | sustain-iq.evidence.md CL-01 (305 of 305), CL-02, CL-09 (52 committed windows pass; 2,004-window run not reproducible) | Supported; "bit-exact" rests on 305 committed vectors |
| IX-09 | IronBoot row: "update logic and threat model tested by exhaustive power-cut injection on a simulated flash; nothing on a chip" | ironboot README (read only): 1,626 flash operations, 6,504 runs, 78,048 more with a second cut; "nothing ran on an RP2350" | Consistent with its README; not reproduced |
| IX-10 | WILCO row: "stub planners; simulator runs in a container but nothing is flown by it yet; no language model is wired in"; "C++ / Python" | wilco README (2026-10-23): milestone 0.3 flew 43 vetted missions in PX4 SITL; 0.4 put two local Qwen2.5 models behind the monitor; camera-frame test with a 3B vision model; sources listed are `src/wilco/*.py` | Stale; not reproduced. Timing (commit times UTC): index last edit 22 Oct 12:29; WILCO 0.3 flight commit 22 Oct 17:18 (about 5 h later); 0.4 on 23 Oct 14:01 |
| IX-11 | FleetForge row: "simulated sequential shadow-evaluation test and a tested signed-artifact verifier; no device agent, control plane or real devices"; "Go or Rust" | fleetforge README (2026-10-23): 0.3 device update agent (20,238 simulated power-cut runs), 0.4 staged-rollout control plane (300 simulated devices), chunked delta updates; run commands are pip and pytest | Stale; not reproduced. Timing: index last edit 22 Oct 12:29; device agent commit d533a5d 12:46 (about 17 min later); 0.4 control plane 23 Oct 12:48. Its README still has a leftover sentence "no device agent, control plane" in the status paragraph |
| IX-12 | Connect: "Sentinel Node, SpectrumSentry publish detections as CoT; FuseTrack consumes and emits the same format" | sentinel-node.evidence.md CL-06 (298-byte CoT message, test under 600); `grep -il "cursor.on.target\|CoT"` over spectrumsentry README and docs/*.md found nothing (Ran it); fusetrack README mentions CoT, guide lists CoT output as planned | Sentinel only |
| IX-13 | Connect: "Jetson used for Sentinel Node reused for TriageBox and WILCO" | sentinel-node.evidence.md CL-08; triagebox.md "Hoped for but not yet done" (edge device); wilco README "No hardware" | Not yet true |
| IX-14 | Connect: "Common method: headline measurement first, then a limitations section" | The five guides; sustain-iq.evidence.md S1 and results.md Limitations; fusetrack README Limitations | Supported for five; not checked for the other three |
| IX-15 | Thesis: "a model running on real hardware ... under a latency or power budget" | No member guide reports a device run. Sentinel Node latency is a laptop GPU figure; TriageBox energy is quoted from its docs (not recomputed) | Not yet borne out |
| IX-16 | Roadmap rule: "Finish and benchmark a project before starting the next" | E4 creation dates; FuseTrack still "In progress" | Not followed |
| IX-17 | Roadmap: phase 4 "SpectrumSentry or Sustain-IQ" | Both exist (E4) | Both built |
| IX-18 | Roadmap: phase 5 "only after devices and models exist" | IronBoot, WILCO, FleetForge created 10-21 and 10-22; no member reports a device | Not followed |
| IX-19 | Roadmap gates: Sentinel "latency/energy table at 7/15/25 W", TriageBox "benchmarked on 3 runtimes" | Sentinel: no device table (CL-08). TriageBox guide: model run through llama.cpp only | Gates not met; stated by the guides as planned work |
| IX-20 | Conventions: "CI runs tests from the first commit" | Index itself has no CI. TriageBox red since the lock commit (E3). Others green | Mostly |
| IX-21 | Conventions: every project README follows Problem, Architecture, Results, Reproduce, Limitations | Not checked heading by heading | Not verified |
| IX-22 | Roadmap: "Shared infrastructure ... CoT encoder/decoder used by Projects 1, 2, 3" | The index holds no code; no shared library found across members; Sentinel has its own CoT writer | Not built as shared code |
| IX-23 | Scope: passive RF only; no weapons code | spectrumsentry.md: reads recordings only; fusetrack.md: tracking only. Other three not checked | Supported for two |
| IX-24 | Roadmap: "status in the README is the source of truth" | IX-10 and IX-11: members' READMEs are more current than the index rows | Contradicted in practice |

## E6 Figures in the guide and where they come from

- FuseTrack: 156 m at 200 false echoes with the 3-of-5 rule, 12 to 13 m good runs, 58 tests (fusetrack.md opening and evidence E1).
- Sentinel Node: 0.162 score, INT8 about 0.009 lower (about 5%), 8% to 27% faster than FP16, 42 tests (sentinel-node.md opening; evidence CL-01 to CL-04).
- TriageBox: 74 of 100 correct, 31 of 100 unanswerable wrongly answered, about 14 of 100 after hand reading (triagebox.md opening); ISR locked test 90.5% accuracy, 11.1% hallucination, n 42 and 18 (CL-02); 112 tests, 111 pass on Linux CI (evidence E7). The sentence "about half supported" in the guide comes from CL-05 (17 of 31 supported).
- SpectrumSentry: 77% and 68%; 97% to 21% at 10 dB; 37 tests (spectrumsentry.md opening; CL-01, CL-03; E7).
- Sustain-IQ: 99.9 / 98.7 / 51.9; locked set 43.5% across 24 files; 305 of 305; 32 Python plus 19 Rust tests (CL-01 to CL-03; E-line "Re-run in a scratch copy").

All are carried from the member guides; none were recomputed for this guide.

## E7 Picture sources

- images/physical-ai-portfolio-family-map.png: titled "grouped for this guide" (earlier title wrongly said the index groups them); built from the README table (eight projects); the grouping is this guide's own (sensing; edge model and machines; firmware, autonomy, fleets), chosen for readability. Colour key (green = finished guide, amber = no guide) is printed at the top of the picture. After the reader check the link boxes were removed (the guide's table and text carry IX-12, IX-13, IX-14, IX-16), so the unsupported "about a week" wording no longer appears; the dated claim in the text is 16 to 17 October (five members), 21 October (IronBoot), 22 October (WILCO, FleetForge), from E4.
- images/physical-ai-portfolio-status-grid.png: columns from E3 (tests and CI), the guides (results, hardware) and IX-01 to IX-11 (row match). Recoloured after the reader check: unverified cells are amber, not green. IronBoot, WILCO and FleetForge "code and tests" and "measured results" are amber ("README says yes, CI passes"; "claimed in README, not checked") because nothing was reproduced (IX-09 to IX-11). FuseTrack and Sentinel Node "index row matches" are amber ("Mostly") per IX-01, IX-02 and IX-12. TriageBox "Mostly" and CI red per IX-06 and E3; WILCO and FleetForge red from IX-10 and IX-11.
- Both generated with matplotlib in the scratchpad virtual environment (script pap_figs2.py); both viewed after rendering, no clipped text.

## E8 Rules check

Revised after the reader check. No absolute local paths in the guide, no secrets or `.env` read, no command text such as `gh run list` in the body (it stays here in E1 and E3), build tools named only as "AI coding agents", no "things to confirm" section, no "In short" lines. Two tables plus one list in the guide (project status; six mismatches). "Guide", "member" and every project name and acronym are defined before the first table or picture. The Q&A block, the separate strengths section and the per-project test counts, 305 of 305, the 24-file set and the 7/15/25 W list were cut from the body; those figures remain in the member guides. Word count about 3,400 including tables.

## E9 What was and was not verified

Verified: index contents, commit and CI state, creation dates, README text of three unguided members, and consistency between the index and five finished guides. Not verified: any member's tests or numbers were not re-run for this guide; IronBoot, WILCO and FleetForge were not built; newer commits (after 10-23) in the five guided members were checked by file list only and are guide files; private vulnerability reporting not checked.
