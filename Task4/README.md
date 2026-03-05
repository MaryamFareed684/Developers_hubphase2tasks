#Auto Tagging Support Tickets Using LLM

##  Objective

The objective of this project is to automatically classify free-text customer support tickets into relevant categories using a Large Language Model (LLM).

The system predicts the **Top 3 most probable tags** for each ticket and compares the performance of:

- Zero-Shot Classification  
- Prompt-Engineered (Enhanced) Classification  

This project demonstrates LLM-based text classification, multi-class prediction, and ranking without traditional model training.



##  Dataset

A small support ticket dataset was created containing free-text customer issues such as:

- Login problems  
- Payment failures  
- Technical bugs  
- Subscription requests  
- Refund issues  
- Performance complaints  

Each ticket was manually assigned a **True Label** to evaluate model accuracy.

---

##  Methodology / Approach

### 1️ Zero-Shot Classification

We used the HuggingFace `facebook/bart-large-mnli` model via the `transformers` pipeline.

- No additional training was performed.
- The model classified tickets based on predefined candidate labels.
- The Top 3 tags were extracted using confidence scores.

This demonstrates **Zero-Shot Learning**, where the model performs classification without being trained on the specific dataset.

---

### 2️ Prompt Engineering (Enhanced Labels)

To improve performance, label descriptions were enhanced with contextual explanations.

Example:

Instead of:

Login Issue

We used:

Login Issue: problems related to login, authentication, password errors, unable to access account

This provides richer semantic meaning to the model and improves classification accuracy.

---

### 3️ Multi-Class Prediction with Ranking

For each support ticket, the model returns:

- Top 1 Tag  
- Top 2 Tag  
- Top 3 Tag  
- Corresponding confidence scores  

This ranking-based prediction helps in better ticket routing and prioritization.

---

### 4️ Model Evaluation

Performance was evaluated using:

- **Accuracy Score**
- Comparison between Zero-Shot and Prompt-Engineered methods

Accuracy formula:

Accuracy = Correct Predictions / Total Predictions

---

## Key Results

| Method | Accuracy |
|--------|----------|
| Zero-Shot | 71.4% |
| Prompt-Engineered | 85.7% |

###  Accuracy Improvement:
**+14.3% improvement** using prompt engineering.

---

##  Key Observations

- Zero-shot classification works effectively without training.
- Adding descriptive context to labels significantly improves performance.
- Prompt engineering is a powerful alternative when fine-tuning is not available.
- Multi-label ranking provides better insight than single-label classification.

---

## Skills Demonstrated

- Prompt Engineering  
- Zero-Shot Learning  
- Multi-Class Text Classification  
- Multi-Label Ranking  
- Model Evaluation using Accuracy  
- HuggingFace Transformers  
- Python (Pandas, NumPy, Scikit-learn)  

---

##  Technologies Used

- Python  
- HuggingFace Transformers  
- Facebook BART (bart-large-mnli)  
- Pandas  
- NumPy  
- Scikit-learn  




##  Conclusion

This project demonstrates how Large Language Models can be effectively used for automatic support ticket classification without requiring full model training.

Prompt engineering significantly enhances classification performance, making it a practical and powerful NLP solution for real-world applications.
