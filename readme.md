# 🎵 Music Genre Classification  

[![Live App on Hugging Face](https://img.shields.io/badge/🤗_Live_App-Hugging_Face-blue?style=for-the-badge)](https://huggingface.co/spaces/Deepak-002/Music-Genre-Classification)

---

## 📌 Project Overview  
This project builds an end-to-end **machine learning system** that automatically classifies an input audio track into its corresponding music genre.  

Given a short audio clip, the system extracts meaningful acoustic features and predicts the most probable genre such as **Classical, Jazz, Pop, Rock, Metal**, and more.

---

## 📊 Dataset  
We use the **GTZAN Dataset – Music Genre Classification**:  
- 🎧 1,000 audio tracks  
- ⏱️ Each track is 30 seconds  
- 🎼 10 genres:  
  *Blues, Classical, Country, Disco, Hiphop, Jazz, Metal, Pop, Reggae, Rock*  

📎 Dataset Link:  
https://www.kaggle.com/datasets/andradaolteanu/gtzan-dataset-music-genre-classification  

---

## 🧠 Technical Architecture  

This project uses a **Dual-Model Pipeline** to compare different feature extraction strategies:

### 🔹 1. YAMNet Pipeline (TensorFlow)
- Uses Google’s **YAMNet** pre-trained audio model  
- Extracts deep acoustic embeddings from **16kHz audio**  
- Uses a custom classification head  
- Exported in `.keras` format for stability  

---

### 🔹 2. MERT Pipeline (Transformer-based)
- Uses **MERT (Music Representation Transformer)**  
- Processes **24kHz audio**  
- Extracts rich musical embeddings using transformer layers  
- Classification performed using an optimized **MLP model**

---

## 🛠️ Model Training Pipeline  

Training is handled via `model_generation.ipynb` with a **feature-based approach**:

- 📥 **Data Loading:** Precomputed embeddings (`.npy`)  
- ⚖️ **Stratified Split:** 80/20 split  
- 🧮 **Model:** MLP with hidden layers `(256, 128)`  
- ⚡ **Optimization:** Adam + Early Stopping  
- 📊 **Evaluation:** Accuracy, Macro F1-score, Confusion Matrix  
- 💾 **Export:** Model, Scaler, Label Encoder (`.pkl`)  

---

## ⚙️ Local Setup  

### 1️⃣ Clone Repository
```bash
git clone https://github.com/your-username/Music-Genre-Classification.git
cd Music-Genre-Classification
