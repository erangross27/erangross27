<div align="center">

  <!-- Animated Header -->
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=150&section=header&text=IntelliCare&fontSize=50&fontColor=ffffff&animation=fadeIn&fontAlignY=35&desc=Enterprise%20Medical%20Intelligence%20Platform&descAlignY=55&descSize=20" width="100%"/>

  # IntelliCare - Enterprise Medical Intelligence Platform

  ### *AI-Powered Healthcare Platform Built with Claude Opus 4.8*

  <!-- Badges -->
  <p>
    <img src="https://img.shields.io/badge/Claude-Opus%204.6-7C3AED.svg?style=for-the-badge&logo=anthropic&logoColor=white" alt="Claude"/>
    <img src="https://img.shields.io/badge/node.js-18+-339933.svg?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js"/>
    <img src="https://img.shields.io/badge/react-19-61DAFB.svg?style=for-the-badge&logo=react&logoColor=white" alt="React"/>
    <img src="https://img.shields.io/badge/mongodb-8.4-47A248.svg?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB"/>
    <img src="https://img.shields.io/badge/express-5-000000.svg?style=for-the-badge&logo=express&logoColor=white" alt="Express"/>
  </p>

  <p>
    <img src="https://img.shields.io/badge/Production%20Ready-brightgreen?style=flat-square" alt="Production Ready"/>
    <img src="https://img.shields.io/badge/HIPAA%20Compliant-red?style=flat-square" alt="HIPAA"/>
    <img src="https://img.shields.io/badge/Multi--Tenant-purple?style=flat-square" alt="Multi-Tenant"/>
    <img src="https://img.shields.io/badge/2.1M%20Lines%20of%20Code-blue?style=flat-square" alt="Lines of Code"/>
    <img src="https://img.shields.io/badge/3%2C500%2B%20Commits-orange?style=flat-square" alt="Commits"/>
  </p>

  ---

  **A full-stack, enterprise-grade medical intelligence platform featuring conversational AI agents, automated document analysis, drug safety monitoring, real-time clinical decision support, and comprehensive medical data management across 884 medical collections spanning 36 specialties with 23,000+ structured medical fields.**

  *Designed and built as a solo full-stack engineering effort over 5 months.*

</div>

---

## Platform at a Glance

<table>
<tr>
<td width="50%" valign="top">

### Engineering Scale
| Metric | Count |
|--------|-------|
| Lines of Code | **2.1 Million** |
| Git Commits | **3,500+** |
| Backend Services | **289** |
| API Routes | **64** |
| Data Models | **37** |
| Middleware Layers | **29** |
| Production Dependencies | **85** |
| Source Files | **4,200+** |

</td>
<td width="50%" valign="top">

### Medical Coverage
| Metric | Count |
|--------|-------|
| Document Templates | **614** |
| PDF Export Templates | **580** |
| Medical Collections | **884** |
| Medical Data Fields | **23,400+** |
| AI Agent Functions | **3,200+** |
| Field Mapping Modules | **36** |
| External API Integrations | **15+** |
| Learning System Services | **20** |

</td>
</tr>
</table>

---

## Core Capabilities

### AI-Powered Conversational Agent

The platform implements true agentic behavior using the **Anthropic Claude Agent SDK** powered by **Claude Opus 4.8**:

- **Dynamic Tool Discovery** via Anthropic's native Tool Search feature allows Claude to discover and select from 3,200+ medical functions on-demand, scaling to thousands of tools without consuming context window
- **Autonomous Agentic Loop** where Claude selects tools, the backend executes them immediately, results are returned to Claude, and Claude decides whether to call more tools or generate a final response — up to 15 autonomous iterations per request
- **Direct Backend Execution** — selected tools execute immediately in the backend with full results returned to Claude for continued clinical reasoning
- **Real-time Streaming** delivers text, thinking blocks, and tool execution progress via Server-Sent Events as they're generated
- **1M Token Context Window** enables analysis of complete patient histories, multi-document comparisons, and complex clinical reasoning in a single request
- **Prompt Caching** delivers 95% cost reduction on repeated analyses through intelligent cache management

### Automated Document Analysis Pipeline

