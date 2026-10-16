# Syed Muhammad Mehran

**AI Engineer** — agentic LLM systems, backend engineering, applied ML
Lahore, Pakistan · Open to remote roles

---

## About

I build LLM systems that are meant to be inspected and trusted: schema-enforced outputs, deterministic checks alongside model judgment, confidence-gated human review, and observability on every run. My work covers the full path from database schema and API design to deployment to debugging model behavior.

I am completing an MS in Data Science at FAST-NUCES, Lahore. My thesis (in progress) is on agentic video moment retrieval using multi-agent orchestration.

## Focus

- **Agentic systems:** multi-agent LangGraph pipelines, reflection and critic loops, checkpointed state, human-in-the-loop routing
- **LLM reliability:** typed outputs with Pydantic, arithmetic and schema guardrails against hallucination, per-agent latency, token and cost tracking
- **Backend and deployment:** FastAPI, async SQLAlchemy, PostgreSQL, Docker, AWS
- **Applied ML:** PyTorch, parameter-efficient fine-tuning, sequence modeling, time-series forecasting

## Selected Projects

### [Smart Invoice Extraction System](https://github.com/S-Mehran/llm-invoice-pipeline)

A full-stack system that extracts structured data from invoices with a two-agent LangGraph pipeline (extraction and reflection) on Gemini 2.5 Flash.

- Confidence-gated routing sends uncertain extractions to a human Review Workbench with an inline vendor-onboarding flow.
- Line-item arithmetic (quantity, net amount, tax %, total) is enforced as schema-level constraints, flagging inconsistencies beyond a 0.05 tolerance before they reach review.
- An observability dashboard tracks latency, token usage, cost and confidence per agent, with drill-down into individual critiques.
- Normalized 7-table PostgreSQL schema; Dockerized FastAPI on AWS EC2, React/TypeScript on Vercel, Supabase Postgres, S3 storage; typed API client generated from the OpenAPI schema.

`FastAPI` `SQLAlchemy` `PostgreSQL` `LangGraph` `Gemini` `React` `TypeScript` `Docker` `AWS`

### [Parameter-Efficient Fine-Tuning: Full FT vs. LoRA vs. QLoRA vs. IA3](https://github.com/S-Mehran/REPO_NAME)

Controlled comparison on IMDb sentiment classification (RoBERTa-base, DistilBERT) across two seeds, with rank, module-placement and learning-rate ablations.

- LoRA (r=16, attention + FFN) reached 91.97% accuracy with 2.95M trainable parameters, 42x fewer than full fine-tuning (124.6M).
- QLoRA (NF4) cut peak VRAM to 0.626 GB, about 83% below full fine-tuning, at 89.5% accuracy.

`PyTorch` `Hugging Face Transformers` `PEFT` `bitsandbytes`

### [Sequence Modeling and Neural Machine Translation](https://github.com/S-Mehran/REPO_NAME)

RNN, LSTM and GRU cells implemented from scratch, with an English–German Seq2Seq model and Bahdanau, Luong and scaled dot-product attention built on top. Five encoder–decoder variants were benchmarked on 100K WMT14 pairs (BLEU, BERTScore, METEOR), with attention heatmaps used to verify cross-lingual alignment.

`PyTorch` `NumPy`

### [Stock Market Forecasting (Kaggle)](https://github.com/S-Mehran/REPO_NAME)

End-to-end time-series pipeline predicting excess stock returns from 30 years of market data: lag and Fourier features, SVD to retain 95% of variance, and XGBoost, Random Forest and LSTM models with tuning. A 3-layer LSTM with layer normalization achieved the best Sharpe ratio (1.2).

`PyTorch` `scikit-learn` `Pandas`

### [Freelance Platform Backend](https://github.com/S-Mehran/REPO_NAME)

REST API with JWT authentication, OTP verification and role-based access control for client and freelancer profiles. 6 entities, 42 endpoints, TypeORM migrations, and a layered controller–service–repository structure.

`Node.js` `Express` `TypeScript` `PostgreSQL` `TypeORM`

Additional work includes a PySpark movie recommender (ALS and neural collaborative filtering), YOLOv8 traffic-sign detection, and language modeling and embeddings from scratch. These are available in my repositories.


## Experience

**Systems Limited**, Intern

Built real-time monitoring and log-analysis dashboards for 35+ enterprise file-transfer pipelines on Azure (Node.js, Server-Sent Events, Azure Storage). 

## Technical Stack

| Area | Tools |
| --- | --- |
| LLM and agents | LangGraph, LangChain, Gemini, OpenAI API, Pydantic |
| Backend | FastAPI, SQLAlchemy (async), Alembic, PostgreSQL, Node.js, Express |
| Frontend | React, TypeScript, TanStack Query |
| Cloud and infrastructure | AWS (EC2, S3), Docker, Azure (Storage, Tables), Vercel, Supabase |
| Machine learning | PyTorch, Hugging Face Transformers, PEFT, scikit-learn, PySpark, TensorFlow, OpenCV |
| Data | Pandas, NumPy, SQL |

## Contact

- Email: smehran.mme@gmail.com
- LinkedIn: [linkedin.com/in/s-mehran](https://www.linkedin.com/in/s-mehran)
