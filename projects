# AIMusubi Projects

AIMusubi is a **local-first agentic automation platform** built around one governed loop:

**Observe → Decide → Act → Verify**

This file is the project shelf — each repo below is a reference implementation that proves the loop in a real domain.

---

## 1) AIMusubi NetOps (this repo)

**What it is:** LLM-driven intent operations against real network devices (Cisco IOS-XE, Arista EOS, VyOS) through a unified API.

**What it proves:**  
- Observe device state  
- Decide a minimal change set  
- Act via vendor adapters  
- Verify outcomes + export metrics

**Highlights:**
- FastAPI API + intent engine
- Vendor adapters (RESTCONF/eAPI)
- SQLite state/memory
- Prometheus + Grafana observability
- Open WebUI wired to OpenAPI schema

Start here: `README.md` → Quickstart

---

## 2) Tesla Gateway (separate repo)

**What it is:** Intent-driven agentic control demo for Tesla vehicles using the same loop, with governance controls (confirm/allowlist/dry-run patterns).

**What it proves:**  
- Observe vehicle state  
- Decide safe actions based on intent  
- Act only when allowed/confirmed  
- Verify state changes

**Artifacts you should expect in that repo:**
- FastAPI gateway service
- Intent endpoint(s) (e.g., `prepare_departure`)
- Config template (no secrets committed)
- Demo scripts (curl examples)
- Safety/sanitize checklist for public sharing

Repo: (add link once public / final path confirmed)

---

## Roadmap: more domains

AIMusubi is intentionally cross-domain. NetOps is the first implementation, Tesla is the first consumer implementation, and more can follow (desktop, smart home, cloud ops, finance, etc.) as long as they honor the same governed loop.
