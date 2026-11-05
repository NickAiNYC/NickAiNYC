# Nick Altstein

**Software Engineer — AI Infrastructure & Backend Systems**  
New York City · [GitHub](https://github.com/NickAiNYC) · [LinkedIn](https://www.linkedin.com/in/nickaltstein/) · [Technical Site](https://scrutexity.com) · [Email](mailto:nickaltstein@gmail.com)

---

I am a software engineer based in New York City, building AI agent infrastructure, backend systems, and developer tools.

My work focuses on a practical challenge: making agent execution secure, understandable, and reproducible. I build the systems around AI models—authorization controls, workflow runtimes, execution traces, testing, and verification.

**Core Specialization:** Python · TypeScript · Agent Runtimes · Authorization · Workflow Orchestration · Evaluation · Verification

---

## Selected Engineering Work

### [INFINI — Portable AI Agent Workflow Infrastructure](https://github.com/NickAiNYC/infini)
*Define a workflow once. Execute, inspect, and verify it through a consistent runtime interface.*

- Built a Python CLI and declarative workflow specification (`Loopfile`) that separates agent orchestration from execution engines.
- SQLite-backed orchestration with budget enforcement and step verification.
- Structured execution traces, replay, and cross-engine divergence diffing (`infini diff`).
- OpenTelemetry trace export (GenAI semantic conventions) and offline Ed25519 signature verification.
- Automated conformance tests and reproducible local benchmarks.
- **Stack:** Python · SQLite · YAML · pytest · GitHub Actions · OpenTelemetry
- **Links:** [Source Code](https://github.com/NickAiNYC/infini) · [Conformance Tests](https://github.com/NickAiNYC/infini/tree/main/tests/conformance) · [Benchmarks](https://github.com/NickAiNYC/infini/blob/main/benchmarks/results.json)
- **Current Status:** Working reference engine; external runtime adapters remain experimental.
- **Verification & Evidence:** 56 unit and integration tests (`pytest cli/tests`) plus 8 core workflow conformance test cases (`tests/conformance/`). Measured benchmark: 100.0% replay determinism across 100 consecutive runs and 1.846 ms per-step overhead on Apple M4 hardware (`benchmarks/results.json`). Published on PyPI as `infini-cli 0.2.0`.

---

### [Birkin — Agent Authorization & Evidence Layer](https://github.com/NickAiNYC/Birkin)
*Local-first policy engine and cryptographic audit layer for autonomous tool execution.*

- Built a fail-closed policy engine that intercepts agent action requests and validates parameters against path-restricted, shell-restricted, and network-scoped rules.
- Implemented Ed25519 digital signing of execution receipts (`AuthorizationReceipt`), cryptographically binding agent identity, requested action, and policy approval prior to tool dispatch.
- Append-only, SHA-256 hash-chained audit ledger (`AuditLedger`) ensuring forward-integrity and tamper detection for post-execution forensics.
- Standalone offline verification CLI (`birkin verify`) to validate receipts and replay ledger hash chains without network calls.
- Authored a demonstration Hermes tool-registry adapter (`birkin.adapters.hermes`) demonstrating the tool-dispatch interception seam (`fs.write`, `fs.read`, `shell.exec`, `http.get`, `http.post`, `db.query`).
- **Stack:** Python · Cryptography (Ed25519) · Pydantic · Typer · pytest
- **Links:** [Source Code](https://github.com/NickAiNYC/Birkin) · [PyPI Package](https://pypi.org/project/birkin/)
- **Current Status:** Core authorization engine and offline verification complete; adapter harnesses demonstrate runtime seams.
- **Verification & Evidence:** 40 passing tests with zero failures (`pytest tests/`), including an explicit tamper detection matrix (`tests/test_tamper_matrix.py`) asserting receipt rejection under mutated payloads, modified timestamps, and mismatched keypairs. Published on PyPI as `birkin 0.2.0`.

---

### [PropStein — Quantitative Modeling & Verification Terminal](https://github.com/NickAiNYC/Propstein)
*Empirical NFL prop research terminal and cryptographic closing line value (CLV) ledger.*

- Built an end-to-end quantitative pricing terminal evaluating full predictive distributions for NFL receiving props using compound Negative Binomial and Gamma formulations.
- Designed market-anchored shrinkage against sharp devigged closing consensus to temper model variance during uncalibrated regimes.
- Implemented SHA-256 integrity checks for recorded market snapshots and prospective cutoff validation to support reproducible evaluation and detect potential data leakage.
- Maintained an unedited public calibration record, including transparent publication of negative holdout results (e.g., Week 1 Brier skill deficit of -12.51%) and automated commercial gating that suspends monetization until reaching statistical significance ($N \ge 600$).
- **Integrity Note:** Cryptographic checksums verify payload integrity of recorded market snapshots, while prospective cutoffs and automated test suites help detect lookahead leakage—they do not guarantee predictive market edge.
- **Stack:** Python · NumPy · SciPy · Pandas · FastAPI / Starlette · Vanilla JS / CSS · pytest
- **Links:** [Source Code](https://github.com/NickAiNYC/Propstein) · [Live Terminal](https://propstein.com) · [Audit Protocol](https://propstein.com/performance/)
- **Verification & Evidence:** Automated test suites spanning Python (542 tests) and Node.js (294 tests) covering data leakage, odds adapter ingestion, line history provenance, feature cutoffs, and paired scoring. Deployed live at [propstein.com](https://propstein.com).

---

## How I Engineer

- **Fail-Closed by Default:** Systems default to denial. Missing parameters, unverified cryptographic signatures, unauthorized tool paths, or unquoted market lines abort execution immediately rather than degrading into unsafe fallback states.
- **Offline Cryptographic Proofs:** Verification should never depend on trust in a remote server. Execution receipts, audit logs, and workflow traces are signed using Ed25519 and chained via SHA-256 hashes, allowing full offline auditability.
- **Comprehensive Verification Suites:** Test suites are treated as first-class architectural artifacts. Projects include explicit tamper matrices, cross-engine conformance assertions, data leakage barriers, and reproducible determinism benchmarks.
- **Explicit Interfaces & Architectural Honesty:** Pure mathematical and policy logic is decoupled from transport layers, external tool dispatchers, and language models. Demonstrations, mock harnesses, and experimental adapters are documented transparently rather than claiming production completeness.

---

## Technical Repertoire

- **Languages:** Python (3.9–3.11), TypeScript, JavaScript, SQL, Bash
- **Backend & Runtimes:** FastAPI, Starlette, Node.js, SQLite, PostgreSQL, Docker
- **Agent Infrastructure:** Policy Evaluation Engines, Tool Authorization, Workflow Orchestration, OpenTelemetry (GenAI Semantic Conventions), Execution Traces & Replay
- **Security & Quality:** Ed25519 Cryptography, SHA-256 Tamper-Evident Ledgers, Pytest, Data Leakage Prevention, Conformance Suites, GitHub Actions CI/CD

---

## Contact & Links

- **GitHub:** [github.com/NickAiNYC](https://github.com/NickAiNYC)
- **LinkedIn:** [linkedin.com/in/nickaltstein](https://www.linkedin.com/in/nickaltstein/)
- **Technical Site:** [scrutexity.com](https://scrutexity.com)
- **Live Terminal:** [propstein.com](https://propstein.com)
- **Email:** [nickaltstein@gmail.com](mailto:nickaltstein@gmail.com)

*Open to engineering discussions regarding AI infrastructure, agent execution runtimes, backend platforms, and systems engineering roles.*
