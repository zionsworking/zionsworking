# Hi, I'm Zion Boggan

**Cybersecurity Analyst and AI Engineer.** I monitor and respond to threats across enterprise environments by day, and I build autonomous systems, open cryptographic protocols, and self-hosted AI infrastructure by night. My work runs on a two-node Proxmox cluster under my own roof, with real workloads, real money, and real code shipping every week.

I am currently open to full-time roles in security engineering, detection engineering, AI engineering, or applied security research. If you are hiring, the fastest way to reach me is the contact line at the bottom of this page.

## Featured Work

### Oversight Protocol
[oversight-protocol/oversight](https://github.com/oversight-protocol/oversight) &middot; [oversightprotocol.dev](https://oversightprotocol.dev) &middot; Apache 2.0

An open protocol for cryptographic data provenance, recipient attribution, and leak detection. Oversight seals documents to named recipients with hybrid post-quantum encryption, three independent watermark layers, and Sigstore Rekor v2 transparency logging. Python reference implementation plus a Rust canonical port across a nine-crate workspace, with cross-language conformance tests proving bit-identical output.

Recent releases:
- **v0.4.8** (April 29, 2026): Patch release that unblocks mobile cross-compile and tightens TLS. The Rust core's 4 GiB ciphertext-size cap now gates to 64-bit targets and falls back to `usize::MAX` on 32-bit, which is what makes the mobile companion's `armv7-linux-androideabi` and `i686-linux-android` builds pass. `rustls-webpki` lifted to 0.103.13 for GHSA-82j2-j2ch-gfr8 (reachable CRL parse panic) and a corrected URI excluded-subtree check. Wire format, manifest, and CLI surface unchanged. Notes at [github.com/oversight-protocol/oversight/releases/tag/v0.4.8](https://github.com/oversight-protocol/oversight/releases/tag/v0.4.8).
- **Mobile beta** (April 26, 2026): The companion verifier app shipped to TestFlight as `v0.1.11`. Repo at [oversight-protocol/oversight-mobile](https://github.com/oversight-protocol/oversight-mobile). Flutter UI on top of the same Rust crates that power the desktop CLI, embedded via [`flutter_rust_bridge`](https://github.com/fzyzcjy/flutter_rust_bridge), so a manifest that verifies on a laptop verifies the same way on a phone, with no second implementation to drift. The whole iOS pipeline runs on GitHub-hosted macOS runners (`macos-26` / Xcode 26 / iOS 26 SDK); no local Mac required. Status page at [oversightprotocol.dev/mobile/](https://oversightprotocol.dev/mobile/). Writeup at [oversightprotocol.dev/blog/mobile-beta.html](https://oversightprotocol.dev/blog/mobile-beta.html).
- **v0.4.7** (April 22, 2026): Registry v1 federation spec hardened against the reference server. Canonicalization algorithm, uniform error envelope, normative endpoint list, and `/evidence` bundle shape all pinned. A 32-check conformance harness at `tests/test_registry_conformance.py` lets any independent operator point at their deployment and claim v1 compatibility. CORS middleware on the live registry so the in-browser inspector can read public endpoints. Writeup at [oversightprotocol.dev/blog/registry-federation-conformance.html](https://oversightprotocol.dev/blog/registry-federation-conformance.html).
- **v0.4.6**: SIEM export module with schema-stable formatters for Splunk HEC, Microsoft Sentinel Log Analytics, and Elastic Common Schema 8.x, plus a Sentinel HMAC signing helper and a read-only SQLite iterator. Operator guide at [docs/SIEM.md](https://github.com/oversight-protocol/oversight/blob/main/docs/SIEM.md).
- **v0.4.5**: L3 semantic watermark safety, document-class defaults, `canonical_content_hash` as a dispute anchor, Tkinter GUI starter, and a public threat model at [oversightprotocol.dev/research/threat-model.html](https://oversightprotocol.dev/research/threat-model.html).
- **v0.4.4**: Nine security findings audited by an external review and fixed under a fail-closed discipline. Writeup at [oversightprotocol.dev/blog/security-hardening.html](https://oversightprotocol.dev/blog/security-hardening.html).
- **v0.5**: Sigstore Rekor v2 integration with DSSE envelopes and hashed recipient keys on the public log.

**Browser Sealed File Inspector** at [oversightprotocol.dev/viewer/](https://oversightprotocol.dev/viewer/). Drag-drop any `.sealed` file to parse the container, verify the issuer Ed25519 signature via WebCrypto, and fully decrypt the classic suite locally using WebCrypto X25519 and HKDF-SHA256 plus a vendored [@noble/ciphers](https://github.com/paulmillr/noble-ciphers) XChaCha20-Poly1305. Post-decrypt SHA-256 is checked against the manifest content hash and a mismatch aborts. Nothing leaves the device unless the user explicitly requests a registry lookup.

Target venue for the formal writeup is USENIX Security Cycle 2. Roadmap gates a broad public launch on hybrid (post-quantum) in-browser decrypt, an Outlook add-in, and a regulated-industry design partner.

### Perseus
[zionsworking/perseus-ai-platform](https://github.com/zionsworking/perseus-ai-platform)

A 20-agent AI orchestration platform that routes natural language commands to specialized agents across a self-hosted homelab. Multi-LLM integration (Grok/xAI, OpenAI, local Ollama) with runtime model switching, SSH-based infrastructure management, Discord command and control, web search, and real-time health monitoring. FastAPI plus PostgreSQL backend. Runs production workloads against my Proxmox cluster.

### Hermes Trading Bot (private)
Autonomous AI-powered trading system for Kalshi prediction markets. Three independent scanners, two-pass model verification, self-improving calibration via Brier scores, GPU-accelerated embeddings, NWS weather integration, and fractional Kelly sizing. 4,400 plus lines of Python, trading real money 24 by 7 on my own account. Code is private; outcomes and PnL are tracked internally.

### Flywheel (private)
Autonomous offensive security platform for authorized engagements and research. Private repository, scope-bounded, no shared details in public.

## Current Focus

- Hardening the Oversight mobile verifier: external TestFlight invitations after the iOS 26 SDK migration settles, reproducible mobile builds so anyone can confirm the App Store binary matches the source, and a v2 signer with hardware-backed keys (Secure Enclave on iOS, StrongBox on Android).
- Shipping Oversight past the public-launch gate: hybrid (post-quantum) in-browser decrypt, an Outlook add-in as the first ecosystem integration, a Rust Axum registry port with migration tooling from the Python reference, and the hardware `KeyProvider` trait (YubiKey, Nitrokey, OnlyKey).
- Continuing the spec work: `docs/spec/registry-v1.md` is published and hardened; next is an arXiv preprint and a draft IETF Internet-Draft.
- Bug bounty recon work on authorized programs, with tooling I maintain in private.
- Studying for the next cert rung: AWS Security Specialty and OSCP are both on the near-term list.

## Roadmap

**Next 6 months**
- Oversight mobile v2: signer mode with Secure Enclave / StrongBox-backed keys, F-Droid release, and reproducible builds.
- Oversight hybrid decrypt in the browser via a wasm build of liboqs.
- Outlook add-in and one regulated-industry design-partner deployment.
- Hardware `KeyProvider` trait with `FileKeyProvider` and `PivKeyProvider` implementations.
- Conference submissions: USENIX Security Cycle 2 paper, Black Hat Europe 2026 CFP.

**12 months and beyond**
- Independent security audit of Oversight (Trail of Bits, NCC Group, Cure53, or Zellic).
- Oversight v1.0 release with spec freeze and RFC shepherding.
- ISO 27001 after SOC 2 Type 2.
- Continued specialization in detection engineering and applied cryptography.

## Stack

**Languages:** Python, Rust, Dart (Flutter), TypeScript, JavaScript (WebCrypto), Bash, SQL
**Backend:** FastAPI, Axum, Tokio, PostgreSQL, SQLite, REST and WebSocket APIs, DSSE, JWS, RFC 3161, RFC 6962 Merkle transparency
**Applied cryptography:** X25519, Ed25519, XChaCha20-Poly1305, HKDF-SHA256, ML-KEM-768 (FIPS 203), ML-DSA-65 (FIPS 204), Sigstore Rekor v2
**AI / ML:** Grok and xAI Responses API, Anthropic Claude, OpenAI, local Ollama (qwen3, nomic-embed-text), vector search, GPU-accelerated inference
**Security:** SOC operations, incident response, Microsoft Sentinel, SentinelOne, Splunk HEC and Elastic Common Schema export, threat hunting, detection engineering, authorized offensive tooling
**Mobile:** Flutter, `flutter_rust_bridge`, iOS (TestFlight, fastlane, App Store Connect API), Android (PKCS12 signing, AAB / APK), CI-only build pipelines on GitHub-hosted macOS runners
**Infrastructure:** Proxmox VE, LXC, GPU passthrough, WireGuard, Pi-hole, Proxmox Backup Server, systemd, Cloudflare Tunnel, GitHub Pages, GitHub Actions

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
- LinkedIn: [linkedin.com/in/zion-boggan](https://www.linkedin.com/in/zion-boggan)
- Project site: [oversightprotocol.dev](https://oversightprotocol.dev)

If you are a recruiter or hiring manager, the quickest read on my current work is the Oversight blog index at [oversightprotocol.dev/blog/](https://oversightprotocol.dev/blog/). If you want to talk about a role, email me directly and mention the role in the subject line so I can prioritize.
