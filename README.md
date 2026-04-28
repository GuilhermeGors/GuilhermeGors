<div align="center">

# Guilherme Oliveira

**AI Engineer · Privacy-First RAG & Multi-Agent Systems · GDPR-Compliant Generative AI**

Building enterprise AI infrastructure that runs locally, scales globally, and leaks nothing.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/guilhermegors/)
[![Email](https://img.shields.io/badge/guilhermegors@gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:guilhermegors@gmail.com)
![Views](https://komarev.com/ghpvc/?username=GuilhermeGors&color=2C3E50&style=flat&label=views)

</div>

---

### 🎯 What I Do & Impact

I engineer **Generative AI platforms for highly-regulated environments**, ensuring data privacy, scalable orchestration, and independence from cloud LLM providers. The market demands AI that respects GDPR — I build systems where **infrastructure sovereignty is the default**. 

Instead of just prototyping, I approach AI Engineering with a results-driven mindset:

*   **Sovereign Enterprise AI:** Companies need AI without risking proprietary data leaks. *Result:* Architected systems like **Codex One** and **IA News Agent**, utilizing open-weights models (Ollama) and on-prem ChromaDB to achieve **100% data sovereignty and zero external API dependencies**, making them audit-ready for strict compliance.
*   **Workflow Automation at Scale:** Manual data processing bottlenecks business growth. *Result:* Built **JobMatch**, a multi-agent RAG platform that parses unstructured resumes and performs semantic ranking, reducing human evaluation time by **95%** while retaining precise skill-matching.
*   **High-Throughput & Low-Latency AI:** Cloud API costs scale linearly; local inference requires optimization. *Result:* Implemented batch prompting, asynchronous LangGraph orchestration, and exact/semantic dual-layer caching (achieving **12ms inference latency** in Visual Tagger) to push CPU/GPU hardware to its limits.

```
Privacy-First RAG Pipelines    ·    Multi-Agent Orchestration    ·    Data Engineering (Spark + Scala)
Local LLM Deployment           ·    Multi-Cloud Infrastructure   ·    Security & GDPR Compliance
```

---

## ⚡ Featured Projects

<table>
<tr>
<td width="50%" valign="top">

### 📰 [IA News Agent](https://github.com/GuilhermeGors/IA_News)
**Autonomous multilingual intelligence pipeline**

Aggregates, enriches, and validates AI research across 10 languages and 7 source types. Uses a dual-model LLM strategy (Qwen 3B + 14B) driven by a stateful LangGraph reasoning core. Complete on-prem execution with zero data leakage.

`Python` `Ollama` `LangGraph` `ChromaDB` `FastAPI`

</td>
<td width="50%" valign="top">

### 🔒 [Codex One](https://github.com/GuilhermeGors/Codex_One)

**Privacy-first enterprise knowledge base — fully offline RAG**

Zero-egress architecture with pre-ingestion Threat Quarantine and automated PII Scrubbing. Uses CPU-bound ONNX embeddings and multilingual Cross-Encoder reranking (FlashRank) to isolate GPUs exclusively for Local LLMs (Ollama), delivering audit-ready compliance and high-performance retrieval.

`Python` `FastAPI` `Next.js` `Ollama` `ChromaDB` `FlashRank`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🤖 [JobMatch](https://github.com/GuilhermeGors/JobMatch)
**Multi-agent RAG platform for HR automation**

Automated talent screening reducing manual evaluation by 95%. Semantic search over unstructured data, dynamic ranking, LLM-agnostic inference (OpenAI / Gemini / local). Real-time analytics via WebSockets.

`FastAPI` `LangChain` `React` `WebSockets` `Vector DB`

</td>
<td width="50%" valign="top">

### 🏷️ [Visual Tagger](https://github.com/GuilhermeGors/Visual_tagger)
**High-performance AI image classification — 12ms latency**

Concurrent ViT + CLIP Zero-Shot inference with confidence-score aggregation. Parallel model execution for automated multi-label tagging at production scale.

`FastAPI` `PyTorch` `HuggingFace` `CLIP` `Docker`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 💄 [Cosmetic Cosmos](https://github.com/GuilhermeGors/Cosmetic_cosmos)
**AI-augmented scalable sales management platform**

Distributed high-performance ScyllaDB backend handling concurrent retail transactions. Features an embedded role-aware local LLM assistant (Ollama) providing contextual KPIs and mentorship without exposing metrics to third parties.

`Node.js` `Express` `ScyllaDB` `Ollama` `Docker`

</td>
<td width="50%" valign="top">

### 🧱 [Systems Programming](https://github.com/GuilhermeGors/libft)
**Low-level engineering — C from scratch**

Custom standard library, Unix process pipelines, 2D rendering engine. Built at 42 São Paulo with zero external dependencies — raw memory management, file descriptors, and bitwise ops.

`C` `Unix` `Makefile` `Memory Management`

</td>
</tr>
</table>

---

## 🏗️ Architecture — How I Build RAG Systems

```mermaid
flowchart TD
    %% Styling
    classDef edgeLayer fill:#e3f2fd,stroke:#1565c0,stroke-width:2px,color:#000
    classDef orchestrator fill:#fff3e0,stroke:#ef6c00,stroke-width:2px,color:#000
    classDef agents fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px,color:#000
    classDef data fill:#fce4ec,stroke:#c62828,stroke-width:2px,color:#000
    classDef model fill:#f3e5f5,stroke:#7b1fa2,stroke-width:2px,color:#000

    subgraph Gateway ["🌐 Security & Edge Layer"]
        direction LR
        Client(["Client Apps"])
        API["API Gateway<br/><i>(Auth & Rate Limits)</i>"]
        Vault[("Secrets<br/>Manager")]
    end

    subgraph Core ["🔄 Orchestration Engine"]
        direction TB
        Router{"Semantic Router<br/><i>(Intent Classification)</i>"}
        Ctx["Context Manager<br/><i>(State & Memory)</i>"]
    end

    subgraph Swarm ["🤖 Specialized Agent Swarm"]
        direction LR
        GDPR["Compliance Agent<br/><i>(PII Scrubber)</i>"]
        RAG["RAG Agent<br/><i>(Retrieval Logic)</i>"]
        Eval["Analysis Agent<br/><i>(Synthesis)</i>"]
    end

    subgraph Storage ["💾 Hybrid Data Layer"]
        direction LR
        Redis[("Redis Cache<br/><i>(Low Latency)</i>")]
        Vector[("ChromaDB<br/><i>(Semantic DB)</i>")]
    end

    subgraph Engine ["🧠 Local Inference"]
        direction LR
        LLM("Open-Weights LLMs<br/>via Ollama <i>(Zero Leakage)</i>")
    end

    %% Connections
    Client ===>|TLS/WS| API
    API <.->|Vault Keys| Vault
    API --->|Requests| Router

    Router <-->|Maintains| Ctx
    Router -->|Dispatch| GDPR
    Router -->|Dispatch| RAG
    Router -->|Dispatch| Eval

    GDPR ===>|Sanitized Query| RAG
    
    RAG <-->|Query/Upsert| Vector
    Eval <-->|Check Hits| Redis
    
    RAG --->|Private Inference| LLM
    Eval --->|Private Inference| LLM

    %% Apply Classes
    class Gateway,Client,API,Vault edgeLayer
    class Core,Router,Ctx orchestrator
    class Swarm,GDPR,RAG,Eval agents
    class Storage,Redis,Vector data
    class Engine,LLM model
```

---

## 🛠️ Tech Stack

<table>
<tr>
<td align="center" width="25%">

**AI & ML**

![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat&logo=langchain&logoColor=white)
![LlamaIndex](https://img.shields.io/badge/LlamaIndex-6B7280?style=flat)
![Ollama](https://img.shields.io/badge/Ollama-000000?style=flat&logo=ollama&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HF-FFD21E?style=flat&logo=huggingface&logoColor=black)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/sklearn-F7931E?style=flat&logo=scikitlearn&logoColor=white)

</td>
<td align="center" width="25%">

**Data Engineering**

![Spark](https://img.shields.io/badge/Spark-E25A1C?style=flat&logo=apachespark&logoColor=white)
![Scala](https://img.shields.io/badge/Scala-DC322F?style=flat&logo=scala&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/Postgres-4169E1?style=flat&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat&logo=redis&logoColor=white)
![ChromaDB](https://img.shields.io/badge/Chroma-FF6F61?style=flat)

</td>
<td align="center" width="25%">

**Cloud & DevOps**

![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazonaws&logoColor=white)
![GCP](https://img.shields.io/badge/GCP-4285F4?style=flat&logo=googlecloud&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat&logo=microsoftazure&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat&logo=terraform&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat&logo=ansible&logoColor=white)

</td>
<td align="center" width="25%">

**Languages & APIs**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat&logo=c&logoColor=black)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)
![Node.js](https://img.shields.io/badge/Node-339933?style=flat&logo=nodedotjs&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)

</td>
</tr>
</table>

---

## 📐 Core Engineering Core Principles

- **🔒 Privacy & Law by Design:** Engineered for environments where strict European GDPR dictates are mandatory. Implementing Offline LLMs and on-prem vector databases to guarantee zero third-party exposure.
- **🔌 Vendor-Agnostic Architecture:** Building decoupled, LLM-agnostic platforms. Codebases designed such that swapping OpenAI ↔ Gemini ↔ Local Ollama requires zero restructuring.
- **🚀 Scalability & Resiliency:** Designing hybrid architectures—from 200GB/day distributed Apache Spark systems to ultra-lightweight Dockerized microservices wrapped in circuit breakers and semantic cache layers.
- **⚙️ First-Principles Thinking:** Grounded in the brutal *42 São Paulo methodology* (C, Unix, memory management). I don't just glue APIs together; I profoundly understand the performance parameters executing them.

---

## 🎓 Background

**42 São Paulo** — Software Engineering *(Peer-to-peer, zero-professor model)*  
**Unisinos** — Analysis & Systems Development  
**Bayswater College, London** — Exchange Program  

🥈 **Moving The Cities** — Unisinos × SAP × FH Münster (Germany) × UAS7  
🏆 **Geração Caldeira** — First Class, Institute Caldeira  

---

<div align="center">

**Open solve problems**<br>
Fluent in English · Eligible anywhere :)

[![LinkedIn](https://img.shields.io/badge/Connect-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/guilhermegors/)
[![Email](https://img.shields.io/badge/Contact-Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:guilhermegors@gmail.com)

</div>

</details>
