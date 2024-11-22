# Chatbot
# **Grant Assistance Chatbot**

This repository contains a GPT-2-based chatbot designed to assist users with grant-related inquiries. The chatbot was fine-tuned on a dataset of grant-related FAQs and responses to classify user intents and generate accurate responses.

---

## **Dataset**
The chatbot was trained and evaluated on a custom dataset of grant-related queries categorized by intent. 

- **Dataset Link**: [Grant FAQ Dataset](https://drive.google.com/file/d/1hymb-eVi6UveXL9YBWJswP8Y0htmQWlc/view?usp=sharing)

---

## **Performance Metrics**
The chatbot's performance was evaluated across three epochs on a validation set. The results are summarized below:

| **Epoch** | **Training Loss** | **Validation Loss** | **Accuracy** | **F1-Score** | **Precision** | **Recall** |
|-----------|--------------------|----------------------|--------------|--------------|---------------|------------|
| 1         | No log             | 1.235141            | 0.500        | 0.500        | 0.500         | 0.500      |
| 2         | No log             | 1.359530            | 0.500        | 0.333        | 0.250         | 0.500      |
| 3         | No log             | 1.489877            | 0.333        | 0.333        | 0.250         | 0.500      |

## Explanation of Training and Validation Metrics

## 1. Training Loss and Validation Loss

- **Training Loss**:  
  This measures the error on the training dataset. It’s missing here (`No log`), but typically, it helps indicate how well the model is learning during training.

- **Validation Loss**:  
  This measures the error on the validation dataset (unseen data). It evaluates how well the model generalizes.

- **Interpretation**:  
  A rising validation loss across epochs (1.235 → 1.360 → 1.490) suggests **overfitting**. The model might be memorizing the training data rather than learning generalized patterns.
---

## 2. Accuracy

- **Accuracy**:  
  Accuracy is the proportion of correctly classified queries over the total queries in the validation set.

- **Epoch 1**:  
  **50% accuracy** means the model correctly classified half of the inputs.

- **Epoch 2-3**:  
  Accuracy remains at **50%**, but this metric alone isn’t very useful for imbalanced datasets.

---

## 3. F1-Score

- **F1-Score**:  
  F1-score is the harmonic mean of precision and recall. It’s especially useful for evaluating models on imbalanced datasets.

- **Epoch 1**:  
  F1-score is **0.500**, indicating balanced performance.

- **Epoch 2**:  
  F1-score drops to **0.333**, suggesting the model’s classification ability deteriorates over time.

- **Epoch 3**:  
  F1-score stays at **0.333**, implying no further improvement despite additional training.

---

## 4. Precision

- **Precision**:  
  Precision is the proportion of true positives out of all predicted positives.

- **Epoch 1**:  
  **0.500** suggests half of the predictions classified as a particular class are correct.

- **Epoch 2-3**:  
  **0.250** means only 25% of positive predictions are correct, indicating the model is struggling to predict specific classes accurately.

---

## 5. Recall

- **Recall**:  
  Recall is the proportion of true positives out of all actual positives.

- **Epochs 1-3**:  
  **0.500** means the model identifies half of all the true positive instances in each epoch.

---
## **Examples of Conversations**
Here are some example interactions with the chatbot:

### Example 1: General Eligibility Inquiry
**User**: Who is eligible for the grant?  
**Chatbot**: Students on full scholarships are ineligible for this grant. Priority will be given to new candidates, but previous recipients are welcome to apply.

### Example 2: Application Process Inquiry
**User**: How do I apply for the grant?  
**Chatbot**: To apply, submit all required documents and information through the Financial Aid Office. Ensure your submissions are accurate and verifiable, as unverified information may weaken your application.

### Example 3: Grant Prioritization
**User**: Who gets priority for the grant?  
**Chatbot**: Priority is given to new applicants with the most demonstrated financial need. However, previous recipients may still apply.

### Example 4: Out-of-Scope Inquiry
**User**: Can I get funding for another term?  
**Chatbot**: I’m not sure about that. Could you clarify your question or ask about the current grant term?

---

## **Chatbot Demo**
- **Live Chatbot**: [Access the Chatbot](https://colab.research.google.com/drive/1ULkLCNr1vkz5i289qdgynWR9dh2xUyld?usp=sharing)  
- **Demo Video**: [Watch Demo](https://youtu.be/7yTNFicdW7o)

---

## **How It Works**
1. **Input Query**: Users input their grant-related questions.
2. **Intent Classification**: The model identifies the user's intent based on the query.
3. **Response Generation**: The chatbot provides an accurate, pre-defined response based on the detected intent.

---

## **Setup Instructions**
To run the chatbot locally:

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/chatbot.git
   cd chatbot
2. Install dependencies:
   ```bash
   pip install transformers datasets torch sklearn
   cd chatbot
3. Run the notebook

---

## **Future Improvements**
1. **Expand the dataset with more diverse and realistic queries.**
2. **Optimize the training process for better performance metrics.**
3. **Enable context-based multi-turn conversations.**
4. **Deploy the chatbot on popular platforms like Telegram or as a web-based interface.**
