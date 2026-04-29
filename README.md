# NLP Conversation Analysis for E-commerce Chatbots

## Overview
This project focuses on analyzing customer conversations from e-commerce chatbots.  
The objective is to extract meaningful insights from user interactions in order to improve customer experience and support business decisions.

The system includes:
- Intent classification
- Sentiment analysis
- Churn risk detection

---

## Features
- Intent classification using **SetFit (Sentence Transformers + contrastive learning)**
- Sentiment analysis (separate model)
- Churn risk estimation based on intent + sentiment + behavioral signals
- Preprocessing with placeholder normalization (e.g., [ORDER], [PRODUCT])
- Evaluation using F1-score and accuracy

---

## Technologies
- Python
- HuggingFace Transformers
- **SetFit (primary model for intent classification)**
- Scikit-learn
- Pandas / NumPy
- Matplotlib

---

## Dataset
- Bitext E-commerce Customer Support Dataset
- Contains labeled customer queries across multiple intent categories
- High presence of placeholders (e.g., {{Order Number}}, {{Product Name}})

---

## Preprocessing
- Cleaning text data
- Replacing placeholders with normalized tokens:
  - `{{Order Number}}` → `[ORDER]`
  - `{{Product Name}}` → `[PRODUCT]`
- Tokenization and preparation for transformer models

---

## Pipeline
1. Data cleaning and preprocessing
2. Placeholder normalization
3. Intent classification using **SetFit**
4. Sentiment analysis using a separate model
5. Churn risk estimation:
   - Rule-based or lightweight model
   - Combines intent + sentiment + interaction signals

---

## Model Details

### Intent Classification (SetFit)
- Uses Sentence Transformers embeddings
- Contrastive learning for few-shot/generalization
- Better generalization compared to previous BERT-based approach

### Sentiment Analysis
- Independent model
- Used as input for churn detection

### Churn Risk
- Based on:
  - Negative sentiment
  - Critical intents (complaints, refunds, delays)
  - Behavioral signals

---

## Results
- F1-score (macro): ~0.65 (external test)
- Accuracy: ~0.87
- Improved performance compared to previous model (DitBERT)

---


---

## Future Work
- Improve performance with more training epochs (SetFit)
- Add deep learning-based churn prediction
- Deploy as API (FastAPI)
- Integrate real-time chatbot analytics

---

## Author
Nour Ayari  
Software Engineering Student – INSAT
