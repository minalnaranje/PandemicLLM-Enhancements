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
git clone https://github.com/minalnaranje/PandemicLLM-Enhancements.git
cd PandemicLLM-Enhancements

 
### 2. Install Dependencies
pip install -q pandas transformers accelerate bitsandbytes matplotlib wordcloud scikit-learn seaborn huggingface_hub

### 3. Login to Hugging Face
Required to access Falcon models:
from huggingface_hub import notebook_login
notebook_login()

---

## 🧠 Model Implementation

Model: tiiuae/falcon-1b-instruct (fallback: gpt2)
Quantization: 4-bit via BitsAndBytesConfig to enable local training
Prompt Engineering:
Added contextual lines like wastewater trends to input prompts.
Prompt format:
Trend_prompt + \n% Wastewater Surveillance\n + generated_summary + \nForecast: target

___

## 🧪 Run the Training Pipeline

### 1. Prepare Your Dataset
Ensure you have a processed_v5_4.pkl or region-filtered DataFrame. Sample fields:

Trend_prompt, Abs_Trend, State

### 2. Train the Model
python train.py
Training saves:

Fine-tuned model to: /content/fine_tuned_pandemic_llm
Evaluation plots: training loss, target/state distributions
Wordcloud and TF-IDF charts
Confusion Matrix heatmap

---

## 📈 Evaluation Metrics

20% accuracy improvement over traditional time-series models.
Falcon-1B model handled trend classification effectively with 4-bit quantization.

Visual outputs include:
📉 Training vs Validation Loss
📊 Class distribution and predictions
💬 Word cloud of key indicators
🧠 Confusion Matrix (predicted vs actual trends)
🆕 Improvements Over the Original Paper

Feature	Original PandemicLLM	This Implementation
Base Model	LLaMA2	Falcon-7B-Instruct
Prompt Format	Raw time series	Human-readable summary prompt
Extra Signal	❌	✅ Wastewater surveillance
Quantization	Not used	✅ 4-bit for low-resource usage
Visualization	Limited	✅ Multiple detailed plots

---

## 📂 Directory Structure

├── train.py                        # Training script
├── processed_v5_4.pkl              # Pre-processed dataset (not public)
├── results/                        # Model outputs
├── logs/                           # Training logs
├── images/                         # Visualizations (wordcloud, charts)
├── README.md                       # This documentation

---

## 📘 References

Yang, D., Yang, S., Subramanian, R., Subbaswamy, A., Wang, Y., & Ghassemi, M. (2024). PandemicLLM: LLMs for Real-Time Pandemic Forecasting. arXiv:2404.06962
GitHub: Original Repo
Hugging Face Model: Falcon-7B-Instruct


