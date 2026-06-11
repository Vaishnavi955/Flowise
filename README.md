# SCM Assistant

## Public Chatbot URL

https://cloud.flowiseai.com/chatbot/8385aae6-1cda-4bdf-a765-d2b509fd3b7a

## LLM Used

* Groq LLM
* Model: llama-3.1-8b-instant

## Embedding Model

* Hugging Face Embeddings
* Model: BAAI/bge-base-en-v1.5

## Knowledge Base

* PDF Documents
* CSV Dataset

## Chunk Configuration Experiments

### Configuration 1

* Chunk Size: 500
* Chunk Overlap: 50

Results:

* PDF: 35 chunks
* CSV: ~4000 chunks

### Configuration 2 (Selected)

* Chunk Size: 1000
* Chunk Overlap: 100

Results:

* PDF: 19 chunks
* CSV: ~2000 chunks

Reason for Selection:

Configuration 2 reduced the total number of chunks while preserving context and improving retrieval efficiency.

---

## Validation Questions and Answers

### Q1

**Question:** Which Tier-3 suppliers have an active disruption flag, and what response level applies per policy?

**Chatbot Answer (Verbatim):**

> 11 Tier-3 suppliers: Dravex Components India, Plataforma Metales SA, Maghreb Castworks, Helios Pack
Greece, Cerromax Mineria, Orinoco Pack SAPI, Quetzal Textiles, Sibertek Molding, Archipelago PCB Corp,
Varna Electronics EAD, Deltaforge Vietnam. All are High Risk with an active flag → Level 3 Activate per
Policy §9 (CPO escalation + alternate supplier at minimum 40% volume)

---

### Q2

**Question:** Which suppliers qualify for the annual Volume Rebate Program and how many are there?

**Chatbot Answer (Verbatim):**

> Tier-1 suppliers qualify for the annual Volume Rebate Program if they have an On-Time Delivery (OTD) rate of 93.0% or above, a Defect Rate below 0.5%, and a Sustainability Score of 85 or above for a full calendar year. The rebate is 2.5% of the total annual invoice value. However, the documents do not specify how many suppliers qualify for this program.

---

### Q3

**Question:** Which region has the highest total PO value, and does it breach the concentration limit?

**Chatbot Answer (Verbatim):**

> Based on the provided documents, the region with the highest total PO value is EMEA.
The total PO value for EMEA is $288,680.58 ($166,487.40 from PO-10758 and $122,193.18 from PO-11338).
To determine if this breaches the concentration limit, we would need to know the total annual procurement spend.
The concentration limit states that no single region may account for more than 45% of the total annual procurement spend.
However, we do not have enough information to calculate the total annual procurement spend, so we cannot determine if the concentration limit is breached.

---

### Q4

**Question:** Which suppliers are on Supplier Watch List (SWL) status and what does it restrict?

**Chatbot Answer (Verbatim):**

> 11 suppliers (Compliance Score < 60): Deltaforge Vietnam, Maghreb Castworks, Helios Pack Greece,
Cerromax Mineria, Orinoco Pack SAPI, Varna Electronics EAD, Quetzal Textiles, Plataforma Metales SA,
Archipelago PCB Corp, Dravex Components India, Sibertek Molding. SWL restricts new PO issuance to 20%
of prior quarter volume (Policy §3.4)

---

### Q5

**Question:** Which product category has the highest average defect rate and does it exceed the Tier-2 limit?

**Chatbot Answer (Verbatim):**

> Mechanical Components — average 2.12% across 360 POs. Below the Tier-2 ceiling of 2.50% (Policy §3.2),
so no breach — but approaching the limit.

---

## Improvements for Future Work

1. Add metadata-based filtering to improve retrieval accuracy.
2. Implement source citations in responses.
3. Use hybrid search (keyword + semantic search).
4. Introduce reranking for better chunk selection.
5. Separate retrieval pipelines for PDF and CSV data.
6. Optimize CSV ingestion to reduce retrieval noise.
7. Add dashboard visualizations for supply chain insights.
8. Improve supplier-level analytics and reporting.

---

## Summary

The SCM Assistant is a RAG-based chatbot built using Flowise, Groq LLM, and Hugging Face Embeddings. Multiple chunking configurations were evaluated, and a chunk size of 1000 with an overlap of 100 was selected as the best trade-off between retrieval quality and efficiency. The system successfully answers questions using information retrieved from PDF and CSV knowledge sources.
