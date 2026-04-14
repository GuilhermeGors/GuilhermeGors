<div align="center">

# Guilherme Oliveira

**AI Platform Engineer · Privacy-First RAG & Multi-Agent Systems · GDPR-Compliant Generative AI**

Building enterprise AI infrastructure that runs locally, scales globally, and leaks nothing.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/guilhermegors/)
[![Email](https://img.shields.io/badge/guilhermegors@gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:guilhermegors@gmail.com)
![Views](https://komarev.com/ghpvc/?username=GuilhermeGors&color=2C3E50&style=flat&label=views)

</div>

---

### What I Do

I architect **Generative AI systems designed for environments where data cannot leave the building** — offline RAG pipelines, multi-agent orchestration, and data engineering at 200GB/day scale. Everything I build prioritizes GDPR compliance, zero data leakage, and vendor independence.

```
Privacy-First RAG Pipelines    ·    Multi-Agent Orchestration    ·    Data Engineering (Spark + Scala)
Local LLM Deployment           ·    Multi-Cloud Infrastructure   ·    Security & GDPR Compliance
```

---

## ⚡ Featured Projects

<table>
<tr>
<td width="50%" valign="top">

### 🔒 [Codex One](https://github.com/GuilhermeGors/Codex_One)
**Privacy-first enterprise knowledge base — fully offline RAG**

Zero external API calls. Zero data leakage. Local LLMs via Ollama combined with real-time vector retrieval across PDFs and ePubs. Precise source attribution for audit-ready compliance.

`Python` `Ollama` `LangChain` `ChromaDB` `FastAPI`

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

### 🤖 JobMatch
**Multi-agent RAG platform for HR automation**

Automated talent screening reducing manual evaluation by 95%. Semantic search over unstructured data, dynamic ranking, LLM-agnostic inference (OpenAI / Gemini / local). Real-time analytics via WebSockets.

`FastAPI` `LangChain` `React` `WebSockets` `Vector DB`

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
graph TD
    classDef client fill:#1a1a2e,stroke:#16213e,stroke-width:2px,color:#e0e0e0
    classDef gateway fill:#e67e22,stroke:#d35400,stroke-width:2px,color:#fff
    classDef orch fill:#2980b9,stroke:#1f618d,stroke-width:2px,color:#fff
    classDef agent fill:#27ae60,stroke:#1e8449,stroke-width:2px,color:#fff
    classDef data fill:#8e44ad,stroke:#71368a,stroke-width:2px,color:#fff
    classDef infra fill:#c0392b,stroke:#922b21,stroke-width:2px,color:#fff

    User["Client App"]:::client

    subgraph Security["Security Layer"]
        GW["API Gateway + Auth"]:::gateway
        Vault["Secrets Manager"]:::infra
    end

    subgraph Core["AI Orchestration"]
        Orch["Semantic Router"]:::orch
        Ctx["Context Manager"]:::orch
    end

    subgraph Agents["Agent Pool"]
        RAG["RAG Agent"]:::agent
        Eval["Analysis Agent"]:::agent
        Compliance["GDPR Agent"]:::agent
    end

    subgraph Store["Data Layer"]
        VDB[("Vector DB")]:::data
        Cache[("Redis")]:::data
        LLM["LLM · Local or API"]:::infra
    end

    User -->|HTTPS / WS| GW
    GW <-->|Keys| Vault
    GW --> Orch
    Orch <--> Ctx
    Orch --> RAG
    Orch --> Eval
    Orch --> Compliance
    RAG <--> VDB
    RAG --> LLM
    Eval --> LLM
    Compliance -->|PII Scan| VDB
    Orch --> Cache
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

## 📐 Technical Approach

```
1. PRIVACY BY DESIGN       →  Data never leaves the infrastructure. Local LLMs, on-prem vector stores.
2. VENDOR INDEPENDENCE      →  LLM-agnostic pipelines. Swap OpenAI ↔ Gemini ↔ Ollama without code changes.
3. SCALABLE DATA PIPELINES  →  Apache Spark + Scala for 200GB/day distributed processing.
4. SECURITY-FIRST           →  AWS Secrets Manager, Checkmarx scans, zero hardcoded credentials.
5. SYSTEMS THINKING         →  42 São Paulo foundations — C, Unix, memory management, no abstractions.
```

---

## 🎓 Background

**42 São Paulo** — Software Engineering *(Peer-to-peer, zero-professor model)*
**Unisinos** — Analysis & Systems Development
**Bayswater College, London** — Exchange Program

🥈 **Moving The Cities** — Unisinos × SAP × FH Münster (Germany) × UAS7
🏆 **Geração Caldeira** — First Class, Institute Caldeira

---

<div align="center">

**Open to AI Platform Engineer & RAG Systems roles in Europe**
Fluent in English · Eligible for relocation

[![LinkedIn](https://img.shields.io/badge/Connect-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/guilhermegors/)
[![Email](https://img.shields.io/badge/Contact-Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:guilhermegors@gmail.com)

</div>

<details>
<summary>📊 GitHub Analytics</summary>
<br>
<div align="center">

![Stats](https://github-readme-stats.vercel.app/api?username=GuilhermeGors&show_icons=true&theme=default&hide_border=true&count_private=true&bg_color=00000000)
![Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=GuilhermeGors&layout=compact&hide_border=true&bg_color=00000000)

</div>
</details>
