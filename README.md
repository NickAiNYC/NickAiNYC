# Nick Altstein

**Software Engineer | AI Infrastructure & Backend Systems**  
New York City

I build AI systems that can be executed, inspected, tested, and controlled. My work focuses on backend runtimes, policy-controlled agent execution, structured observability, and verifiable data pipelines.

---

### Featured Engineering Projects

#### [INFINI — Agent Workflow Infrastructure](https://github.com/NickAiNYC/infini)
A portable workflow runtime and specification that separates agent execution logic from underlying model runtimes.
- **Workflow Orchestration:** Built a Python CLI and declarative workflow engine (`Loopfile`) backed by SQLite state persistence and budget controls.
- **Observability & Replay:** Implemented OpenTelemetry GenAI semantic trace export, deterministic step replay, and cross-engine execution diffing (`infini diff`).
- **Testing & Verification:** Verified through automated cross-engine conformance suites and reproducible benchmarks (1.846 ms per-step overhead).
- **Links:** [Repository](https://github.com/NickAiNYC/infini) · [Conformance Suite](https://github.com/NickAiNYC/infini/tree/main/tests/conformance) · [Benchmarks](https://github.com/NickAiNYC/infini/blob/main/benchmarks/results.json)

#### [Birkin — Agent Authorization & Evidence](https://github.com/NickAiNYC/Birkin)
A local-first policy engine and cryptographic audit layer for autonomous AI tool execution.
- **Policy Enforcement:** Evaluates agent tool calls against path-restricted, shell-restricted, and network-scoped rules using a fail-closed policy engine.
- **Authorization Evidence:** Issues Ed25519-signed receipts binding agent identity, requested tool parameters, and policy decisions prior to execution.
- **Offline Verification:** Features a standalone verification CLI (`birkin verify`) and an append-only SHA-256 hash-chained ledger tested against adversarial tamper suites.
- **Links:** [Repository](https://github.com/NickAiNYC/Birkin) · [Tamper Test Suite](https://github.com/NickAiNYC/Birkin/blob/main/tests/test_tamper_matrix.py) · [Demonstration](https://github.com/NickAiNYC/Birkin/blob/main/demos/end_to_end.py)

#### [PropStein — Quantitative Research Platform](https://github.com/NickAiNYC/Propstein)
An empirical quantitative research terminal and closing line value (CLV) ledger for NFL player derivative markets.
- **Statistical Modeling:** Built an end-to-end pricing engine calculating predictive distributions using compound Negative Binomial and Gamma formulations with market calibration controls.
- **Data Engineering:** Designed automated ingestion pipelines with strict prospective cutoffs and SHA-256 snapshot hashing to prevent lookahead leakage.
- **Evaluation & Integrity:** Transparently publishes full unedited holdout calibration records and maintains commercial gating backed by 542 automated tests.
- **Links:** [Live Application](https://propstein.com) · [Repository](https://github.com/NickAiNYC/Propstein) · [Evaluation Record](https://propstein.com/performance/)

---

### Technical Stack

- **Languages:** Python, TypeScript, SQL, Bash
- **Backend & Infrastructure:** FastAPI, Starlette, SQLite, PostgreSQL, Docker, Node.js
- **AI Systems:** Agent Runtimes, Policy Engines, Workflow Orchestration, OpenTelemetry (GenAI Semantic Conventions)
- **Testing & Verification:** Pytest, Conformance Testing, Adversarial Tamper Suites, Ed25519 Cryptography, SHA-256 Hash Chaining

---

### Contact

- **LinkedIn:** [linkedin.com/in/nickaltstein](https://www.linkedin.com/in/nickaltstein/)
- **GitHub:** [github.com/NickAiNYC](https://github.com/NickAiNYC)
- **Technical Site:** [scrutexity.com](https://scrutexity.com)
- **Live Application:** [propstein.com](https://propstein.com)
- **Email:** [nickaltstein@gmail.com](mailto:nickaltstein@gmail.com)

Open to engineering opportunities focused on AI infrastructure, backend systems, and agent runtimes.
