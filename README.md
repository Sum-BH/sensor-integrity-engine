# sensor-integrity-engine

> Audit the instruments your reliability programme stands on.

Before trusting any anomaly/diagnosis model built on plant sensor data, this engine checks
whether the sensors themselves are telling the truth: drift, dropout, cross-talk, and the
downstream decisions that get contaminated when they don't. Built on public or synthetic
sensor data only — no proprietary plant data.

## Phases

| Phase | Folder | Purpose |
|---|---|---|
| 0 | [00_charter](00_charter) | Problem framing: which instruments, which decisions depend on them |
| 1 | [01_instrument_health](01_instrument_health) | Per-sensor health checks: drift, dropout, noise floor, calibration drift |
| 2 | [02_disambiguation](02_disambiguation) | Disambiguate sensor fault vs. real process/asset fault |
| 3 | [03_decision_contamination](03_decision_contamination) | Quantify how much downstream decisions are contaminated by bad sensor data |
| 4 | [04_agent_investigator](04_agent_investigator) | LangGraph agent that investigates flagged instruments and proposes root cause |
| 5 | [05_reporting](05_reporting) | Audit report generation |

## Stack

Python, NumPy, SciPy, pandas, DuckDB, LangGraph, Ollama.

## Hardware

Fully laptop-portable — no GPU-bound phases. Statistical/signal methods (NumPy/SciPy) and
local LLM agent (Ollama, small quant) both run fine on CPU-only hardware.

## Data

Public sensor datasets or synthetic time series generated in-repo. No proprietary
instrumentation data is used or committed.

## Status

Scaffolding stage — phase folders and environment are set up; implementation in progress.

## License

MIT — see [LICENSE](LICENSE).