A batch processing system that converts unstructured medical documents into structured, searchable clinical data:

- **Claude Batch API** integration provides 50% cost savings for bulk document analysis
- **Skills API Architecture** uses a reusable 1MB medical extraction schema uploaded once and referenced across all analyses
- **23,400+ Medical Field Extraction** across 884 collections with 36 specialty-specific field mapping modules
- **Two-Path Storage** maintains both complete unified documents and 884 granular collections for fast querying
- **Automatic Deduplication** with content hashing prevents reprocessing of duplicate documents

### 614 Specialized Document Templates

Each medical data type has a dedicated React template with:

- **4-Level Search System** enabling document-level, section-level, row-level, and field-level filtering with real-time highlighting
- **Copy System** with per-section and full-document copy functionality using clinically-formatted output
- **Professional PDF Export** via `@react-pdf/renderer` with medical-grade formatting (580 PDF templates)
- **Interactive Data Visualizations** including bar charts for vitals, blood pressure trends, lab values, and clinical scores
- **Dynamic Lazy Loading** prevents 21MB+ bundle bloat by loading templates on-demand

Templates cover specialties including cardiology, neurology, nephrology (including comprehensive dialysis workflows), oncology, emergency medicine, dental, geriatrics, pediatrics, obstetrics, psychiatry, endocrinology, and 24 more.

### Drug Safety & Clinical Decision Support

- **OpenFDA Integration** with access to 100,000+ drug records for interaction checking, contraindication detection, and adverse event monitoring
- **RxNorm Service** for medication normalization and cross-referencing
- **Real-Time Safety Alerts** for dangerous medication combinations with severity classification (major/moderate/minor)
- **500,000+ Medical Device Records** for device recall and adverse event tracking

### Intelligent Learning System

A 20-service learning subsystem that continuously improves platform performance:

- **Function Interceptor** captures all operation patterns for efficiency analysis
- **Temporal and Sequence Pattern Engines** identify clinical workflow patterns
- **Bottleneck Detection** and **Automation Opportunity Analysis** optimize system performance
- **User Memory Service** and **Personal Assistant** adapt to individual clinician workflows
- **Workflow Predictor** anticipates next actions based on learned patterns

---

## Architecture Overview

### High-Level System Design

```
                    ┌──────────────────────────────────────────────┐
                    │              FRONTEND                         │
                    │  React 19 + Vite 7 + Chakra UI + MUI         │
                    │  ├─ Conversational AI Chat Interface         │
                    │  ├─ Artifact Panel (3-level document nav)    │
                    │  ├─ 614 Specialized Document Templates       │
                    │  ├─ 580 PDF Export Templates                 │
                    │  ├─ Real-time Streaming (Socket.IO)          │
                    │  ├─ Staff Collaboration Chat                 │
                    │  └─ i18n + RTL Language Support              │
                    └──────────────────┬───────────────────────────┘
                                       │
                                    HTTPS/TLS
                                       │
                    ┌──────────────────▼───────────────────────────┐
                    │              BACKEND API                      │
                    │  Node.js 18+ / Express 5 / GraphQL           │
                    │  ├─ 289 Microservices                        │
                    │  ├─ Agent SDK (Claude Opus 4.6)              │
                    │  ├─ Batch Document Processor                 │
                    │  ├─ 36 Specialty Field Mapping Modules       │
                    │  ├─ 20-Service Learning System               │
                    │  ├─ External API Gateway (15+ APIs)          │
                    │  ├─ 29 Middleware Layers                     │
                    │  └─ OpenTelemetry Observability               │
                    └──────────────────┬───────────────────────────┘
                                       │
                    ┌──────────────────▼───────────────────────────┐
                    │              DATA LAYER                       │
                    │  MongoDB 8.4 + Redis                          │
                    │  ├─ Multi-tenant Database Isolation           │
                    │  ├─ 884 Medical Collections                  │
                    │  ├─ AES-256-GCM Field-Level Encryption       │
                    │  ├─ Immutable Audit Logs                     │
                    │  └─ Change Streams for Real-time Sync        │
                    └──────────────────────────────────────────────┘
```

