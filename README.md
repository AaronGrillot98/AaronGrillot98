# Hi, I'm Aaron 👋

**DevSecOps · Cloud Security · AI Security · Aerospace Systems**

I build security-focused projects that cover the full lifecycle: **prevent → detect → analyze → understand impact**. My aviation maintenance background gives me a systems-and-safety lens on cybersecurity — I think about how things fail in the real world, not just whether a tool runs green.

📍 Available for full-time DevSecOps / Cloud Security / AI Security / Defense / forward-deployed Tech Ops roles
🔗 [LinkedIn](https://linkedin.com/in/aarongrillot)

---

## 🎯 Focus areas

- **AI / LLM security** — prompt-injection / jailbreak detection, two-stage defense pipelines (regex + LLM-judge), output-side PII redaction, OpenAI-compatible proxies, integrations with LangChain / LiteLLM / FastAPI
- **DevSecOps & CI/CD security** — Sigstore keyless signing, SLSA Build provenance, signed SBOMs, OIDC-only deploys, fail-closed scanners
- **Cloud security** — AWS hardening (IAM least privilege, S3 BucketOwnerEnforced + SecureTransport deny, CloudFront OAC), Terraform IaC, runtime hardening (PSS-restricted Kubernetes)
- **Compliance literacy** — NIST SP 800-53 Rev. 5, NIST SP 800-171 Rev. 2 / CMMC 2.0 L2, NIST SSDF v1.1, SLSA v1.0
- **Forward-deployed / DDIL** — single static Go binaries, atomic-swap installs, cryptographic update verification, intermittent-connectivity tolerance
- **Aerospace cyber risk** — mapping cyber threats to operational impact on maintenance, inventory, scheduling, and ground systems

---

## ⚒️ Featured: Mithril — a firewall for LLMs

<a href="https://github.com/AaronGrillot98/mithril">
  <img src="https://raw.githubusercontent.com/AaronGrillot98/mithril/main/docs/banner.png" alt="Mithril — a firewall for LLMs" />
</a>

[![PyPI](https://img.shields.io/pypi/v/mithril-llm?logo=pypi&logoColor=white&label=pypi&color=4c83cf)](https://pypi.org/project/mithril-llm/)
[![Downloads](https://img.shields.io/pypi/dm/mithril-llm?color=4c83cf)](https://pypi.org/project/mithril-llm/)
[![CI](https://github.com/AaronGrillot98/mithril/actions/workflows/ci.yml/badge.svg)](https://github.com/AaronGrillot98/mithril/actions/workflows/ci.yml)
[![Tests](https://img.shields.io/badge/tests-167%20passing-brightgreen.svg)](https://github.com/AaronGrillot98/mithril#validation)
[![Coverage](https://img.shields.io/badge/coverage-88%25-brightgreen.svg)](https://github.com/AaronGrillot98/mithril#validation)
[![JailbreakBench](https://img.shields.io/badge/JailbreakBench-100%25-brightgreen.svg)](https://github.com/AaronGrillot98/mithril#benchmarks)

**Self-hosted OpenAI-compatible reverse proxy that scans LLM traffic in both directions.** Stops prompt injection, jailbreaks, and PII exfiltration at the gateway — *what nginx is to web traffic, Mithril is to LLM prompts.*

- ✅ **100% recall / 100% precision** on the [JailbreakBench](https://jailbreakbench.github.io/) corpus (NeurIPS 2024) with the harmful behaviors wrapped in real-world jailbreak frames
- ✅ **Bi-directional firewall** — scans user prompts (attack technique) AND model responses (PII / secret / credential leakage). Block / redact / log modes on the output side
- ✅ **Two-stage defense** — sub-millisecond regex pipeline + optional LLM-judge fallback for the ambiguous middle (~5% of traffic). Works with OpenAI, Anthropic, Ollama, vLLM, llama.cpp — fully air-gapped if you want
- ✅ **Drop-in integrations** for LangChain, LiteLLM, FastAPI — one import line firewalls your existing stack
- ✅ **167 tests · 88% coverage · ruff clean**, automated PyPI + GHCR multi-arch publish on every tag, six green install paths (pip / docker / docker-compose / one-line shell / source)

```bash
pip install mithril-llm
mithril serve
# → http://localhost:8080  (dashboard at /)
```

Built end-to-end: regex rule engine, async judge with HTTP error handling, FastAPI proxy with body-size + header-leak protections, SQLite event log with async wrappers, request-ID correlation middleware, three framework integration packages, JailbreakBench evaluation harness, and a Mithril-themed dashboard.

---

## 🛡️ Featured: connected supply-chain trust portfolio

**Three repos, one story** — supply-chain trust from CI to forward-deployed edge.

```text
  TalonEdge-Secure-Deploy  ──→   sarif-merge   ──→  field-update-agent
       (CI signs)               (consolidates           (field consumes
                                  CI findings)            signed artifacts)
```

Each one is a real, tested, CI-green repo. They're separate but interoperable: TalonEdge produces the SBOM-attested + SLSA-provenanced artifacts; sarif-merge collapses the five-scanner output of TalonEdge's Security CI into one PR comment; field-update-agent runs on a forward-deployed device and consumes TalonEdge's signed artifacts under DDIL conditions.

### 1. [TalonEdge-Secure-Deploy](https://github.com/AaronGrillot98/TalonEdge-Secure-Deploy)

[![SLSA Build L3](https://img.shields.io/badge/SLSA-Build%20L3-success)](https://github.com/AaronGrillot98/TalonEdge-Secure-Deploy/blob/main/docs/COMPLIANCE.md#slsa-v10--build-track)
[![NIST 800-53](https://img.shields.io/badge/NIST%20800--53-22%20controls-blue)](https://github.com/AaronGrillot98/TalonEdge-Secure-Deploy/blob/main/docs/COMPLIANCE.md)
[![NIST 800-171 / CMMC L2](https://img.shields.io/badge/NIST%20800--171%20%2F%20CMMC%20L2-22%20reqs-blue)](https://github.com/AaronGrillot98/TalonEdge-Secure-Deploy/blob/main/docs/COMPLIANCE.md)
[![SSDF](https://img.shields.io/badge/NIST%20SSDF-11%20practices-blue)](https://github.com/AaronGrillot98/TalonEdge-Secure-Deploy/blob/main/docs/COMPLIANCE.md)

A forward-deployed secure-edge platform. Verifies software end-to-end through a real cryptographic chain — Sigstore (Fulcio + Rekor) keyless signatures, CycloneDX SBOM attestations, and SLSA v1 Build Provenance — then publishes an operator report through an OIDC-only AWS pipeline. **Zero long-lived secrets anywhere.**

- ✅ SLSA Build L3 **verified live in CI** (cosign + independent Python re-verifier)
- ✅ NIST 800-53 / 800-171 / SSDF mapped to file-and-line evidence
- ✅ Production environment gate (required reviewer + branch protection)
- ✅ 71 negative-path tests including type-confusion attacks on attestation predicates
- ✅ Hardened AWS Terraform + PSS-restricted Kubernetes

### 2. [sarif-merge](https://github.com/AaronGrillot98/sarif-merge)

[![CI](https://github.com/AaronGrillot98/sarif-merge/actions/workflows/ci.yml/badge.svg)](https://github.com/AaronGrillot98/sarif-merge/actions/workflows/ci.yml)
[![Python 3.11+](https://img.shields.io/badge/python-3.11%2B-blue)](https://github.com/AaronGrillot98/sarif-merge)
[![SARIF v2.1.0](https://img.shields.io/badge/SARIF-v2.1.0-success)](https://github.com/AaronGrillot98/sarif-merge)

Multi-scanner SARIF consolidator. Reads **Bandit + Semgrep + Trivy + gitleaks + tfsec** output, deduplicates overlapping findings via two-phase clustering, and bumps severity when ≥2 scanners independently agree. Replaces five scanner tabs with one prioritized PR comment.

- ✅ **Wired live** into TalonEdge's Security CI as a `merge` job
- ✅ Stable PR-comment marker — re-runs update the same comment, never stack
- ✅ 48 tests covering scanner-vocabulary normalization + every CLI failure mode
- ✅ **Zero runtime third-party deps** — pure stdlib Python

### 3. [field-update-agent](https://github.com/AaronGrillot98/field-update-agent)

[![CI](https://github.com/AaronGrillot98/field-update-agent/actions/workflows/ci.yml/badge.svg)](https://github.com/AaronGrillot98/field-update-agent/actions/workflows/ci.yml)
[![Go 1.22+](https://img.shields.io/badge/go-1.22%2B-00ADD8)](https://github.com/AaronGrillot98/field-update-agent)
[![Cross-compile](https://img.shields.io/badge/cross--compile-5%20targets-success)](https://github.com/AaronGrillot98/field-update-agent/actions)

**Sigstore-verifying update agent for forward-deployed devices**, written in Go. Single static binary, ARM-cross-compilable. Polls a signed manifest under intermittent connectivity, atomically swaps payloads via a `current` symlink, runs a configurable health check, and auto-rolls-back on failure.

- ✅ **DDIL failure-mode matrix** documented + tested (`docs/DESIGN.md`)
- ✅ Cross-compiles to linux/amd64, linux/arm64, linux/arm v7, darwin/amd64, darwin/arm64 — all 5 produced as CI artifacts
- ✅ 45 tests with race detector clean; survives 30-day blackouts via SHA-256-checksummed JSON state
- ✅ Consumes TalonEdge's signed artifacts → end-to-end supply-chain trust from CI to edge

---

## 🔧 Also shipped

- **[k8s-secure-secrets-lab](https://github.com/AaronGrillot98/k8s-secure-secrets-lab)** — Hands-on Kubernetes secrets handling: deploy a sample app, manage secrets securely, convert plain Kubernetes Secrets into SealedSecrets, keep sensitive data out of git history.

---

## 🚧 Currently building

- **[aviation-cyber-risk-mapping](https://github.com/AaronGrillot98/aviation-cyber-risk-mapping)** — Mapping cyber threats to operational impact on maintenance, inventory, scheduling, and ground aviation systems.
- **[Endpoint-Detection-Lab](https://github.com/AaronGrillot98/Endpoint-Detection-Lab)** — Detection-engineering lab focused on endpoint behaviors and noisy-vs-actionable signal tuning.
- **[AeroLedger](https://github.com/AaronGrillot98/AeroLedger)** — Aircraft awareness + tracking application; data-pipeline + frontend.
- **[IPhone-Cloud-Project](https://github.com/AaronGrillot98/IPhone-Cloud-Project)** — Doing cloud-security workflows from a phone: experiments in mobile-only ops.
- **[iOS-Cybersecurity-Toolkit](https://github.com/AaronGrillot98/iOS-Cybersecurity-Toolkit)** — Toolkit for security work on iOS — proxying, traffic analysis, configuration review.

---

## 💡 What makes me different

- **Aviation maintenance background** → real systems-and-safety mindset, not just CTF-style thinking
- **Focus on *why* systems fail**, not only what tools detect
- **Compliance-literate without being compliance-only** — I read NIST controls and trace them to specific files; I don't paste them as wallpaper
- **Polyglot, deliberately** — Python for tooling and CI, Go for forward-deployed agents, Terraform/HCL for cloud infra, JSON Schema / SARIF for interop
- **Ship, don't just prototype** — Mithril is published on PyPI and GHCR, TalonEdge's SLSA chain runs in CI on every push, sarif-merge is wired live into a real Security CI

---

## 📫 Get in touch

- LinkedIn: [aarongrillot](https://linkedin.com/in/aarongrillot)
- Email: aarongrill98 at gmail dot com
- This profile: [AaronGrillot98](https://github.com/AaronGrillot98)
