# Hi, I'm Aaron 👋

**DevSecOps · Cloud Security · Aerospace Systems**

I build security-focused projects that cover the full lifecycle: **prevent → detect → analyze → understand impact**. My aviation maintenance background gives me a systems-and-safety lens on cybersecurity — I think about how things fail in the real world, not just whether a tool runs green.

📍 Available for full-time DevSecOps / Cloud Security / Defense roles
🔗 [LinkedIn](https://linkedin.com/in/aarongrillot)

---

## 🎯 Focus areas

- **DevSecOps & CI/CD security** — Sigstore keyless signing, SLSA Build provenance, signed SBOMs, OIDC-only deploys, fail-closed scanners
- **Cloud security** — AWS hardening (IAM least privilege, S3 BucketOwnerEnforced + SecureTransport deny, CloudFront OAC), Terraform IaC, runtime hardening (PSS-restricted Kubernetes)
- **Compliance literacy** — NIST SP 800-53 Rev. 5, NIST SP 800-171 Rev. 2 / CMMC 2.0 L2, NIST SSDF v1.1, SLSA v1.0
- **Aerospace cyber risk** — mapping cyber threats to operational impact on maintenance, inventory, scheduling, and ground systems

---

## 🛡️ Featured project — TalonEdge Secure Deploy

[![SLSA Build L3](https://img.shields.io/badge/SLSA-Build%20Level%203-success)](https://github.com/AaronGrillot98/TalonEdge-Secure-Deploy/blob/main/docs/COMPLIANCE.md#slsa-v10--build-track)
[![NIST 800-53](https://img.shields.io/badge/NIST%20800--53-22%20controls-blue)](https://github.com/AaronGrillot98/TalonEdge-Secure-Deploy/blob/main/docs/COMPLIANCE.md#nist-800-53-rev-5-control-mapping)
[![NIST 800-171](https://img.shields.io/badge/NIST%20800--171%20%2F%20CMMC%20L2-22%20requirements-blue)](https://github.com/AaronGrillot98/TalonEdge-Secure-Deploy/blob/main/docs/COMPLIANCE.md#nist-800-171-rev-2--cmmc-20-level-2-mapping)
[![SSDF](https://img.shields.io/badge/NIST%20SSDF-11%20practices-blue)](https://github.com/AaronGrillot98/TalonEdge-Secure-Deploy/blob/main/docs/COMPLIANCE.md#nist-800-218-ssdf-v11-practice-mapping)

**[github.com/AaronGrillot98/TalonEdge-Secure-Deploy →](https://github.com/AaronGrillot98/TalonEdge-Secure-Deploy)**

A forward-deployed secure-edge platform. Verifies software end-to-end through a real cryptographic chain — Sigstore (Fulcio + Rekor) keyless signatures, CycloneDX SBOM attestations, and SLSA v1 Build Provenance — then publishes an operator report through an OIDC-only AWS pipeline. Zero long-lived secrets anywhere.

- ✅ SLSA Build L3 verified live in CI (cosign + independent Python re-verifier)
- ✅ Mapped to NIST 800-53 / 800-171 / SSDF, with file:line evidence per control
- ✅ Real fail-closed Security CI: Bandit, pip-audit, gitleaks, tfsec, Trivy fs
- ✅ Production environment gate (required reviewer + branch protection)
- ✅ Hardened AWS Terraform + PSS-restricted Kubernetes
- ✅ 71 negative-path tests including type-confusion attacks on the attestation predicate

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

---

## 📫 Get in touch

- LinkedIn: [aarongrillot](https://linkedin.com/in/aarongrillot)
- Email: aarongrill98 at gmail dot com
- This profile: [AaronGrillot98](https://github.com/AaronGrillot98)
