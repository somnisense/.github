# SomniAI

> **On-device sleep health from a phone microphone — no wearable, no upload, no account.**

SomniAI is an independent research and product LLC working on audio-based sleep monitoring that runs entirely on the device. The repositories here are the algorithm side of that work, openly published so what listens to you sleeping isn't a black box.

The current flagship product is **SomniSense**, an iOS / Android app that turns one night's audio into a private snore + breathing-pause report.
→ [somnisense.top](https://www.somnisense.top)

Production deployment specifics and the audio pre-processing front-end are covered by pending US patents and not redistributed here.

---

## Research

| Repo | What it covers |
|---|---|
| [`audio-sleep-cnn-baselines`](https://github.com/somnisense/audio-sleep-cnn-baselines) | Two CNN baselines for audio-based sleep monitoring — a 2D-CNN snore detector and a 1D-CNN apnea detector, with multi-seed bootstrap CIs on 80 PSG-paired nights across 40 participants. Methodology-focused: intentionally simple architectures + openly released evaluation code. |
| [`ca1d-sleep-apnea`](https://github.com/somnisense/ca1d-sleep-apnea) | A 1D Coordinate-Attention architecture for audio-based sleep apnea detection — a 14,001-parameter network that hits 87% accuracy (a 93% parameter reduction over the standard baseline), with full architecture and training code. |
| [`apnea-compression-pipeline`](https://github.com/somnisense/apnea-compression-pipeline) | An on-device compression pipeline: joint quantization-aware training + L1-structured pruning that takes the model down to 9,416 INT8 parameters and CoreML on the Apple Neural Engine at 0.064 ms / inference, without sacrificing accuracy. |

All three accompanying preprints are forthcoming on arXiv (links live here once first uploaded). All code is MIT-licensed for research and reproducibility.

---

## Why we publish

A few specific reasons, in order of importance:

1. **You should be able to inspect the model that listens to you sleeping.** That's a higher bar than most sleep apps clear today. Publishing the architecture, training protocol, and per-seed metrics is the version of "trust us" that's actually verifiable.
2. **Bootstrap CIs matter on small biomedical datasets.** Single-seed numbers in this regime are routinely misleading. We publish 5-seed × 10,000-iteration bootstrap CIs so the next group doesn't waste time chasing seed-noise.
3. **Reference numbers help downstream work.** A common dataset and identical evaluation protocol across the three preprints — anyone testing a new attention design, a new compression technique, or a new front-end can compare against ours.

What we *don't* publish:

- The 40-participant audio-PSG dataset itself (consent doesn't cover public release).
- The production audio pre-processing front-end and event-triggered inference scheduler — covered by pending US patents.

---

## About SomniAI LLC

Wyoming-registered LLC. The longer version of why this exists is on the marketing site: [somnisense.top/story](https://www.somnisense.top/story).

---

## Partnerships & Collaboration

We're open to a wide range of collaboration:

- **Research collaborations** — sleep medicine, mobile health, on-device ML, audio-based biomedical signal processing
- **SDK / API integration** — consumer health platforms, wearable ecosystems, smart-home audio products
- **Clinical partnerships** — sleep specialists, sleep clinics, healthcare providers, sleep-related medical-device companies
- **Academic / industrial co-authorship** on the next round of preprints, particularly around cross-cohort validation and language / device generalization

Reach out at `service@somnisense.top`.

---

## Contact

- General contact: `service@somnisense.top`
- The app: **[somnisense.top](https://www.somnisense.top)**

---

<sub>SomniAI LLC · 30 N Gould St, Sheridan, WY 82801, USA</sub>
