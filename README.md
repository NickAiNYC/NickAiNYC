<div align="center">

<!-- ═══════════════════════════════════════════════════════════════════ -->
<!--                         JUNE 2026 PROFILE                          -->
<!-- ═══════════════════════════════════════════════════════════════════ -->

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/infini-hero.png">
  <source media="(prefers-color-scheme: light)" srcset="assets/infini-hero.png">
  <img alt="INFINI — portable agent infrastructure" src="assets/infini-hero.png" width="100%" />
</picture>

<br/>

<img src="https://capsule-render.vercel.app/api?type=rect&height=8&color=0:00D4FF,50:25E587,100:0D1117&section=header" width="100%" />

# Nick Ai

### Builder of portable agent infrastructure, governed AI systems, and open-source loops.

<a href="https://github.com/NickAiNYC/infini">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=22&duration=2300&pause=650&color=25E587&center=true&vCenter=true&width=1000&lines=Building+INFINI+%E2%80%94+the+open+standard+for+agent+portability.;Loopfiles.+Adapters.+Traces.+Replay.+Observatory.;Write+agent+logic+once.+Run+it+anywhere.;June+2026%3A+shipping+portable%2C+inspectable+AI+systems." alt="Typing animation" />
</a>

<br/><br/>

<p>
  <a href="https://github.com/NickAiNYC/infini"><img src="https://img.shields.io/badge/Featured-INFINI-25E587?style=for-the-badge&labelColor=0D1117&logo=github&logoColor=white" /></a>
  &nbsp;
  <img src="https://img.shields.io/badge/Focus-Agent%20Portability-00D4FF?style=for-the-badge&labelColor=0D1117" />
  &nbsp;
  <img src="https://img.shields.io/badge/Discipline-Governed%20AI-7DD3FC?style=for-the-badge&labelColor=0D1117" />
  &nbsp;
  <img src="https://img.shields.io/badge/Based-NYC-25E587?style=for-the-badge&labelColor=0D1117" />
</p>

<br/>

