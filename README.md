# Financial Fraud Detection and Advisory Assistant

**IT9204: Emerging Technologies in AI**
**Student:** Hatem Isa | **ID:** 202508993
**Programme:** MSc in Artificial Intelligence, Bahrain Polytechnic

## Overview

A cloud based AI system that helps fraud analysts and bank risk officers detect and respond to financial fraud. The system integrates four AI components on Microsoft Azure into a single agent that can analyze transactions, retrieve compliance policies, and provide grounded recommendations.

## System Architecture

The system is deployed across five integrated layers:

1. **LLM Layer** — Azure OpenAI (gpt-4o-mini) for reasoning and response generation
2. **RAG Component** — Azure AI Search with text-embedding-3-small over 4 bank policy documents
3. **Agent Component** — Agentic loop with 3 registered tools using function calling
4. **ML Component** — Azure AutoML VotingEnsemble (AUC 0.98383) deployed as a real time endpoint
5. **Decision Logic** — Deterministic keyword based router for transparent query classification

## Tools

| Tool | Purpose |
|---|---|
| `predict_fraud_risk` | Calls Azure ML endpoint for fraud probability |
| `retrieve_policy` | Vector search over compliance documents (top 3 chunks) |
| `calculate_risk_score` | Deterministic composite risk score (0 to 10) |

## Evaluation Results

| Metric | Result |
|---|---|
| Routing Accuracy | 100% (14/14) |
| Tool Selection Accuracy | 78.6% (11/14) |
| Forbidden Policy Violations | 0 |
| AutoML AUC Weighted | 0.98383 |
| AutoML Accuracy | 0.99199 |
| Models Evaluated | 342 |

```
## Repository Structure
A - Data and Knowledge Layer/ # RAG pipeline and policy documents
B - Machine Learning Component/ # Dataset, AutoML training scripts
C - Agent System/ # Agent loop and tool definitions
D - Decision and Reasoning Layer/# Deterministic query router
E - System Integration/ # Main entry point and config
F - Evaluation and Analysis/ # Evaluation scripts and results
I - References/ # Academic papers cited in report
```

## Project Resources

| Resource | Link |
|---|---|
| Demo Video | https://youtu.be/_bll4nqog1o |
| Dataset | https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud |

## Tech Stack

Python, Azure OpenAI, Azure AutoML, Azure AI Search, Azure ML Endpoints

## AI Disclosure

This project was completed with the assistance of AI tools:

- **Claude (Anthropic)** was used to assist with code generation, debugging, and report writing. All code was reviewed, tested, and validated by the student. All Azure services were configured, deployed, and tested by the student. All evaluation results are real outputs from the deployed system.
- **Perplexity AI** was used to assist with identifying relevant academic references for the literature review. All referenced papers were downloaded, read, and verified by the student before inclusion.

The system design, architectural decisions, choice of technologies, evaluation methodology, and interpretation of results are the student's own work.
