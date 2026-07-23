# ZarishSphere
> **Universal, Sovereign, Open-Source, Operating System of Global Standards & Zero-Cost Infrastructure for Human Civilization**

[![GitHub](https://img.shields.io/badge/zsdotcom/zarishsphere-181717?logo=github)](https://github.com/zsdotcom/zarishsphere)
[![OKF Specification](https://img.shields.io/badge/OKF-v0.1-0284C7.svg)](https://github.com/zarishsphere)
[![ZUSS Specification](https://img.shields.io/badge/ZUSS-v1.2-0D9488.svg)](https://github.com/zarishsphere)
[![License: Code](https://img.shields.io/badge/License_Code-Apache_2.0-green.svg)](LICENSE)
[![License: Docs](https://img.shields.io/badge/License_Docs-CC_BY_4.0-blue.svg)](LICENSE-DOCS)
[![Runtime Constraint](https://img.shields.io/badge/JVM_Dependencies-0%25-red.svg)](#3-baseline-hardware--runtime-constraints)
[![Status](https://img.shields.io/badge/Status-V1_Stable-brightgreen.svg)](#10-governance-and-foundation-mandate)
[![CI](https://github.com/zsdotcom/zarishsphere/actions/workflows/ci.yml/badge.svg)](https://github.com/zsdotcom/zarishsphere/actions/workflows/ci.yml)


---

## Table of contents

1. [Executive Summary](#1-executive-summary)
2. [Purpose and scope](#2-purpose-and-scope)
3. [Executive architectural alignment](#2-executive-architectural-alignment)
4. [Monorepo Structural Zones (Folder Taxonomy)](#4-monorepo-structural-zone-and-folder-taxonomy)  
5. [Baseline hardware boundaries](#5-baseline-hardware-boundaries)
6. [Static-first governance model](#6-static-first-governance-model)


7. [Open Knowledge Format (OKF) v0.1 as SSOT](#5-open-knowledge-format-okf-v01-as-ssot)
8. [MCP integration for local AI interactivity](#6-mcp-integration-for-local-ai-interactivity)
9. [ADK and local agent session architecture](#7-adk-and-local-agent-session-architecture)
10. [Agent2Agent (A2A) capability discovery](#8-agent2agent-a2a-capability-discovery)
11. [Separation of concerns: structural zones](#9-separation-of-concerns-structural-zones)
12. [Sandbox environment and validation pipeline](#10-sandbox-environment-and-validation-pipeline)
13. [CI/CD governance and compliance automation](#11-ci-cd-governance-and-compliance-automation)
14. [Implementation checklist](#12-implementation-checklist)

---

## 1. Executive Summary

The ZarishSphere Foundation maintains this documentation monorepo as the single, authoritative source of truth for the entire ZarishSphere ecosystem. ZarishSphere is a universal, open-source, zero-cost, no-code platform designed to index every global standard across human civilization and transform them into executable digital assets (forms, workflows, microservices, and decision engines) deployable from air-gapped single devices up to global multi-region cloud tiers.

This repository serves as both the governance engine and the technical documentation hub for all zs-* repositories, implementing a static-first, agent-native architecture governed by the ZarishSphere Universal Serialization Standard (ZUSS) and the Open Knowledge Format (OKF v0.1).

This repository serves as both the **governance engine** and the **technical documentation hub** for all zs-* repositories, implementing a static-first, agent-native architecture governed by the **ZarishSphere Universal Serialization Standard (ZUSS)** and the **Open Knowledge Format (OKF v0.1)**.

---

## 2. Purpose and scope

This blueprint defines the ZarishSphere monorepo’s architecture, governance controls, and operational boundaries for deployment on modest local hardware.

It establishes a single, declarative, static-first workstream for:

- governance and policy documents
- metadata schemas and validation rules
- agent-native tooling and local AI integration
- operational procedures for offline-first environments

> **Constraint:** The monorepo must not require heavy background VMs, proprietary database engines, or memory-intensive orchestration frameworks to provide its governance and validation functionality.


## 3. Executive architectural alignment

The ZarishSphere monorepo is aligned with the foundation’s core architecture principles:

- **Governance-first:** Every repository, module, and tool path is defined in markdown before any runtime implementation exists.
- **Static source of truth:** All operational state is encoded as flat files rather than a running metadata registry.
- **Offline capability:** The system must work locally on a workstation with intermittent or no internet.
- **Agent-nativity:** Documents are structured for direct consumption by AI agents using MCP.

This architecture is intentionally conservative: it trades dynamic runtime flexibility for deterministic, low-footprint operational safety.

## 4. Monorepo Structural Zones and Folder Taxonomy

This monorepo follows the OKF v0.1 and ZUSS folder structure. Every folder begins with a 3-digit zero-padded prefix.  

```text
zarishsphere/  
| .github/
|  ├── workflows/                        ← Monorepo progressive disclosure map  
|  ├── log.md                             ← Chronological change registry (ISO 8601)  
|  ├── zs-meta/                           ← System architecture, constitution, and blueprints  
|  ├── zs-foundation/                     ← Institutional profile, governance rules, and charter  
|  ├── zs-platform/                       ← Platform engine specifications and G2A mechanics  
| .vscode/
|  ├── index.md                           ← Monorepo progressive disclosure map  
|  ├── log.md                             ← Chronological change registry (ISO 8601)  
|  ├── zs-meta/                           ← System architecture, constitution, and blueprints  
|  ├── zs-foundation/                     ← Institutional profile, governance rules, and charter  
|  ├── zs-platform/                       ← Platform engine specifications and G2A mechanics
| .devcontainer/
|  ├── index.md                           ← Monorepo progressive disclosure map  
|  ├── log.md                             ← Chronological change registry (ISO 8601)  
|  ├── zs-meta/                           ← System architecture, constitution, and blueprints  
|  ├── zs-foundation/                     ← Institutional profile, governance rules, and charter  
|  ├── zs-platform/                       ← Platform engine specifications and G2A mechanics  
| public/
|  ├── index.md                           ← Monorepo progressive disclosure map  
|  ├── log.md                             ← Chronological change registry (ISO 8601)  
|  ├── zs-meta/                           ← System architecture, constitution, and blueprints  
|  ├── zs-foundation/                     ← Institutional profile, governance rules, and charter  
|  ├── zs-platform/                       ← Platform engine specifications and G2A mechanics  
| agents/
|  ├── index.md                           ← Monorepo progressive disclosure map  
|  ├── log.md                             ← Chronological change registry (ISO 8601)  
|  ├── zs-meta/                           ← System architecture, constitution, and blueprints  
|  ├── zs-foundation/                     ← Institutional profile, governance rules, and charter  
|  ├── zs-platform/                       ← Platform engine specifications and G2A mechanics  
| mcp/
|  ├── index.md                           ← Monorepo progressive disclosure map  
|  ├── log.md                             ← Chronological change registry (ISO 8601)  
|  ├── zs-meta/                           ← System architecture, constitution, and blueprints  
|  ├── zs-foundation/                     ← Institutional profile, governance rules, and charter  
|  ├── zs-platform/                       ← Platform engine specifications and G2A mechanics  
| docs/
|  ├── index.md                           ← Monorepo progressive disclosure map  
|  ├── log.md                             ← Chronological change registry (ISO 8601)  
|  ├── zs-meta/                           ← System architecture, constitution, and blueprints  
|  ├── zs-foundation/                     ← Institutional profile, governance rules, and charter  
|  ├── zs-platform/                       ← Platform engine specifications and G2A mechanics  
|  ├── zs-index/                          ← ZarishIndex taxonomy, schema rules, and ingestion specs  
|  ├── zs-standards/                      ← ZarishStandards transformation maps and form models  
|  ├── zs-infrastructure/                 ← Multi-plane deployment scripts and Cloudflare configurations  
|  ├── zs-tech-stack/                     ← Master tech inventory, writing rules (ZUSS), and OSS catalog  
|  ├── zs-adrs/                           ← Architecture Decision Records (ADRs)  
|  ├── zs-operations/                     ← Operational SOPs, field runbooks, and disaster recovery  
|  └── zs-ecosystem/                      ← Component specs (Console, Marketplace, Builder, Apps)
| scripts/
|  ├── index.md                           ← Monorepo progressive disclosure map  
|  ├── log.md                             ← Chronological change registry (ISO 8601)  
|  ├── zs-meta/                           ← System architecture, constitution, and blueprints  
|  ├── zs-foundation/                     ← Institutional profile, governance rules, and charter  
|  ├── zs-platform/                       ← Platform engine specifications and G2A mechanics  
├── .gitignore                            ← Monorepo landing page (tooling-reserved)
├── BLUEPRINT.md                          ← Monorepo landing page (tooling-reserved)
├── README.md                             ← Monorepo landing page (tooling-reserved)
├── AGENTS.md                             ← Monorepo landing page (tooling-reserved)
```

---

## **5. Hardware Boundaries & Resource Constraints**

All ecosystem tools must execute deterministically on low-cost local hardware without external cloud dependencies.

### **Target Hardware Baseline**

> * **Processor:** Intel Core i5 or equivalent ARM64 board (e.g., Raspberry Pi 5\)  
> * **Memory:** 8 GB RAM total system capacity  
> * **Storage:** 512 GB SSD (or high-speed NVMe/SD edge storage)  
> * **OS Compatibility:** Ubuntu 26.04 LTS, Linux-Mint 22.3 Cinnamon, Linux-Lite 7.8

### **Operational Memory Limits**

> * Idle governance layer footprint: ![][image4] RAM overhead (static flat files).  
> * Individual background microservices: ![][image5] RAM operational allocation.  
> * **Strict Prohibition:** JVM runtimes (e.g., HAPI FHIR Java servers), Kubernetes clusters, and heavy background VM daemons are explicitly banned from the core execution path.

## **6. Five Infrastructure Deployment Planes**

Every platform feature must operate across all five infrastructure planes without core logic modification.

| Plane | Deployment Type | Environment | Operational Capability |
| :---- | :---- | :---- | :---- |
| **Plane 0** | Air-gapped | Single local device / hand-carried tablet | Fully offline, zero internet requirement |
| **Plane 1** | Local Edge | Raspberry Pi 5 / LAN server | Local Wi-Fi network routing, offline sync queues |
| **Plane 2** | District Node | Intermittent connectivity field office | Asynchronous batch sync, SQLite WAL persistence |
| **Plane 3** | National Cloud | Regional cloud data center | High-availability tenant storage |
| **Plane 4** | Global SaaS | Multi-region Cloudflare / Edge network | Global distribution and automated deployment |


## **7. Agent-Native Architecture (OKF, MCP, ADK, A2A)**

The monorepo is engineered for direct ingestion and manipulation by AI agents.  
graph TD  
    A\[Layer 1: Knowledge Storage \- OKF v0.1\] \--\>|Context Grounding| B\[Layer 2: Local Interactivity \- MCP\]  
    B \--\>|Capabilities Exposure| C\[Layer 3: Agent Orchestration \- ADK\]  
    C \--\>|Capability Handoff| D\[Layer 4: Network Interoperability \- A2A\]

> 1. **Open Knowledge Format (OKF v0.1):** Machine-readable YAML frontmatter embedded on all Class B documents.  
> 2. **Model Context Protocol (MCP):** Exposes documentation, validation tools, and search tools directly to AI hosts over standard stdio and streamable HTTP.  
> 3. **Agent Development Kit (ADK):** Lightweight Python/Go runners coordinating short-lived local sessions.  
> 4. **Agent2Agent (A2A) Discovery:** Exposes system capabilities via standard JSON cards located at /.well-known/agent-card.json.

## **8. Production Tech Stack Summary**

| Layer | Technology | Operational Specification |
| :---- | :---- | :---- |
| **Backend Language** | Go 1.26.4 | Statically compiled binaries, low memory footprint (![][image6]) |
| **HTTP Router** | Chi (go-chi/v5) | Idiomatic, zero-allocation Go HTTP routing |
| **Database Store** | SQLite 3.46+ | Embedded database operating in Write-Ahead Logging (WAL) mode |
| **Healthcare Standard** | zs-fhir-go | Go-native FHIR R5 implementation (Zero JVM) |
| **Frontend UI** | React 19.3 / Next.js 16/15 | Server Actions, Partial Pre-Rendering (PPR), Shadcn UI |
| **Styling Engine** | Tailwind CSS 4.3 | CSS-first @theme design token definitions |
| **Analytical Store** | Apache Parquet / Arrow | Columnar batch data processing for zero-cost analytics |

## **9. Local Validation & CI/CD Pipeline**

The monorepo relies on static-first build checks to enforce document consistency and metadata validation.

### **Local Execution Chain**

Run these scripts prior to submitting pull requests:  
\# Refresh system file manifests  
python3 scripts/010-refresh-files.py

\# Validate ZUSS rule compliance (filenames, headers, math syntax, banned words)  
bash scripts/001-zuss-validate.sh

\# Verify data pipeline status and schema definitions  
bash scripts/002-pipeline-status.sh

\# Validate cross-references across monorepo documents  
bash scripts/003-resolve-cross-refs.sh

### **ZUSS Validation Matrix**

| Rule ID | Enforced Constraint |
| :---- | :---- |
| **Z01** | Kebab-case filenames with 3-digit zero-padded index prefixes (001-descriptive-name.md) |
| **Z02 / Z03** | No doubled extensions (.md.md) and strictly lowercase filenames |
| **Z05 / Z07** | Strict separation of Class A (narrative header) and Class B (YAML frontmatter) documents |
| **Z08** | Mandatory footer on all Class A documents |
| **Z09** | Rejection of marketing language ("seamless", "cutting-edge", "game-changing", "genuinely") |
| **Z12** | Prohibition of latest tags in container configurations |

## **10. Governance & Non-Negotiable Constraints**

> 1. **GitHub is the Government:** No verbal agreements or private decisions carry standing. All governance changes occur through commits, issues, and pull requests under the zarishsphere GitHub organization.  
> 2. **Permanent Zero-Cost Guarantee:** No premium tiers, freemium expirations, or feature gates exist in the ecosystem. All code is Apache 2.0; all documentation is CC BY 4.0.  
> 3. **No-Code Primacy:** All ecosystem functions must be fully operable via the browser-based Console without requiring terminal commands or software development tools.  
> 4. **Offline Primacy (Plane 0):** Any feature that fails to execute in an air-gapped environment on an 8 GB RAM device is invalid.  
> 5. **No JVM Dependencies:** Core data engines and APIs must compile to lightweight native binaries.

## **11. Cross-References**

→ **007-tech-stack/004-zarishsphere-writing-rules.md** — ZUSS naming, formatting, and structural guidelines  
→ **001-meta/001-zarishsphere-constitution.md** — ZarishSphere ecosystem supreme governing laws  
→ **002-foundation/002-zarishsphere-profile.md** — Institutional mandate, founder profile, and mission scope  
→ **001-meta/008-zarishsphere-monorepo-blueprint.md** — Monorepo architectural blueprint and hardware boundaries  
→ **007-tech-stack/001-tech-stack-master.md** — Master production tech stack specification  
→ **007-tech-stack/006-oss-tool-catalog.md** — Catalog of approved open-source libraries and licenses  

---

*ZarishSphere Foundation · V1 · July 23, 2026*  
*License: Apache 2.0 (code) · CC BY 4.0 (documentation)*  
*GitHub Repository URL: https://github.com/zsdotcom/zarishsphere
