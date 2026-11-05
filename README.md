# Nick Altstein

**Software Engineer — AI Infrastructure & Backend Systems**  
New York City · [GitHub](https://github.com/NickAiNYC) · [LinkedIn](https://www.linkedin.com/in/nickaltstein/) · [Technical Site](https://scrutexity.com) · [Email](mailto:nickaltstein@gmail.com)

---

I am a software engineer based in New York City, building AI agent infrastructure, backend systems, and developer tools.

My work focuses on a practical challenge: making agent execution secure, understandable, and reproducible. I build the systems around AI models—authorization controls, workflow runtimes, execution traces, testing, and verification.

**Core Specialization:** Python · TypeScript · Agent Runtimes · Authorization · Workflow Orchestration · Evaluation · Verification

---

## Selected Engineering Work

### [Birkin — Agent Authorization & Evidence Layer](https://github.com/NickAiNYC/Birkin)
*Local-first policy engine and cryptographic audit layer for autonomous tool execution.*

- **Problem:** AI agents invoke high-privilege tools (filesystem mutation, shell processes, database queries, network APIs) without deterministic authorization boundaries, producing unverifiable execution trails that fail security review.
- **Implementation:**
  - Designed a fail-closed policy engine that intercepts agent action requests and validates parameters against path-restricted, shell-restricted, and network-scoped rules.
  - Implemented Ed25519 digital signing of execution receipts (`AuthorizationReceipt`), cryptographically binding agent identity, requested action, and policy decision prior to tool dispatch.
  - Built an append-only, SHA-256 hash-chained audit ledger (`AuditLedger`) ensuring forward-integrity and tamper detection for post-execution forensics.
  - Implemented an offline verification CLI (`birkin verify`) to validate receipts and replay ledger hash chains without external network calls.
  - Authored a demonstration Hermes tool-registry adapter (`birkin.adapters.hermes`) demonstrating the tool-dispatch interception seam (`fs.write`, `fs.read`, `shell.exec`, `http.get`, `http.post`, `db.query`).
- **Technologies:** Python 3.11, Cryptography (Ed25519), Pydantic v2, Typer CLI, Pytest.
- **Verification & Testing:** 40 passing tests with zero failures (`pytest tests/`), including an explicit tamper detection matrix (`tests/test_tamper_matrix.py`) asserting receipt rejection under mutated payloads, modified timestamps, and mismatched keypairs. Published on PyPI as `birkin 0.2.0`.

---

### [INFINI — Portable Agent Workflow Execution & Traces](https://github.com/NickAiNYC/infini)
*Declarative workflow specification and OpenTelemetry-native execution runtime.*

- **Problem:** Agent workflows are locked into vendor-specific runtime frameworks (LangGraph, CrewAI, AutoGen), making execution non-portable and preventing cross-engine trace comparison and replay debugging.
- **Implementation:**
  - Specified the declarative `Loopfile` format (YAML), formalizing multi-agent workflows, steps, dependency DAGs, budget ceilings, and verification contracts.
  - Implemented a lightweight Python CLI (`infini-cli`) with a zero-external-dependency SQLite execution engine for workflow orchestration and step lifecycle management.
  - Built an OpenTelemetry exporter (`infini/otel.py`) mapping workflow executions to spans conforming to the OpenTelemetry GenAI semantic conventions (distinguishing stable attributes from experimental GenAI conventions).
  - Developed cross-engine trace divergence diffing (`infini diff`), isolating the exact step where two execution engines produce divergent outcomes.
  - Added standalone Ed25519 trace signing and offline signature verification (`infini verify-trace`).
- **Engine Status:** 1 reference execution engine fully operational; 5 mock adapters (`langgraph`, `hermes`, `openclaw`, `codemap`, `local`) for cross-engine schema verification; 5 prospective adapters (`crewai`, `autogen`, `mastra`, `goose`, `openai-agents`) designed with fail-closed "not implemented" handlers.
- **Technologies:** Python 3.11, OpenTelemetry (GenAI Semantic Conventions), SQLite, Pytest, Click/Typer.
- **Verification & Testing:** 35 unit tests and 8/8 passing conformance suite tests (`tests/conformance/`). Measured benchmark: 100.0% replay determinism across 100 consecutive runs and 1.824 ms per-step overhead on Apple M4 hardware (`benchmarks/results.json`). Published on PyPI as `infini-cli 0.2.0`.

---

### [PropStein — Quantitative Modeling & Verification Terminal](https://github.com/NickAiNYC/Propstein)
*Empirical NFL prop research terminal and cryptographic closing line value (CLV) ledger.*

- **Problem:** Sports analytics software frequently relies on uncalibrated models, lookahead bias, cherry-picked backtesting, and unverified odds feeds.
- **Implementation:**
  - Built an end-to-end quantitative pricing terminal evaluating full predictive distributions for NFL receiving props using compound Negative Binomial and Gamma formulations.
  - Designed market-anchored shrinkage against sharp devigged closing consensus to temper model variance during uncalibrated regimes.
  - Implemented cryptographic SHA-256 ingestion receipts on market odds snapshots to guarantee immutable input provenance and prevent retroactive line tampering.
  - Enforced freeze-slate cutoff pipelines (`freeze_slate.py`) that strictly lock inputs prior to game kickoff, eliminating lookahead data leakage.
  - Maintained an unedited public calibration record, including transparent publication of negative holdout results (e.g., Week 1 Brier skill deficit of -12.51%) and automated commercial gating that suspends monetization until reaching statistical significance ($N \ge 600$).
- **Integrity Note:** Cryptographic receipts guarantee data ingestion integrity, timestamp immutability, and reproducible audits—they do not guarantee predictive market edge.
- **Technologies:** Python 3.9/3.11, NumPy, SciPy, Pandas, FastAPI / Starlette, Vanilla JS / CSS, Pytest.
- **Verification & Testing:** 562 passing unit and integration tests across data leakage, odds adapter ingestion, line history provenance, feature cutoffs, and paired scoring. Deployed live at [propstein.com](https://propstein.com).

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
