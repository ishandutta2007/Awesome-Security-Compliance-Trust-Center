# Awesome-Security-Compliance-Trust-Center

# Awesome Security, Compliance & Trust Center

> A curated list of top Security, Compliance and Trust Center platforms — both SaaS/Hosted commercial solutions and open-source alternatives for publishing security posture, managing compliance evidence, and building customer trust.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [SafeBase](#safebase)
  - [Vanta Trust Center](#vanta-trust-center)
  - [Drata Trust Center](#drata-trust-center)
  - [Conveyor](#conveyor)
  - [Whistic](#whistic)
  - [OneTrust Trust Center](#onetrust-trust-center)
  - [TrustArc](#trustarc)
- [Open-Source Software](#-open-source-software)
  - [Kodus Trust Center](#kodus-trust-center)
  - [Cairn](#cairn)
  - [Probo](#probo)
  - [QResponder](#qresponder)
  - [Questionnaire-Responder](#questionnaire-responder)
  - [OpenGRC](#opengrc)
  - [OpenWatch](#openwatch)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Security, Compliance and Trust Center platforms. These are not open-source but are included as reference points for feature comparison.

### SafeBase
**Type:** Trust center platform with AI questionnaire automation  
SafeBase is a leading commercial trust center platform, providing a public-facing security posture page alongside AI-assisted questionnaire response and document access controls. Its **Multi-Product Trust Center** consolidates security, privacy, and compliance information across multiple products onto a single page, with product filters that let visitors narrow content by product [citation:6]. The June 2026 release added **AI-Assisted Trust Center Setup**, which automatically analyzes uploaded documents, knowledge base content, and synced evidence to generate Trust Center content in minutes, moving teams from a days-long writing process to a faster review workflow [citation:14]. The platform also includes questionnaire lifecycle management with a formal "Ready for Review" state and an append-only Answer History Log [citation:14].

### Vanta Trust Center
**Type:** Trust center within compliance automation suite  
Vanta's Trust Center extends its compliance automation platform with a public-facing trust page. The Trust Center editor allows teams to manage resources, subprocessors, and updates, with **draft and preview capabilities** before publishing changes [citation:15]. Resource drafting can be enabled so that knowledge base changes are saved as drafts until explicitly published, giving teams control over what goes live [citation:15]. The platform tracks engagement with the Trust Center homepage and document downloads, providing visibility into visitor interest [citation:7].

### Drata Trust Center
**Type:** Trust center within Drata compliance platform  
Drata provides a Trust Center as part of its compliance automation offering, enabling organizations to publish their security posture and certifications without building a separate portal. The Trust Center is managed through a dedicated editor, with automatic synchronization between Drata files/policies and the Trust page — deleting a file in Drata automatically removes it from the Trust page, and archiving a policy removes it as well [citation:8]. File visibility is controlled through privacy settings, with an NDA option that sets all uploaded files to private by default [citation:8]. **Note:** Customers using the "New Drata experience" now manage their Trust Center through SafeBase [citation:8].

### Conveyor
**Type:** Trust center and security review automation  
Conveyor provides a trust center for publishing compliance posture, alongside a security questionnaire automation workflow that helps sales and security teams respond faster to customer inquiries.

### Whistic
**Type:** Vendor security assessment and trust management  
Whistic focuses on vendor security assessments and trust management, helping organizations respond to security questionnaires and manage third-party risk from a centralized platform.

### OneTrust Trust Center
**Type:** Privacy-focused trust center within OneTrust suite  
OneTrust provides a Trust Center as part of its broader privacy management platform, focused on consent, data mapping, and privacy certifications.

### TrustArc
**Type:** Privacy certification and trust center  
TrustArc provides privacy compliance certifications and a trust center for publishing certification status to customers and partners.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Security, Compliance and Trust Center tools. The open-source ecosystem **splits** between **trust center builders** (Kodus Trust Center), **GRC platforms with public compliance pages** (Cairn, Probo), and **questionnaire automation engines** (QResponder, Questionnaire-Responder).

### Kodus Trust Center
**Stack:** Next.js / TypeScript / Supabase | **License:** Open Source  
Kodus Trust Center is a **free, self-hosted, YAML-driven trust center builder** that lets you paste your security program into a single YAML document and instantly expose a polished trust portal [citation:1]. Features include a public trust center with theming (light/dark), company logo, hero commitments, metrics, compliance cards, policies, documents, infrastructure, monitoring, updates, FAQs accordion, subprocessors, and contacts. Document requests are collected via modal (work email + context) and stored in Supabase, with an admin dashboard for managing requests and editing the YAML config. GitHub SSO via NextAuth secures admin access. Everything lives in your repo or Supabase project, deployable to Vercel, Fly, Render, or any Next.js host — explicitly "no paid SaaS, no vendor lock-in" [citation:1].  
**Best for:** Small to mid-sized teams wanting a self-hosted trust center that can be edited via YAML by sales and security teams, without a commercial subscription.

### Cairn
**Stack:** Django / PostgreSQL / Redis | **License:** Open Source (permissive)  
Cairn is a comprehensive open-source GRC platform with a built-in **Trust Center** module — a public, curated page for your security posture, optionally on its own domain [citation:4]. Beyond the trust page, Cairn covers governance (ISO 27001 clause 4 context), assets with CIA valuation, risks (ISO 27005 and EBIOS RM), compliance frameworks with audits, incidents with sealed evidence and statutory notification clocks (GDPR, NIS2, DORA), and steering dashboards. **Governance is enforced, not suggested**: every record runs a permissioned lifecycle that leaves a trail, with no status dropdown. Everything is reachable through a REST API and a built-in MCP server for AI assistants, under the caller's own permissions. AI features (Ask Cairn) are off by default and can point at local Ollama [citation:4].  
**Best for:** Organizations wanting a self-hosted GRC platform that includes a public trust center alongside full internal compliance management, with strong audit trails and API/MCP accessibility.

### Probo
**Stack:** Go / PostgreSQL / GraphQL | **License:** ISC  
Probo is an open-source GRC platform with a built-in **Compliance Page** for public trust center publishing [from previous context]. It covers risk management, controls, vendor risk, data privacy, access reviews, and audit programs. The Compliance Page supports NDA management, certification publishing, and custom domains. Every entity is accessible via web console, CLI, **270+ MCP tools** for AI agents, and GraphQL API, with immutable audit logs and policy-based RBAC.

### QResponder
**Stack:** Python / FastAPI | **License:** Open Source  
QResponder is a **local-first, self-hostable security questionnaire automation** tool that generates grounded, cited answers from your own knowledge base [citation:2]. Key privacy guarantees: connector credentials live server-side and never touch the browser; connectors run only on explicit `connect`, never during answering; local answering stays **zero-egress**. Supports OAuth connections to Notion, Google Drive, and Confluence. The answering path (Tier-1 → hybrid retrieval + rerank → grounded generation → faithfulness → abstain) never makes external fetches unless you configure a cloud model; with a local model, zero external calls are made. Includes per-run source include/exclude filters and an audit trail recording effective sources used [citation:2].  
**Best for:** Security teams wanting questionnaire automation with strict data boundary guarantees, where internal policies never leave the host unless explicitly configured.

### Questionnaire-Responder
**Stack:** Python / SQLite / Streamlit | **License:** Open Source  
Questionnaire-Responder turns a vendor security questionnaire spreadsheet into a first-pass draft, **citing your own security docs for every answer and never inventing a control you do not have** [citation:10]. It includes a **documentation gap report** that analyzes unanswered questions to reveal what your policy set does not document — "find out what you need to write before a customer asks." Multi-client workspaces keep consultant or vCISO client evidence structurally isolated at the storage layer (separate directories, separate SQLite stores), making cross-workspace contamination structurally impossible. Includes a Streamlit review UI for approving, editing, or rejecting drafted answers with verbatim cited evidence and confidence badges [citation:10].  
**Best for:** Consultants and vCISOs answering questionnaires for multiple clients, needing strict workspace isolation and gap analysis to improve documentation.

### OpenGRC
**Stack:** Web application | **License:** MIT  
OpenGRC is a cyber Governance, Risk, and Compliance web application intended for small businesses and teams — explicitly "not intended to replace large-scale GRC Platforms, but it just might for your use case" [citation:12]. Features include a simple interface designed for minimal training, quick imports of common security frameworks, ability to connect Standards/Controls/Implementations, internal and external audit capabilities, report generation for auditors, and intuitive dashboards. Positioned as an accessible alternative to complex enterprise solutions [citation:12].  
**Best for:** Small businesses and teams wanting a lightweight, MIT-licensed GRC tool with framework imports and audit reporting, without enterprise complexity.

### OpenWatch
**Stack:** Go / PostgreSQL / React | **License:** Open Source  
OpenWatch is a **continuous compliance platform** for Linux fleets under CIS, STIG, NIST 800-53, NIST 800-171, CMMC Level 2, and PCI DSS [from previous context]. It provides the audit-ready evidence layer that a trust center depends on: point-in-time queries answering "Were these servers compliant on January 15th?" in seconds, backed by machine-verifiable evidence exportable as CSV, JSON, PDF, or OSCAL. Connects to servers over SSH and keeps posture as a timeline showing what is passing now, what was passing last week, and what drifted.  
**Best for:** Linux-centric organizations needing continuous compliance evidence for audits that can feed into trust center claims, without proprietary scanning agents.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Public Trust Page | Questionnaire Automation | Self-Hosted | Best For |
|----------|---------|-------|-------------------|--------------------------|-------------|----------|
| **SafeBase** | Proprietary | Cloud | ✅ Multi-product | ✅ AI-assisted | ❌ | Commercial trust center |
| **Vanta Trust Center** | Proprietary | Cloud | ✅ Draft/preview | (Suite) | ❌ | Vanta compliance users |
| **Drata Trust Center** | Proprietary | Cloud | ✅ Auto-sync files | ❌ | ❌ | Drata compliance users |
| **Kodus Trust Center** | Open Source | Next.js/Supabase | ✅ YAML-driven | ❌ | ✅ | Self-hosted trust portal |
| **Cairn** | Open Source | Django/Postgres | ✅ Trust Center module | ❌ | ✅ | Full GRC + public page |
| **Probo** | ISC | Go/Postgres | ✅ Compliance Page | ❌ | ✅ | Full GRC + MCP tools |
| **QResponder** | Open Source | Python/FastAPI | ❌ | ✅ Zero-egress | ✅ | Local-first questionnaire |
| **Questionnaire-Responder** | Open Source | Python/SQLite | ❌ | ✅ Gap report | ✅ | Multi-client consultants |
| **OpenGRC** | MIT | Web app | ❌ | ❌ | ✅ | Lightweight GRC for SMBs |
| **OpenWatch** | Open Source | Go/Postgres | ❌ (Evidence layer) | ❌ | ✅ | Continuous compliance evidence |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Security, Compliance or Trust Center tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem **splits** between **trust center builders** (Kodus Trust Center, the most direct SafeBase alternative with YAML-driven editing), **GRC platforms with public compliance pages** (Cairn for comprehensive governance with enforced lifecycles, Probo for 270+ MCP tools), and **questionnaire automation engines** (QResponder for zero-egress local answering, Questionnaire-Responder for multi-client gap analysis). **SafeBase** and **Vanta** remain the commercial leaders, with SafeBase's AI-Assisted Trust Center Setup and multi-product consolidation representing capabilities that open-source tools are still catching up to [citation:6][citation:14]. For organizations wanting a self-hosted trust center today, Kodus + Cairn provides a solid foundation.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
