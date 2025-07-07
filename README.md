
#  Brief Me The Case: AI-Powered Legal & News Summarizer

> A powerful multi-model AI summarization engine for transforming lengthy legal and journalistic content into concise, human-readable summaries — featuring abstractive, extractive, and rewriter modules.

 **Deployed with FastAPI**  
 **ROUGE, BERTScore, Perplexity Evaluated**  
 **Powered by BART, T5, and DistilBERT**

---


##  Objective

**Brief Me The Case** is a transformer-based summarization platform designed for domains where clarity and accuracy are critical — like **legal documents** and **news articles**.

It supports:
-  Abstractive summarization (BART)
-  Extractive summarization (DistilBERT + LoRA)
-  Fluency-enhancing rewriters (T5 and BART)
-  Human-in-the-loop interface for summary refinement

---

##  Datasets Used

| Dataset | Domain | Source |
|---------|--------|--------|
| BillSum | Legal Bills | U.S. Congressional Bills |
| MultiNews | Journalism | Multiple News Outlets |
| CNN/DailyMail | Extractive | HuggingFace Datasets |

---

##  Model Architecture

###  Abstractive Summarizer (BART)
- Encoder-Decoder architecture using `facebook/bart-large-cnn`
- Handles up to 1024 token input
- Cross-Entropy loss + AdamW + LR warmup

###  Extractive Summarizer (DistilBERT + LoRA)
- Sentence-level regression model
- ROUGE-L scoring for supervision
- Fine-tuned with 1% data subset
- Low-Rank Adaptation for fast training

###  Rewriter Models
- **T5-base**: Improves fluency of decoder-generated text
- **BART-base**: Enhances structure, tone, and coherence
- Evaluation: ROUGE-1/2/L, BERTScore, GPT-2 Perplexity, Readability

---

##  Evaluation Metrics

| Metric       | Score    | Interpretation                       |
|--------------|----------|--------------------------------------|
| ROUGE-1      | 0.4541   | Word overlap (abstractive)           |
| ROUGE-2      | 0.1920   | Phrase overlap                       |
| BERTScore F1 | 0.8705   | Semantic similarity                  |
| GPT-2 PPL    | 19.19    | Fluency of generated summaries       |
| Readability  | 37.17    | Formal/legal tone readability        |

---

##  App Features

- Upload a long legal/news document
- Click **"Generate Summary"** for AI abstraction
- Click **"Humanize Summary"** for fluent version
- Try **extractive summarization** mode for speed

---


