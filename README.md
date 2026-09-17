<div align="center">

# Kareem Mohammad

**Applied AI Engineer & Systems Architect**  
*Autonomous Agent Swarms &nbsp;·&nbsp; Low-Latency Distributed Caching &nbsp;·&nbsp; Zero-Trust Enterprise Infrastructure*

[![GitHub](https://img.shields.io/badge/GitHub-Kareem411-181717?style=flat-square&logo=github)](https://github.com/Kareem411)
[![TriCache](https://img.shields.io/badge/TriCache-Documentation%20Portal-0284c7?style=flat-square&logo=gitbook&logoColor=white)](https://kareem411.github.io/TriCache/)
[![npm](https://img.shields.io/badge/npm-tricache%20v0.8.0-cb3837?style=flat-square&logo=npm&logoColor=white)](https://www.npmjs.com/package/tricache)
[![VoiCase](https://img.shields.io/badge/SaaS-VoiCase.me-10b981?style=flat-square&logo=safari&logoColor=white)](https://www.voicase.me)
[![Workabix](https://img.shields.io/badge/Enterprise-Workabix%20(In%20Dev)-047857?style=flat-square&logo=target&logoColor=white)](#-workabix--distributed-enterprise-hris--applicant-tracking-system-in-development)

</div>

---

### 🏛️ Flagship Systems & Core Engineering

#### ⚡ [TriCache](https://github.com/Kareem411/TriCache) — Enterprise Three-Tier Distributed Caching Engine for Node.js
*High-throughput, multi-tier caching engine absorbing 95%+ of queries locally with warm in-memory reads at **2.81 million ops/sec (356 ns/op)**.*
* **Three-Tier Storage Hierarchy**: Automatic cascading through **L1 RAM** (adaptive W-TinyLFU + Count-Min Sketch) $\rightarrow$ **L1.5 Off-Heap POSIX `/dev/shm` tmpfs & NVMe spill** $\rightarrow$ **L2 Clustered Redis/Valkey**.
* **Thundering-Herd Prevention**: In-process Singleflight promise coalescing eliminates duplicate DB queries under 10k-concurrency spikes, combined with background Stale-While-Revalidate (SWR) revalidation.
* **WASM & Mathematical Internals**: Inlined WebAssembly Murmur3 64-bit Bloom filters for zero-GC key-existence checks; zero-JSON MsgPack binary serialization reducing heap pressure by up to 68%.
* **Zero-Dependency Cloud Snapshots & Envelope Encryption**: Standalone AWS SigV4 signer for instant cold-start hydration from S3 / Cloudflare R2; AES-256-GCM / CTR envelope encryption with key-rotation fallbacks.
* **Turnkey Ecosystem Adapters**: Native modules for **Next.js 16/15** App Router (`cacheHandlers`), **NestJS** dynamic modules, **Prisma** `$extends`, **Drizzle ORM** `withCache`, **Express & Fastify** (RFC 7232 weak ETag & `304 Not Modified`), and zero-Node **Cloudflare Workers / Edge Isolates**.
* **Observability Suite**: Real-time SSE Web admin dashboard, Prometheus golden-signals text exporter, pre-built Grafana dashboards, and terminal top monitor (`npx tricache top`).

```
┌──────────────────────────────────────┬─────────────┬─────────────┬───────────────────────────┐
│ Tier / Architecture Path             │ Throughput  │ p50 Latency │ Memory & Eviction Engine  │
├──────────────────────────────────────┼─────────────┼─────────────┼───────────────────────────┤
│ TriCache L1 (In-Memory RAM)          │  2.82 M/s   │   396 ns    │ W-TinyLFU + Count-Min     │
│ TriCache L1.5 (/dev/shm POSIX tmpfs) │  851.5 K/s  │   1.17 µs   │ Zero-GC Off-Heap Spill    │
│ TriCache Singleflight Stampede Gate  │   10k req   │  1 origin   │ Zero herd collapse        │
│ Standalone Remote Redis (Network IO) │   75.0 K/s  │  13.30 µs   │ Network + JSON parse cost │
└──────────────────────────────────────┴─────────────┴─────────────┴───────────────────────────┘
```

#### 💼 Workabix — Distributed Enterprise HRIS & Applicant Tracking System *(In Active Development)*
*Full-lifecycle talent acquisition and human capital management platform engineered as a distributed microservices monorepo.*
* **Distributed Domain Isolation**: Turborepo monorepo separating distinct service domains (`identity-svc`, `jobs-svc`, `candidates-svc`, `employees-svc`) backed by NestJS and coordinated asynchronously over a **Kafka (KRaft)** event bus.
* **High-Throughput Go Workers**: High-performance resume parsing, semantic entity extraction, and asynchronous pipeline ingestion built in Go for maximum memory efficiency under heavy concurrency.
* **Dual-Plane Web Architecture**: Next.js App Router featuring high-speed ISR/SSR for public careers portals alongside a high-density, real-time operator workspace built with custom "Tech-Grotesque" design tokens.
* **Resilient Data Layer**: PostgreSQL managed via Drizzle ORM, multi-tenant RBAC security guards, Redis caching, and OpenSearch for instant full-text candidate indexing.
* **Cloud Infrastructure as Code**: Automated provisioning via Terraform spanning AWS ECS Fargate, Aurora Serverless, Amazon MQ, and S3 asset vaults.

#### 🧠 [CANA](https://github.com/Kareem411/cana) — Continuously Adaptive Neural Architecture
*Context-substrate agent adaptation operating around frozen models (API or local).*
* **Governed Context Substrate**: Replaces the catastrophic forgetting and instability of weight fine-tuning with a governed context layer that adapts agent behavior dynamically at runtime.
* **Deterministic Assembly & Hybrid Retrieval**: Merges structured temporal knowledge graphs, sparse lexical search, and dense vector embeddings (`pgvector`) into verified, context-budgeted prompt frames.
* **Append-Only Capture Ledger**: Continuous ingestion stream capturing interaction telemetry, tool results, and execution trajectories for asynchronous background distillation.
* **Behavioral Verification Gates**: Strictly validates model outputs through offline behavioral invariant gates before actions are committed to production systems.

#### 🤖 [ParadiseLabs](https://github.com/Kareem411) — Autonomous Agent Orchestration & MCP Infrastructure
*Decoupled multi-agent execution harnesses and tool virtualization fabric.*
* **ACT (Agent Coordination Toolkit)**: Multi-agent CLI harness decoupling planning, tool invocation, and formal verification; operates Tier-1 in-process agent swarms directing headless Tier-2 worker processes via structured SPIL tasks.
* **GLUE Framework**: Declarative DSL linking engine designed to dynamically assemble, instantiate, and route collaborative agent collectives.
* **Model Context Protocol (MCP)**: Implemented terminal-driven MCP server discovery, schema validation, and dynamic capability injection across local and remote agent environments.

#### 🛡️ [VoiCase](https://www.voicase.me) — Enterprise Compliance & Whistleblowing SaaS
*Turnkey B2B incident management platform engineered to European Union Whistleblowing Directive & GDPR standards.*
* **End-to-End Product Architecture**: Solely engineered the production B2B platform, converting complex legal privacy requirements into high-assurance cloud software.
* **Cryptographic Case Lifecycle**: Multi-stage case routing engine featuring dual-authorization workflows, immutable audit logs, and tamper-evident incident reporting.
* **Ironclad Isolation**: Multi-tenant PostgreSQL Row-Level Security (RLS) combined with isolated VPC network boundaries to guarantee zero metadata leakage and absolute informant anonymity.

---

### 📐 Architectural Principles

```
  ┌───────────────────────┐      ┌─────────────────────────┐      ┌─────────────────────────┐
  │   Zero-GC & Off-Heap  │      │  Deterministic AI Gates │      │  Defense-in-Depth RLS   │
  │  /dev/shm POSIX tmpfs │ ───► │  Governed context layer │ ───► │ Cryptographic audit log │
  │  2.81M ops/s caching  │      │  Decoupled agent swarms │      │  Zero metadata leakage  │
  └───────────────────────┘      └─────────────────────────┘      └─────────────────────────┘
```

* **Deterministic AI over Stochastic Chaos**: Grounding LLMs with strict behavioral boundaries, governed context substrates, and deterministic multi-phase evaluation.
* **Low-Latency Systems Engineering**: Squeezing hardware limits with POSIX `/dev/shm` shared memory, WASM SIMD filters, and binary protocols rather than bloated serialization layers.
* **Zero-Trust Multi-Tenancy**: Enforcing strict cryptographic boundaries, envelope encryption, and non-bypassable database policies across all enterprise tiers.

---

### 🛠️ Technical Stack & Arsenal

| Domain | Technologies & Infrastructure |
|:---|:---|
| **Core Languages** | TypeScript · Go · Python · C · SQL · WebAssembly (WASM) |
| **Autonomous Systems & AI** | Model Context Protocol (MCP) · LLM Orchestration · Multi-Agent Swarms · RAG Architectures · PyTorch · OpenCV |
| **High-Performance Backend** | Node.js · Fastify · Express · Next.js · NestJS · FastAPI · REST · WebSockets · gRPC · Kafka (KRaft) |
| **Distributed Storage & Caching** | TriCache · Redis / Valkey · PostgreSQL (`pgvector`) · OpenSearch · Supabase · POSIX `/dev/shm` · SQLite |
| **Cloud & Infrastructure** | AWS (ECS, Fargate, Bedrock, Aurora Serverless, S3) · Cloudflare Workers / R2 · Docker · Kubernetes · Terraform · CI/CD |

---

<div align="center">

<sub>Architecting autonomous systems and low-latency infrastructure that scale deterministically.</sub>

</div>
