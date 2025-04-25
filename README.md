# 🌍 PandemicLLM - Enhanced Forecasting with Large Language Models

PandemicLLM uses Large Language Models for real-time hospital trend forecasting during pandemics. It incorporates multimodal inputs like COVID-19 data, policies, genomic variants, and simulated wastewater data. Key improvements include refined conversational prompts and Falcon-7B-Instruct for efficient, interpretable predictions.

This repository implements and improves upon the research from the paper:

**📄 Title**: *PandemicLLM: LLMs for Real-Time Pandemic Forecasting*  
**👩‍🔬 Authors**: Yang, D., Yang, S., Subramanian, R., Subbaswamy, A., Wang, Y., & Ghassemi, M.  
**🧾 Paper**: [arXiv:2404.06962](https://arxiv.org/abs/2404.06962)  
**🧪 Original GitHub**: [PandemicLLM GitHub](https://github.com/miemieyanga/pandemicllm)

---

## 📊 Project Summary

This project replicates and enhances the PandemicLLM framework, which reimagines hospitalization trend forecasting as a natural language task using **Large Language Models (LLMs)**.

### 🎯 Objectives

- Replicate the core methodology using Falcon-7B-Instruct.
- Integrate **simulated wastewater surveillance data** as a novel feature.
- Improve **prompt structure** for human readability.
- Make the model lightweight enough to run on consumer-grade hardware using **4-bit quantization**.

---

## 📦 Dataset

We used pre-processed data from:
- COVID-19 case and hospitalization time series
- Public health policy changes
- Genomic variant distribution
- Demographics
- 🚰 Simulated wastewater surveillance (custom feature)

Data covers **50 U.S. states** over **104 weeks (2021–2023)**.

---

## ⚙️ Setup & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/minalnaranje/PandemicLLM-Enhancements.git
cd PandemicLLM-Enhancements


