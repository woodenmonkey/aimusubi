# AIMusubi – Local-First Agentic Automation Platform

AIMusubi is a **local-first agentic automation platform** that enables an LLM to operate through a governed loop:

**Observe → Decide → Act → Verify**

It ships as a framework — and becomes a **platform** when bootstrapped with adapters, memory, and observability.

> This is not “voice commands.”  
> This is not hard-coded automation.  
> This is an agentic loop with guardrails.

---

## Projects

AIMusubi is the platform. Each repository below is a **reference implementation** that proves the same agentic loop in a real domain:

- **AIMusubi NetOps (this repository)**  
  LLM-driven intent operations against **real network devices** (Cisco IOS-XE, Arista EOS, VyOS) using a unified API and full observability.

- **Tesla Gateway (separate repository)**  
  Intent-driven agentic control demo for Tesla vehicles using the same observe → decide → act → verify loop, with governance controls.

- **AIMusubi Control-Plane Forensics (separate repository)**  
  AIMusubi Control-Plane Forensics is a topology-aware, deterministic incident reconstruction framework designed to explain why control-plane changes occur 

See `PROJECTS.md` for a shelf view and links to each project.

---

## Why AIMusubi?

- **Platform-first** – One governed loop, many domains (NetOps, consumer, and beyond).
- **Local-first** – Runs in your lab. Your devices, your data, your API.
- **Agentic by design** – Built specifically for LLM tool-calling workflows.
- **Governed actions** – Confirm gates, allowlists, and dry-run patterns (implementation-specific).
- **Reproducible environments** – Bootstraps wire the full stack consistently.
- **Open-core** – Clean separation between the lab framework and a future enterprise tier.

---

## What You Get (in this repository)

This repository contains the **NetOps implementation** of the AIMusubi platform. It installs a complete **Level-5 agentic NetOps stack**:

- **AIMusubi API (FastAPI)**
  - `/intent/exec`, `/openapi.json`, `/metrics`, `/health`
- **Vendor Adapters**
  - Cisco RESTCONF (YANG)
  - Arista eAPI (JSON-RPC)
  - VyOS REST / RESTCONF
- **Intent Engine**
  - Vendor-agnostic operations (`iface.list`, `routing.v4.rib`, `ospf.neigh`, etc.)
- **SQLite Memory**
  - Credentials, observations, evolving state
- **Observability**
  - Prometheus metrics + Grafana dashboards
- **LLM Frontend**
  - Open WebUI wired directly to AIMusubi’s OpenAPI schema

> **AIMusubi includes an operator-grade toolchain**  
> (nmap, masscan, fping, SNMP utilities, DNS tools, traceroute, iproute2, etc.)  
> so your environment has the same diagnostic visibility as a real NetOps workflow.  
> **Lab use only.**

All components are installed and wired together via **bare-metal** or **Docker** bootstrap.

---

## NetOps Implementation – Five-Minute Quickstart

> This quickstart bootstraps the **NetOps implementation** of the AIMusubi platform.  
> Other AIMusubi projects (for example, Tesla Gateway) run independently and provide their own setup instructions.

> Full installation details live in `docs/`, but this is the shortest path.

### 1. Clone the repository

```bash
git clone https://github.com/aimusubi/aimusubi.git
cd aimusubi
```

### 2. Choose a bootstrap method

**Bare-metal (Ubuntu 22.04 / 24.04)**

```bash
chmod +x bootstrap/aimusubi_l5_fullstack_baremetal.sh
sudo ./bootstrap/aimusubi_l5_fullstack_baremetal.sh
```

**Docker stack**

```bash
chmod +x bootstrap/aimusubi_l5_fullstack_docker.sh
./bootstrap/aimusubi_l5_fullstack_docker.sh
```

### 3. Activate the system

Follow:

- `docs/post_bootstrap_activation.md`
- `docs/openwebui_setup.md`

Then open Open WebUI, select your LLM, and AIMusubi is ready for tool-calling.

---

## Who Is This For?

- **Network engineers** experimenting with LLM-driven NetOps  
- **Homelab builders** running multi-vendor topologies  
- **SRE / DevOps engineers** exploring agentic workflows  
- **Educators & students** learning real infrastructure automation  
- **IT operators** interested in natural-language operations

AIMusubi is a **lab-first framework**, not a production change-control system.

---

## Project Status

- **Version:** 1.0.0 (Open-Core Lab Release)  
- **Vendors:** Cisco IOS-XE, Arista EOS, VyOS  
- **OS Target:** Ubuntu (bare-metal) + Docker stack  
- **Security Model:** Local lab mode, self-signed certs accepted, HTTP used for analysis  

See:

- `docs/roadmap.md`
- `docs/ARCHITECTURE.md`

---

## Documentation

Start here:

- `docs/overview.md`
- `docs/installation_baremetal.md`
- `docs/installation_docker.md`
- `docs/post_bootstrap_activation.md`
- `docs/openwebui_setup.md`
- `docs/adapters.md`
- `docs/intents_reference.md`

---

## Community & Links

**Join the MusubiAG Discord Community**  
https://discord.gg/xAeXxM5f

- **YouTube – The Agentic Engineer**
- **GitHub Issues** – bugs, ideas, suggestions
- **Roadmap** – `docs/roadmap.md`

---

## Contributing

Contributions are welcome — adapters, intents, dashboards, documentation, and improvements.

See:

- `CONTRIBUTING.md`
- `docs/CHANGELOG.md`

If AIMusubi helps you build, learn, or think differently about operations, that’s the mission.

---

## Software Licensing Notice

AIMusubi communicates with network operating systems exclusively through
standards-based or publicly documented APIs. No proprietary software, firmware,
or intellectual property from any vendor is included in this repository.

Users must supply their own properly licensed network operating system images in
accordance with the terms of their vendor agreements. AIMusubi does not provide,
store, transmit, or facilitate access to any vendor images.

All vendor names and trademarks remain the exclusive property of their respective
owners. AIMusubi is an independent open-source project and has no affiliation
with Cisco, Arista, VyOS, or any other vendor referenced in examples or documentation.
