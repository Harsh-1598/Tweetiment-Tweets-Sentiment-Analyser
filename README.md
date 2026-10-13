# Twitter Sentiment Analysis Using Hugging Face Pre-trained Transformer & Safety Guardrails

A beginner-friendly, academic mini-project designed for college demonstrations, seminars, and viva examinations.

---

## 📌 Project Overview
This project classifies tweets into three primary sentiment classes:
- **Positive (😊)**
- **Negative (😡)**
- **Neutral (😐)**

Rather than training a weak LSTM model from scratch on a small dataset, this updated project uses an industry-standard **Pre-trained Hugging Face Transformer**: **CardiffNLP Twitter-RoBERTa** (`cardiffnlp/twitter-roberta-base-sentiment-latest`), which was trained on **124 million real-world tweets**.

### 🌟 Key Enhancements:
1. **Pre-trained RoBERTa Architecture:** State-of-the-art bidirectional self-attention captures contextual nuance, hashtags, slang, emojis, and negations with high accuracy.
2. **Custom Python Wrapper Model (`TweetSentimentClassifier`):** Encapsulates text normalization, tokenization, device management, softmax probability extraction, and explainable AI insights.
3. **Pre-Inference Content Guardrails (`moderation.py`):**
   - **Sovereign Territorial Integrity:** Prohibits distorted maps, controversial stances, or foreign claims against Indian territory (such as Chinese claims over Arunachal Pradesh, Ladakh, Aksai Chin, or Kashmir) and issues a strict reminder message while upholding Indian sovereignty.
   - **NSFW / Decency Filter:** Zero tolerance for pornography, explicit adult language, or sexual content.
4. **Clean, Aesthetic Streamlit UI:** Redesigned with a minimalist slate color palette, clear cards, live probability meters, one-click demo buttons, and an integrated Teacher Viva Guide.

---

## 🗂️ Project Directory Structure

```text
TweetSentimentAnalyser/
├── app.py                       # Interactive Streamlit Web Application (Aesthetic UI)
├── sentiment_analyzer.py        # Hugging Face Twitter-RoBERTa Wrapper Model
├── moderation.py                # Pre-inference Content Safety & Territorial Guardrail
├── requirements.txt             # Required Python libraries (Transformers, Torch, Streamlit)
├── README.md                    # Setup, execution, and project documentation
├── REPORT.md                    # Academic Project Report & Viva Notes
├── DEMO_SCRIPT.md               # 2-Minute Speech & Step-by-Step Live Demo Plan
├── VIVA_QUESTIONS.md            # College Viva Questions & Answers
├── data/                        # Datasets (retained for reference)
└── models/                      # Legacy model configurations
```

---

## 🛠️ Technology Stack
- **Language:** Python 3.10 / 3.11
- **Deep Learning & NLP:** Hugging Face `transformers`, PyTorch (`torch`)
- **Pre-trained Model:** `cardiffnlp/twitter-roberta-base-sentiment-latest` (RoBERTa Transformer)
- **Web Interface:** Streamlit (Custom minimalist styling)
- **Data & Evaluation:** Pandas, NumPy, Scikit-Learn

---

## 🚀 Quick Start Guide (Windows / VS Code)

### Step 1: Open the Project
Open the `TweetSentimentAnalyser` folder in **Visual Studio Code**.

### Step 2: Activate the Virtual Environment
Open a terminal (`Ctrl + ` `) and run:
```powershell
.\venv\Scripts\activate
```

### Step 3: Run the Streamlit Application
```powershell
streamlit run app.py
```
The browser will automatically open at `http://localhost:8501`.

---

## 🎯 How It Works (For Teacher & Viva Presentation)

```text
[User Tweet Input]
        │
        ▼
[Step 1: Content Guardrail (moderation.py)]
        ├── Disputed Map / Anti-India Claim ──► 🛑 BLOCKED (Strict Sovereign Reminder)
        ├── Explicit Sexual / NSFW Content  ──► 🛑 BLOCKED (Strict Decency Reminder)
        └── Clean & Valid Tweet
                │
                ▼
[Step 2: RoBERTa Transformer (sentiment_analyzer.py)]
        ├── Normalization (@user, http links)
        ├── Byte-Pair Encoding (BPE) Tokenization
        └── Multi-Head Bidirectional Self-Attention
                │
                ▼
[Step 3: Softmax Probabilities & Verdict]
        ├── Winning Sentiment: Positive / Neutral / Negative
        ├── Confidence Score (%)
        └── Educational Viva Explanation
```

---

## ⚖️ Why Pre-trained RoBERTa vs Traditional LSTM? (Top Viva Question)

| Feature | Traditional LSTM | Pre-trained RoBERTa (Our Project) |
| :--- | :--- | :--- |
| **Architecture** | Sequential Recurrent Neural Network | Multi-Head Self-Attention Transformer |
| **Context** | Left-to-right (can forget early words) | Full Bidirectional Context simultaneously |
| **Training Data** | Small custom dataset (~1,000 tweets) | ~124 Million real-world Twitter posts |
| **Negation & Slang** | Struggles with sarcasm & negations | Exceptional understanding of slang & emojis |
| **Guardrails** | Usually None | Integrated pre-inference safety layer |

---

## 💡 Quick Demo Tips for Examiners
- Use the **One-Click Classroom Demo Examples** to showcase Positive, Negative, and Neutral predictions.
- Click **"🚫 Blocked: Disputed Map Claim"** to demonstrate how your wrapper upholds Indian territorial sovereignty and rejects controversial Chinese map claims.
- Click **"🚫 Blocked: Adult / NSFW Content"** to demonstrate zero-tolerance decency moderation.
- Switch to the **"👨‍🏫 Teacher Viva & Architecture Guide"** tab for instant viva answers during the presentation.
# Tweetiment-Tweets-Sentiment-Analyser