[**INFINI**](https://github.com/NickAiNYC/infini) · [Scrutexity](https://scrutexity.com) · [X](https://x.com/nickaltstein) · [LinkedIn](https://linkedin.com/in/nicklatstein)

</div>

---

## Current Focus: INFINI

> **Agents need their Docker moment.**
>
> INFINI is an open standard for agent portability: define autonomous work as a portable Loopfile, execute it through different runtimes, verify the result, and replay the trace when something breaks.

<table>
  <tr>
    <td width="50%" valign="top">
      <h3>Why it matters</h3>
      <p>Most agent logic is trapped inside frameworks, SDKs, prompts, and brittle orchestration code. INFINI moves the logic into a declarative spec so the same workflow can travel across engines.</p>
      <ul>
        <li><strong>Portable logic</strong> — one Loopfile, multiple runtimes.</li>
        <li><strong>Inspectable execution</strong> — standardized traces instead of black-box logs.</li>
        <li><strong>Replayable runs</strong> — debug the loop, not just the error.</li>
        <li><strong>Adapter ecosystem</strong> — Hermes, OpenClaw, and future community runtimes.</li>
      </ul>
    </td>
    <td width="50%" valign="top">
      <h3>Quickstart</h3>

```bash
pip install infini-cli
infini validate loop.yaml
infini run examples/golden-research-assistant/research-loop.yaml --mock
infini ui runs/latest/run.json
```

<sub>Validate the spec. Run the loop. Inspect the trace. Replay the system.</sub>
    </td>
  </tr>
</table>

<div align="center">

<a href="https://github.com/NickAiNYC/infini">
  <img src="https://github-readme-stats.vercel.app/api/pin/?username=NickAiNYC&repo=infini&theme=github_dark&hide_border=true&title_color=25E587&icon_color=00D4FF&text_color=C9D1D9&bg_color=0D1117" alt="Pinned INFINI repository" />
</a>

<br/>

<a href="https://github.com/NickAiNYC/infini"><img src="https://img.shields.io/github/stars/NickAiNYC/infini?style=for-the-badge&label=Stars&color=25E587&labelColor=0D1117&logo=github" /></a>
&nbsp;
<a href="https://github.com/NickAiNYC/infini"><img src="https://img.shields.io/github/forks/NickAiNYC/infini?style=for-the-badge&label=Forks&color=00D4FF&labelColor=0D1117&logo=github" /></a>
&nbsp;
<a href="https://github.com/NickAiNYC/infini/blob/main/spec/loopfile-v1.md"><img src="https://img.shields.io/badge/Spec-Loopfile%20v1.0-25E587?style=for-the-badge&labelColor=0D1117" /></a>
&nbsp;
<a href="https://github.com/NickAiNYC/infini/tree/main/registry/certifications"><img src="https://img.shields.io/badge/Adapters-Hermes%20%2B%20OpenClaw-00D4FF?style=for-the-badge&labelColor=0D1117" /></a>

</div>

---

## The Loopfile Idea

```yaml
LOOPFILE: "1.0"
name: research-assistant

AGENTS:
  - { name: researcher, model_tier: sonnet, tools: [browser] }
  - { name: verifier,  model_tier: haiku }

STEPS:
  - { id: s1, action: browser.find_sources, uses: researcher }
  - { id: s2, action: verify_citations, uses: verifier, depends_on: [s1] }

VERIFY:
  syntactic: ["every_claim_has_citation"]
  semantic: ["source_quality >= 85"]
  confidence_threshold: 85

BUDGET: { dollars: 6, minutes: 20 }
STOP_WHEN: ["all_verify_passed"]
```

<div align="center">

```text
Loopfile → Engine → Adapter → Execution → Trace → Replay → Observatory
```

</div>

---

## What I Build

<table>
  <tr>
    <td width="33%" valign="top">
      <h3>Open Standards</h3>
      <p>Specs, schemas, conformance tests, adapters, certification paths, and contributor-friendly docs.</p>
    </td>
    <td width="33%" valign="top">
      <h3>Governed Agents</h3>
      <p>Agent loops with verification, policy boundaries, audit trails, replay, budget controls, and escalation logic.</p>
    </td>
    <td width="33%" valign="top">
      <h3>Trust Infrastructure</h3>
      <p>Claim intelligence, visibility systems, proof assets, and AI workflows for regulated or trust-sensitive markets.</p>
    </td>
  </tr>
</table>

---

## Featured Systems

| Project | What it is | Why it exists |
| --- | --- | --- |
| **[INFINI](https://github.com/NickAiNYC/infini)** | Open standard for portable, inspectable agent loops. | To make autonomous work reusable across frameworks. |
| **[Scrutexity](https://scrutexity.com)** | Governed growth infrastructure for claim-sensitive businesses. | To help teams prove claims, improve visibility, and recover demand safely. |
| **AuditGPT / Claim Intelligence** | Claim review and proof-gap detection layer. | To turn risky public claims into safer, evidence-backed assets. |
| **Contento by Scrutexity** | Governed content workflow. | To produce content from approved claims instead of unsupported marketing guesses. |

---

## Engineering Principles

```text
Spec first. Demo second. Hype last.
Readable artifacts beat magic.
Every loop needs a verifier.
Every verifier needs a trace.
Every trace should be replayable.
```

I care about systems that are understandable under pressure: when a demo fails, when an agent drifts, when a customer asks why, when a regulator asks for proof, or when a contributor wants to extend the standard.

---

## Stack

<div align="center">

<img src="https://skillicons.dev/icons?i=python,typescript,nextjs,react,fastapi,nodejs,postgres,redis,sqlite,docker,git,github,bash,linux,cloudflare,vercel&theme=dark&perline=8" />

<br/><br/>

<img src="https://img.shields.io/badge/Agent%20Loops-25E587?style=flat-square&labelColor=0D1117" />
<img src="https://img.shields.io/badge/Loopfile%20YAML-00D4FF?style=flat-square&labelColor=0D1117" />
<img src="https://img.shields.io/badge/Adapter%20SDK-7DD3FC?style=flat-square&labelColor=0D1117" />
<img src="https://img.shields.io/badge/Trace%20Replay-25E587?style=flat-square&labelColor=0D1117" />
<img src="https://img.shields.io/badge/Observatory-00D4FF?style=flat-square&labelColor=0D1117" />
<img src="https://img.shields.io/badge/Governance%20as%20Code-7DD3FC?style=flat-square&labelColor=0D1117" />

</div>

---

## GitHub Signals

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=NickAiNYC&show_icons=true&theme=github_dark&hide_border=true&count_private=true&bg_color=0D1117&title_color=25E587&icon_color=00D4FF&text_color=C9D1D9&ring_color=25E587" height="170" />
&nbsp;
<img src="https://github-readme-streak-stats.herokuapp.com/?user=NickAiNYC&theme=github-dark-blue&hide_border=true&background=0D1117&ring=25E587&fire=00D4FF&currStreakLabel=25E587&sideLabels=C9D1D9&currStreakNum=FFFFFF&sideNums=FFFFFF&dates=8B949E" height="170" />

<br/><br/>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=NickAiNYC&bg_color=0D1117&color=25E587&line=00D4FF&point=FFFFFF&area=true&area_color=25E587&hide_border=true&custom_title=June%202026%20Shipping%20Graph" width="100%" />

</div>

---

## Contribution Feed

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/NickAiNYC/NickAiNYC/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/NickAiNYC/NickAiNYC/output/github-contribution-grid-snake.svg" />
  <img alt="GitHub contribution snake" src="https://raw.githubusercontent.com/NickAiNYC/NickAiNYC/output/github-contribution-grid-snake-dark.svg" />
</picture>

</div>

---

## Now Building

- **INFINI reference runtime** — end-to-end Loopfile execution, trace generation, replay, and Observatory.
- **Adapter certification** — conformance tests for Hermes, OpenClaw, and community frameworks.
- **Loop registry** — a contribution layer for reusable loops, skills, patterns, and benchmark cases.
- **Governed growth systems** — Scrutexity, AuditGPT, Contento, AI visibility, and recovery workflows.

---

<div align="center">

### Building the standard layer for autonomous work.

<p>
  <a href="https://github.com/NickAiNYC/infini"><img src="https://img.shields.io/badge/Star%20INFINI-25E587?style=for-the-badge&labelColor=0D1117&logo=github&logoColor=white" /></a>
  &nbsp;
  <a href="https://scrutexity.com"><img src="https://img.shields.io/badge/Scrutexity-00D4FF?style=for-the-badge&labelColor=0D1117&logo=safari&logoColor=white" /></a>
  &nbsp;
  <a href="https://x.com/nickaltstein"><img src="https://img.shields.io/badge/X-000000?style=for-the-badge&labelColor=0D1117&logo=x&logoColor=white" /></a>
  &nbsp;
  <a href="https://linkedin.com/in/nicklatstein"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&labelColor=0D1117&logo=linkedin&logoColor=white" /></a>
</p>

<br/>

<img src="https://komarev.com/ghpvc/?username=NickAiNYC&style=for-the-badge&color=25E587&labelColor=0D1117&label=PROFILE+VIEWS" />

<br/><br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0D1117,35:00D4FF,70:25E587,100:0D1117&height=120&section=footer&text=Portable%20Agents%20%E2%80%A2%20Inspectable%20Loops%20%E2%80%A2%20Open%20Standards&fontSize=18&fontColor=C9D1D9&fontAlignY=70&animation=fadeIn" width="100%" />

</div>