### AI Agent Pipeline (Claude Agent SDK)

```
  Natural Language Query
         │
         ▼
  ┌─────────────────────┐
  │  Tool Search         │  Anthropic's native Tool Search
  │  (Dynamic Discovery) │  discovers relevant functions from
  └─────────┬───────────┘  3,200+ available medical operations
            │
            ▼
  ┌─────────────────────┐
  │  Agentic Loop        │  Claude autonomously calls tools,
  │  (Up to 15 rounds)   │  backend executes immediately,
  │                      │  Claude analyzes results and
  │                      │  decides next action or responds
  └─────────┬───────────┘
            │
            ▼
  ┌─────────────────────┐
  │  Real-time Stream    │  Text + tool progress streamed
  │  + Artifact Panel    │  via SSE to artifact panel
  └─────────────────────┘
```

---

## Security Architecture

IntelliCare implements **defense-in-depth** security designed for healthcare compliance:

| Layer | Implementation |
|-------|---------------|
| **Data Isolation** | Database-per-organization multi-tenant architecture with row-level security filters on every query |
| **Encryption** | AES-256-GCM field-level encryption at rest, HTTPS/TLS in transit, production KMS with master key hierarchy |
| **Access Control** | Service account system with granular permissions, RBAC middleware, and zero-knowledge authentication support |
| **Audit** | Immutable audit logs tracking all data access, breach notification system, and configurable data retention policies |
| **API Security** | Rate limiting (10K queries/min per service), circuit breakers, MongoDB operator validation against injection, GraphQL depth limiting and query complexity analysis |
| **Compliance** | HIPAA-compliant data handling, Business Associate Agreement management, PHI anonymization service for research |
| **Monitoring** | Threat detection, security chaos testing, OpenTelemetry distributed tracing, performance monitoring |

---

## Technology Stack

### Backend
| Category | Technologies |
|----------|-------------|
| **Runtime & Framework** | Node.js 18+, Express 5, GraphQL (Apollo Server) |
| **AI & LLM** | Anthropic Claude Opus 4.6, Claude Agent SDK v0.2, Batch API, Skills API, Tool Search, Code Execution |
| **Database** | MongoDB 8.4, Mongoose 9, Redis 5 |
| **Search & ML** | LangChain, Transformers.js |
| **Observability** | OpenTelemetry (7 packages), Winston logging with daily rotation |
| **Communication** | Socket.IO, SendGrid, Twilio, Nodemailer |
| **File Processing** | PDF parsing, OCR (Tesseract.js), DICOM medical imaging, Office documents |
| **Security** | Helmet, bcrypt, JWT, Zod validation |
| **External APIs** | OpenFDA, CMS Medicare/Medicaid, ClinicalTrials.gov, NIH RePORTER, PubMed, RxNorm |

### Frontend
| Category | Technologies |
|----------|-------------|
| **Framework** | React 19, Vite 7 |
| **UI Libraries** | Chakra UI 3, Material UI 7, Tailwind CSS 4, Framer Motion |
| **State** | Zustand 5, React Context |
| **Data Visualization** | Chart.js, react-chartjs-2 |
| **PDF Generation** | @react-pdf/renderer 4 |
| **Real-time** | Socket.IO Client |
| **Internationalization** | i18next with RTL support |
| **Icons** | Lucide React, MUI Icons |

---

## Medical Specialty Coverage

The platform includes **884 medical data collections** with **23,400+ structured fields**, organized across **36 medical specialties** with dedicated field mapping modules, document templates, and extraction schemas:

<table>
<tr>
<td width="25%" valign="top">

- Allergy & Immunology
- Anesthesiology
- Cardiology
- Colorectal Surgery
- Dental
- Dermatology
- Emergency Medicine
- Endocrinology
- ENT

</td>
<td width="25%" valign="top">

- Family Medicine
- Gastroenterology
- Geriatrics
- Hematology
- IBD
- Infectious Disease
- Medical Genetics
- Nephrology & Dialysis
- Neurology

</td>
<td width="25%" valign="top">

