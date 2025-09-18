# Hate Speech and Offensive Language Detection

This project implements a deep learning pipeline to detect **hate speech** and **offensive language** in tweets.  
Using **LSTM (Long Short-Term Memory)** networks and **parallelized data augmentation** (via back-translation), the model achieves ~90% validation accuracy with balanced F1-scores.  

---

## 📌 Motivation
The rise of harmful and toxic content on social media platforms has made it crucial to build automated systems that can detect and filter hate speech effectively.  
This project explores a machine learning approach for safer online communities.

---

## 📊 Dataset
- **Source:** [Kaggle - Hate Speech and Offensive Language Detection](https://www.kaggle.com/datasets/thedevastator/hate-speech-and-offensive-language-detection)  
- **Size:** ~25k annotated tweets  
- **Classes:**  
  - Hate Speech  
  - Offensive Language  
  - Neither  
- **Challenge:** Class imbalance (offensive language is dominant)

---

## ⚙️ Methods
1. **Data Preprocessing**
   - Removed usernames, URLs, hashtags, punctuation, and stopwords  
   - Lowercasing and text normalization  
   - Tokenization and padding for uniform sequence length  

2. **Parallel Data Augmentation**
   - Applied **back-translation** (English → another language → English)  
   - Used Python **multiprocessing** to reduce runtime (speedup ~3.8x)  

3. **Model Architecture**
   - Embedding Layer (200-dim vectors)  
   - LSTM + CNN layers with Dropout  
   - Dense layers (ReLU + Softmax output)  
   - **Optimizer:** Adam | **Loss:** Categorical Crossentropy  
   - **Metrics:** Accuracy, Precision, Recall, F1-score  

---

## 📈 Results
- **Validation Accuracy:** ~90%  
- **Validation F1-Score:** ~0.89  
- Strong classification performance with some confusion between *Hate Speech* and *Offensive Language*  
- Augmentation improved generalization and reduced overfitting  

---

## 🔮 Future Work
- Transformer models (BERT, RoBERTa, DistilBERT)  
- Multilingual datasets for global hate speech detection  
- Class imbalance handling with SMOTE/class weights  
- Explainable AI dashboards (e.g., SHAP, LIME)  
- Deployment as a web app for real-time moderation  

---

## 📂 Project Files
- `hate modified.ipynb` → Main Jupyter Notebook  
- `Presentation.pptx` → Project presentation slides  
- `Report of Project.pdf` → Full project report  

---

## 👨‍💻 Author
**Raiyanul Islam Siam**  
B.Sc. in Computer Science, BRAC University  
📧 raiyanul.islam.siam@g.bracu.ac.bd  

---

## 📝 Citation
If you use this work, please cite:  
Davidson, T., Warmsley, D., Macy, M., & Weber, I. (2017). *Automated hate speech detection and the problem of offensive language*. ICWSM.  
