# Hi, I'm Zion Boggan

**Cybersecurity Analyst and AI Engineer.** I monitor and respond to threats across enterprise environments by day, and I build autonomous systems, open cryptographic protocols, and self-hosted AI infrastructure by night. My work runs on a two-node Proxmox cluster under my own roof, with real workloads, real money, and real code shipping every week.

I am currently open to full-time roles in security engineering, detection engineering, AI engineering, or applied security research. If you are hiring, the fastest way to reach me is the contact line at the bottom of this page.

## Featured Work

### Oversight Protocol
[oversight-protocol/oversight](https://github.com/oversight-protocol/oversight) &middot; [oversightprotocol.dev](https://oversightprotocol.dev) &middot; Apache 2.0

An open protocol for cryptographic data provenance, recipient attribution, and leak detection. Oversight seals documents to named recipients with hybrid post-quantum encryption, three independent watermark layers, and Sigstore Rekor v2 transparency logging. Python reference implementation at 5,689 LOC; Rust canonical port at 2,934 LOC across seven crates, with a cross-language conformance suite proving bit-identical output.

Recent releases:
- **v0.4.5** (April 2026): L3 semantic watermark safety, document-class defaults, `canonical_content_hash` as a dispute anchor, Tkinter GUI starter, and a public threat model at [oversightprotocol.dev/research/threat-model.html](https://oversightprotocol.dev/research/threat-model.html).
- **v0.4.4**: Nine security findings audited by an external review and fixed under a fail-closed discipline. Writeup at [oversightprotocol.dev/blog/security-hardening.html](https://oversightprotocol.dev/blog/security-hardening.html).
- **v0.5**: Migrated from a self-hosted Merkle tree to Sigstore Rekor v2 with DSSE envelopes and hashed recipient keys on the public log.

Target venue for the formal writeup is USENIX Security. Roadmap gates a broad public launch on a non-CLI user experience (web viewer, Outlook add-in) and a regulated-industry design partner.

### Perseus
[zionsworking/perseus-ai-platform](https://github.com/zionsworking/perseus-ai-platform)

A 20-agent AI orchestration platform that routes natural language commands to specialized agents across a self-hosted homelab. Multi-LLM integration (Grok/xAI, OpenAI, local Ollama) with runtime model switching, SSH-based infrastructure management, Discord command and control, web search, and real-time health monitoring. FastAPI + PostgreSQL backend. Runs production workloads against my Proxmox cluster.

### Hermes Trading Bot (private)
Autonomous AI-powered trading system for Kalshi prediction markets. Three independent scanners, two-pass model verification, self-improving calibration via Brier scores, GPU-accelerated embeddings, NWS weather integration, and fractional Kelly sizing. 4,400+ lines of Python, trading real money 24/7 on my own account. Code is private; outcomes and PnL are tracked internally.

### Flywheel (private)
Autonomous offensive security platform for authorized engagements and research. Private repository, scope-bounded, no shared details in public.

## Current Focus

- Shipping the Oversight v0.5 cycle: web viewer, Outlook add-in, registry federation spec (`docs/spec/registry-v1.md`), and a SIEM export path (Splunk HEC, Microsoft Sentinel, Elastic Common Schema) ahead of SOC 2 Type 1 scoping.
- Expanding Perseus toward multi-tenant agent orchestration and a cleaner eval harness.
- Bug bounty recon work on authorized programs, with tooling I maintain in private.
- Studying for the next cert rung: AWS Security Specialty and OSCP are both on the near-term list.

## Roadmap

**Next 6 months**
- Oversight v0.5 web viewer and drag-drop share workflow.
- Regulated-industry design-partner deployment for Oversight.
- Conference submissions: USENIX Security Cycle 2 paper, Black Hat Europe 2026 CFP.
- Hardware key provider (YubiKey, Nitrokey) integration for Oversight's Rust KeyProvider trait.

**12 months and beyond**
- Independent security audit of Oversight (Trail of Bits, NCC Group, Cure53, or Zellic).
- Oversight v1.0 release with spec freeze and RFC shepherding.
- Continued specialization in detection engineering and applied cryptography.

## Stack

**Languages:** Python, Rust, TypeScript, Bash, SQL
**Backend:** FastAPI, Axum, Tokio, PostgreSQL, SQLite, REST and WebSocket APIs, DSSE, JWS, RFC 3161
**AI / ML:** Grok and xAI Responses API, Anthropic Claude, OpenAI, local Ollama (qwen3, nomic-embed-text), vector search, GPU-accelerated inference
**Security:** SOC operations, incident response, Microsoft Sentinel, SentinelOne, threat hunting, detection engineering, authorized offensive tooling, hybrid post-quantum cryptography (X25519 + ML-KEM-768, Ed25519 + ML-DSA-65)
**Infrastructure:** Proxmox VE, LXC, GPU passthrough, WireGuard, Pi-hole, Proxmox Backup Server, systemd, Cloudflare, GitHub Pages, GitHub Actions

## Certifications

- CompTIA Security+ (DoD 8570 IAT Level II)
- SentinelOne Incident Responder
- Microsoft Security Operations Analyst Associate (SC-200)
- Microsoft Azure Administrator Associate (AZ-104)
- Microsoft Azure Fundamentals (AZ-900)

## Background

I come to security from an operator mindset. Before my current SOC role, I spent years building and breaking things on my own hardware, which is how I learned what a useful alert looks like before I ever had to write one. That same operator instinct shows up in everything I build publicly: Oversight is what happens when someone who watches leaks every day designs a provenance protocol; Perseus is what happens when someone responsible for their own homelab decides an AI should run it.

I write in public because I want my work to be verifiable. Every measurement on the Oversight site is a mean of ten runs on known hardware. Every security finding has a public fix commit. If a claim on any of my pages turns out to be wrong, I want an auditor to be able to prove it.

## Contact

- Email: **zionboggan@gmail.com**
- GitHub: [@zionsworking](https://github.com/zionsworking)
- Project site: [oversightprotocol.dev](https://oversightprotocol.dev)

If you are a recruiter or hiring manager, the quickest read on my current work is the Oversight blog index at [oversightprotocol.dev/blog/](https://oversightprotocol.dev/blog/). If you want to talk about a role, email me directly and mention the role in the subject line so I can prioritize.