- Neurosurgery
- Nuclear Medicine
- Obstetrics & Gynecology
- Oncology
- Ophthalmology
- Orthopedics
- Pathology
- Pediatrics
- Physical Medicine & Rehab

</td>
<td width="25%" valign="top">

- Plastic Surgery
- Preventive Medicine
- Psychiatry
- Pulmonology
- Radiology
- Rheumatology
- Surgery (General)
- Thoracic Surgery
- Urology

</td>
</tr>
</table>

---

## External API Integrations

| Provider | APIs | Purpose |
|----------|------|---------|
| **FDA** | OpenFDA Drug Events, Labels, Enforcement, NDC, Shortages, Devices; iRES Reports; Data Dashboard; Product Code Builder | Drug safety, interaction checking, device monitoring |
| **CMS** | Provider Directory, Blue Button 2.0, Medicaid Data API (DKAN) | Medicare claims import, Medicaid enrollment & drug utilization |
| **NIH** | ClinicalTrials.gov, NIH RePORTER, PubMed E-utilities | Clinical trial matching, research literature search |
| **Pharmacy** | RxNorm | Medication normalization and cross-referencing |
| **Google** | Cloud Healthcare API | FHIR interoperability |

---

## Key Engineering Highlights

### Developed in 5 Months (Solo)
- **3,500+ commits** averaging 24 commits/day
- **2.1 million lines** of production code
- **289 backend services** with comprehensive test coverage
- From first commit to production-ready enterprise platform

### Scale of the Template System
- **614 document templates** each with 4-level search, copy buttons, and real-time highlighting
- **580 matching PDF templates** for professional medical document export
- **Dynamic lazy loading** architecture that prevents multi-megabyte initial bundles
- Each template handles complex medical data parsing: embedded subtitles, multi-group structures, entity recognition, and configurable text splitters

### AI Integration Depth
- **Claude Agent SDK** with native Tool Search for dynamic discovery from 3,200+ medical functions — Claude autonomously chains tool calls in an agentic loop
- **20-service learning system** that captures usage patterns, detects bottlenecks, and predicts clinical workflows
- **Medical image analysis** with DICOM support, Claude Vision integration, and structured findings extraction
- **Staff collaboration chat** for inter-clinician communication within the platform

### Security Engineering
- **29 middleware layers** implementing defense-in-depth (authentication, authorization, rate limiting, threat detection, audit logging, circuit breakers)
- **Field-level encryption** with production KMS and master key hierarchy
- **Multi-tenant isolation** ensuring complete data separation between organizations
- **GraphQL security** with depth limiting, query complexity analysis, and rate limiting

---

## Development Methodology

This platform was built using a highly disciplined **AI-assisted development workflow**:

- **Claude Code CLI** (Anthropic's official coding agent) used throughout development with Claude Opus 4.6
- **MCP Memory Server** for persistent architectural knowledge across development sessions
- **Custom Skills System** providing structured approaches for brainstorming, debugging, code review, test-driven development, and frontend design
- **65-Rule Template Checklist** ensuring consistency across all 614 document templates
- **Session Tracking** with automatic progress logging and decision documentation
- **Specialty Roadmaps** defining tier-based feature rollouts per medical domain

---

## Project Status

| Area | Status |
|------|--------|
| Core Platform | Production Ready |
| AI Agent (Claude Opus 4.8) | Production Ready |
| Document Analysis Pipeline | Production Ready |
| 614 Document Templates | Production Ready |
| Drug Safety (OpenFDA) | Production Ready |
| Multi-Tenant Security | Production Ready |
| Staff Chat | Production Ready |
| Medical Image Analysis | Production Ready |
| Learning System | Active Development |
| FHIR Interoperability | Planned |

---

## About This Repository

This is a **private repository**. This README is shared for portfolio and resume purposes to demonstrate the scope and technical depth of the project. The platform is designed for healthcare organizations requiring enterprise-grade medical data management with AI-powered clinical intelligence.

### Contact

- **Developer**: Eran Gross
- **GitHub**: [@erangross27](https://github.com/erangross27)

---

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer" width="100%"/>

  **Built with Claude Opus 4.6 | Full-Stack Solo Engineering | 5 Months | 2.1M Lines of Code**

</div>
