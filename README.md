<div align="center">

# Syed Muhammad Mehran

**AI Engineer** · Agentic LLM systems · Backend engineering · Applied ML

Lahore, Pakistan · Open to remote roles

[![LinkedIn](https://img.shields.io/badge/LinkedIn-s--mehran-24292f?style=flat-square)](https://www.linkedin.com/in/s-mehran)
[![Email](https://img.shields.io/badge/Email-smehran.mme%40gmail.com-24292f?style=flat-square&logo=gmail&logoColor=white)](mailto:smehran.mme@gmail.com)

</div>

---

## About

I build LLM systems that are meant to be inspected and trusted: schema-enforced outputs, deterministic checks alongside model judgment, confidence-gated human review, and observability on every run. My work covers the full path from database schema and API design to deployment to debugging model behavior.

I am completing an MS in Data Science at FAST-NUCES, Lahore. My thesis (in progress) is on agentic video moment retrieval using a Plan–Observe–Reflect multi-agent loop.

<table align="center">
  <tr>
    <td align="center"><b>42x</b></td>
    <td align="center"><b>~83%</b></td>
    <td align="center"><b>35+</b></td>
    <td align="center"><b>30 min → &lt;1 min</b></td>
  </tr>
  <tr>
    <td align="center"><sub>fewer trainable parameters<br>with LoRA vs. full fine-tuning</sub></td>
    <td align="center"><sub>lower peak VRAM<br>with QLoRA</sub></td>
    <td align="center"><sub>enterprise pipelines<br>monitored in real time</sub></td>
    <td align="center"><sub>production<br>troubleshooting time</sub></td>
  </tr>
</table>

## Focus

- **Agentic systems:** multi-agent LangGraph pipelines, reflection and critic loops, checkpointed state, human-in-the-loop routing
- **LLM reliability:** typed outputs with Pydantic, arithmetic and schema guardrails against hallucination, per-agent latency, token and cost tracking
- **Backend and deployment:** FastAPI, async SQLAlchemy, PostgreSQL, Docker, AWS
- **Applied ML:** PyTorch, parameter-efficient fine-tuning, sequence modeling, time-series forecasting

## Selected Projects

### [Smart Invoice Extraction System](https://github.com/S-Mehran/llm-invoice-pipeline)

A full-stack system that extracts structured data from invoices with a two-agent LangGraph pipeline (extraction and reflection) on Gemini 2.5 Flash.

```mermaid
%%{init: {'theme': 'neutral'}}%%
flowchart LR
    A[Invoice upload] --> B[(S3 storage)]
    B --> C["Extraction agent<br/>Gemini 2.5 Flash"]
    C --> D["Schema and arithmetic<br/>guardrails"]
    C --> E["Reflection agent<br/>critique and confidence"]
    D --> F{Routing}
    E --> F
    F -->|Confident, consistent| G[(PostgreSQL)]
    F -->|Uncertain or flagged| H[Human review workbench]
    H --> G
```

- Confidence-gated routing sends uncertain extractions to a Review Workbench with an inline vendor-onboarding flow.
- Line-item arithmetic (quantity, net amount, tax %, total) is enforced as schema-level constraints, flagging inconsistencies beyond a 0.05 tolerance before they reach review.
- An observability dashboard tracks latency, token usage, cost and confidence per agent, with drill-down into individual critiques.
- Normalized 7-table PostgreSQL schema; Dockerized FastAPI on AWS EC2, React/TypeScript on Vercel, Supabase Postgres, S3 storage; typed API client generated from the OpenAPI schema.

![FastAPI](https://img.shields.io/badge/FastAPI-24292f?style=flat-square&logo=fastapi&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-24292f?style=flat-square)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-24292f?style=flat-square&logo=postgresql&logoColor=white)
![React](https://img.shields.io/badge/React-24292f?style=flat-square&logo=react&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-24292f?style=flat-square&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-24292f?style=flat-square)

### [Parameter-Efficient Fine-Tuning: Full FT vs. LoRA vs. QLoRA vs. IA3](https://github.com/S-Mehran/Fine-Tuning-Methods)

Controlled comparison on IMDb sentiment classification (RoBERTa-base, DistilBERT) across two seeds, with rank, module-placement and learning-rate ablations.

- LoRA (r=16, attention + FFN) reached 91.97% accuracy with 2.95M trainable parameters, 42x fewer than full fine-tuning (124.6M).
- QLoRA (NF4) cut peak VRAM to 0.626 GB, about 83% below full fine-tuning, at 89.5% accuracy.

![PyTorch](https://img.shields.io/badge/PyTorch-24292f?style=flat-square&logo=pytorch&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging_Face-24292f?style=flat-square&logo=huggingface&logoColor=white)
![PEFT](https://img.shields.io/badge/PEFT-24292f?style=flat-square)
![bitsandbytes](https://img.shields.io/badge/bitsandbytes-24292f?style=flat-square)

### [Neural Machine Translation: Seq2Seq and Attention Variants](https://github.com/S-Mehran/Machine-Translation---Comparison-among-base-models-and-Attention-Variants)

RNN, LSTM and GRU cells implemented from scratch, with an English–German Seq2Seq model and Bahdanau, Luong and scaled dot-product attention built on top. Five encoder–decoder variants were benchmarked on 100K WMT14 pairs (BLEU, BERTScore, METEOR), with attention heatmaps used to verify cross-lingual alignment.

![PyTorch](https://img.shields.io/badge/PyTorch-24292f?style=flat-square&logo=pytorch&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-24292f?style=flat-square&logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-24292f?style=flat-square)

### [Hull Tactical Market Prediction (Kaggle)](https://github.com/S-Mehran/Hull-Tactical-Market-Prediction)

End-to-end time-series pipeline predicting excess stock returns from 30 years of market data: lag and Fourier features, SVD to retain 95% of variance, and XGBoost, Random Forest and LSTM models with tuning. A 3-layer LSTM with layer normalization achieved the best Sharpe ratio (1.2).

![PyTorch](https://img.shields.io/badge/PyTorch-24292f?style=flat-square&logo=pytorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-24292f?style=flat-square&logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-24292f?style=flat-square&logo=pandas&logoColor=white)

### [Freelance Platform Backend](https://github.com/S-Mehran/Freelance-Platform)

REST API with JWT authentication, OTP verification and role-based access control for client and freelancer profiles. 6 entities, 42 endpoints, TypeORM migrations, and a layered controller–service–repository structure.

![Node.js](https://img.shields.io/badge/Node.js-24292f?style=flat-square&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-24292f?style=flat-square&logo=express&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-24292f?style=flat-square&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-24292f?style=flat-square&logo=postgresql&logoColor=white)
![TypeORM](https://img.shields.io/badge/TypeORM-24292f?style=flat-square)

<details>
<summary>Additional work</summary>

<br>

- **Movie recommendation system:** PySpark pipeline combining fuzzy k-means clustering, ALS and neural collaborative filtering; 24.3% and 30% HitRatio@10 on MovieLens 100K and 1M.
- **Traffic sign detection:** YOLOv8m fine-tuned on TT100K, reaching 70% mAP@50 and 80% precision.
- **Language modeling and embeddings:** N-gram models with smoothing and perplexity analysis, Byte-Pair Encoding for Urdu, and TF-IDF, PPMI and Word2Vec embeddings evaluated intrinsically and extrinsically.

</details>

## Currently

- Building a multi-agent insurance claims auditor with LangGraph, RAG and FastAPI. Agents cross-check claim decisions against policy documents and evidence, and route ambiguous cases to human review with a cited report.
- Thesis work on agentic video moment retrieval at FAST-NUCES.

## Experience

**Systems Limited**, Intern
Built real-time monitoring and log-analysis dashboards for 35+ enterprise file-transfer pipelines on Azure (Node.js, Server-Sent Events, Azure Storage). Reduced production troubleshooting time from about 30 minutes to under 1 minute.

## Technical Stack

| Area | Tools |
| --- | --- |
| **LLM and agents** | ![LangGraph](https://img.shields.io/badge/LangGraph-24292f?style=flat-square) ![LangChain](https://img.shields.io/badge/LangChain-24292f?style=flat-square&logo=langchain&logoColor=white) ![Gemini](https://img.shields.io/badge/Gemini-24292f?style=flat-square&logo=googlegemini&logoColor=white) ![OpenAI](https://img.shields.io/badge/OpenAI_API-24292f?style=flat-square) ![Pydantic](https://img.shields.io/badge/Pydantic-24292f?style=flat-square&logo=pydantic&logoColor=white) |
| **Backend** | ![FastAPI](https://img.shields.io/badge/FastAPI-24292f?style=flat-square&logo=fastapi&logoColor=white) ![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-24292f?style=flat-square&logo=sqlalchemy&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-24292f?style=flat-square&logo=postgresql&logoColor=white) ![Node.js](https://img.shields.io/badge/Node.js-24292f?style=flat-square&logo=nodedotjs&logoColor=white) ![Express](https://img.shields.io/badge/Express-24292f?style=flat-square&logo=express&logoColor=white) |
| **Frontend** | ![React](https://img.shields.io/badge/React-24292f?style=flat-square&logo=react&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-24292f?style=flat-square&logo=typescript&logoColor=white) ![TanStack Query](https://img.shields.io/badge/TanStack_Query-24292f?style=flat-square&logo=reactquery&logoColor=white) |
| **Cloud and infrastructure** | ![AWS](https://img.shields.io/badge/AWS-24292f?style=flat-square) ![Docker](https://img.shields.io/badge/Docker-24292f?style=flat-square&logo=docker&logoColor=white) ![Azure](https://img.shields.io/badge/Azure-24292f?style=flat-square) ![Vercel](https://img.shields.io/badge/Vercel-24292f?style=flat-square&logo=vercel&logoColor=white) ![Supabase](https://img.shields.io/badge/Supabase-24292f?style=flat-square&logo=supabase&logoColor=white) |
| **Machine learning** | ![PyTorch](https://img.shields.io/badge/PyTorch-24292f?style=flat-square&logo=pytorch&logoColor=white) ![Hugging Face](https://img.shields.io/badge/Hugging_Face-24292f?style=flat-square&logo=huggingface&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-24292f?style=flat-square&logo=scikitlearn&logoColor=white) ![PySpark](https://img.shields.io/badge/PySpark-24292f?style=flat-square&logo=apachespark&logoColor=white) ![TensorFlow](https://img.shields.io/badge/TensorFlow-24292f?style=flat-square&logo=tensorflow&logoColor=white) ![OpenCV](https://img.shields.io/badge/OpenCV-24292f?style=flat-square&logo=opencv&logoColor=white) |
| **Data** | ![Pandas](https://img.shields.io/badge/Pandas-24292f?style=flat-square&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-24292f?style=flat-square&logo=numpy&logoColor=white) ![SQL](https://img.shields.io/badge/SQL-24292f?style=flat-square) |
