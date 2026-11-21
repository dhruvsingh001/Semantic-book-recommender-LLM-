# 📚 Semantic Book Recommender with LLMs

An end-to-end, natural-language book recommendation engine powered by dense vector embeddings, zero-shot text classification, emotion analysis, and an interactive Gradio web interface. 

Instead of relying on rigid keyword matching or basic collaborative filtering, this system understands the **semantic meaning**, **narrative genre**, and **emotional tone** behind a reader's query (e.g., *"A gripping sci-fi story about survival and hope"* or *"A lighthearted mystery set in a small town"*).

---

## ✨ Key Features

- **Natural Language Semantic Search:** Finds books that conceptually match a user's free-text prompt using dense vector embeddings stored in **ChromaDB**.
- **Automated Category Enrichment:** Uses LLM/transformer-based text classification to standardize noisy raw genres into clean, high-level categories (e.g., Fiction, Nonfiction, Children's Fiction, Children's Nonfiction).
- **Emotion & Tone Filtering:** Scores book descriptions across key emotional dimensions (such as *joy, sadness, anger, fear, surprise, disgust, and neutral*), allowing users to sort or filter recommendations by the "vibe" they want to read.
- **Interactive Gradio Dashboard:** A clean, responsive web UI featuring natural-language search, category dropdown filtering, emotional tone sorting, book cover previews (with graceful fallback handling), and truncated/expandable synopses.

---

## 🏗️ System Architecture & Pipeline

The project is organized into a modular data-to-deployment pipeline:

```text
Raw Book Dataset
       │
       ▼
[1. Data Exploration & Cleaning]  ──► books_cleaned.csv & tagged_description.txt
       │
       ▼
[2. Vector Embedding & Indexing]  ──► chroma_db/ (Persistent Vector Store)
       │
       ▼
[3. Genre Text Classification]    ──► books_with_categories.csv
       │
       ▼
[4. Emotion / Sentiment Scoring]  ──► books_with_emotions.csv
       │
       ▼
[5. Interactive Web Application]  ──► gradio-dashboard.py (Live UI)
