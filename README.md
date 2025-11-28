# .Industrial-LLM-Agents
Industrial LLM agents, prompt safety, and orchestration
# Industrial LLM Agents — dub-l-tap-ai-labs

Guardrailed, eval-backed **LLM agents** for industrial ops (aerospace, energy, mining, manufacturing).  
Built by **Christopher Grove** (Seattle/Tacoma) — **voice-over & broadcast engineering** roots.

![CI](https://github.com/<org>/<repo>/actions/workflows/ci.yml/badge.svg)
![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)

## TL;DR
Industrial workflows need agentic AI that is **safe, observable, and affordable**. This repo ships reference agents, prompt safety, and evals you can run before production.

## Features
- **Prompt safety**: injection/jailbreak checks and policy enforcement  
- **Agent orchestration**: route tasks across revenue, security, and shop-floor agents  
- **Evals**: pass/fail gates you can run locally or in CI  
- **Voice UX**: optional TTS/STT pipelines for high-quality narration and IVR/TTS tuning

## Architecture
```mermaid
flowchart TD
    U[User/Service] --> API[FastAPI]
    API --> Sentinel[Security Prompt Sentinel]
    API --> Router[Task Router]
    Router --> Rev[Revenue Agent]
    Router --> Sec[Security Agent]
    Router --> Shop[Shop-floor Agent]
    API --> Log[Observability/Evals]
