# 📰Fake News Detection Using Neural Networks

## Project Overview

This project uses Natural Language Processing (NLP) and Deep Learning to classify news headlines as either:

- Fake News (0)
- Real News (1)

A neural network was built using TensorFlow and the Keras Sequential API to learn patterns within article headlines and predict whether a headline is likely to be fake or real. 

The model uses text preprocessing techniques such as tokenization and padding before training an embedding-based neural network.

---

## 🎯Objectives 

- Load and preprocess news headline data
- Convert text into numerical sequences
- Prepare padded inputs for neural network training
- Build an embedding-based neural network
- Train the classifier using TensorFlow/Keras
- Evaluate the performance using accuracy and precision
- Analyze the importance of precision in fake news detection

---

## 🛠️Technologies Used

- Python
- Pandas
- Numpy
- TensorFlow
- Keras
- Scikit-learn

---

## 📁Repository Structure

```text
fake-news-classifier-neural-network/
│
├── article_headlines.csv
├── fake_news_classifier.ipynb
├── requirements.txt
├── README.md
│
└── screenshots/
├── dataset-preview.png
├── model-summary.png
└── results.png
```

---

## 📊Dataset

The dataset contains article headlines and labels.

### Labels

```text
0 = Fake News
1 = Real News
```

### Example

| Headline | Label |
|----------|----------|
| Government announces new tax reform | 1 |
| Aliens discovered living on Mars |0 |
| Scientists develop new cancer treatment | 1 |

---

## ⚙️Text Preprocessing

The following preprocessing steps were performed:

### Tokenization

Text headlines were converted into sequences of integers using Keras Tokenizer.

### Out-of-Vocabulary Handling 

Unknown words were mapped to a special token:

```text
<00v>
```

### Padding 

Sequences were padded to a fixed length of 10 words using:

```python
pad_sequences()
```

This ensures all inputs have the same dimensions for neural network training.

### Label Preparation

Labels were converted into NumPy arrays for binary classification.

---

## 🧠Neural Network Architecture

The model uses an embedding-based neural network.

### Architecture

```text
Input Headlines
↓
Embedding Layer
↓
GlobalAveragePooling1D
↓
Dense Layer (16 Neurons, ReLU)
↓
Output Layer (1 Neuron, Sigmoid)
```

### Layer Explanation

#### Embedding Layer

Learns vector representations of words.

#### GlobalAveragePooling1D

Reduces sequence information into a compact representation. 

#### Dense Layer

Learns patterns useful for distinguishing fake and real news headlines.

#### Sigmoid Output Layer

Produces a probability between:

```text
0 = Fake News
1 = Real News
```

---

## 📸Model Architecture

<img width="1058" height="498" alt="model-summary" src="https://github.com/user-attachments/assets/9488bdd9-dfa3-4356-9847-8d9b4e62f154" />


---

## 📈Results

<img width="218" height="70" alt="results" src="https://github.com/user-attachments/assets/f6b41da2-7191-4dec-8c02-04d96f0a21af" />

### Model Performance

| Metric | Score |
|----------|----------|
| Accuracy | 0.95% |
| Precision | 0.89% |

### Interpretation 

The model was evaluated using accuracy and precision on unseen test data.

- Accuracy measures the overall percentage of correct predictions.
- Precision measures how many headlines predicted as real (or fake, depending on the positive class) were correctly classified.

Higher precision indicates that the model's positive predictions are more reliable.

---

## 💎Why Precision Matters

Precision is calculated as: 

```text
Precision = True Positives / (True Positives + False Positives)
```

In fake news detection, low precision means the model is incorrectly classifying many headlines.

Potential consequences include: 

- Misinformation remaining undetected
- Legitimate news being flagged incorrectly
- Reduced trust in automated fact-checking systems

A higher precision score improves the credibility and usefulness of the classification system. 

## 🌍Real-World Applications

Applications of fake news detection include:

- Social media moderation
- News verification systems
- Fact-checking platforms
- Misinformation detection
- Content recommendation systems

---

## 🚀Potential Improvements

### 1. Increase Vocabulary Size

Using more words may improve language understanding:

```python
Tokenizer(num_words=5000)
```

### 2. Use More Advanced Deep Learning Models

Models such as:

- LSTM
- GRU
- RoBERTa
- Transformer Networks

can better capture context and word relationships.

---

## ⚠️Model Limitation

This model only considers the headline text and does not analyze:

- Full article content
- Source credibility
- Writing style
- Contextual information

As a result, predictions may be limited when headlines contain ambiguous or complex language.

---

## 🔮Future Enhancements

- Implement LSTM networks
- Use Bidirectional LSTM models
- Apply Transformer architectures
- Fine-tune RoBERTa for fake news detection
- Deploy the model as a web application
- Build an interactive dashboard

---

## 📚Requirements

Install the required dependencies:

```bash
pip install -r requirements.txt
```

### requirements.txt

```txt
pandas
numpy
scikit-learn
tensorflow
```

---

## ▶️Running the Project

Run the application:

```bash
python fake_news_classifier.ipynb
```

The program will:

1. Load the dataset
2. Preprocess text headlines
3. Build the neural network
4. Train the model
5. Generate predictions
6. Display accuracy and precision scores
