# TraverGo 

> **AI-powered hotel discovery and travel assistant**  
> *Aamod Varma · Saksham Bansal · Ze Yu Jiang*

TraverGo is a conversational travel assistant that solves the core pain points of hotel booking — personalization gaps, information overload, and inefficient search — using neural search, sentiment analysis, and real-time AI.

---

## The Problem

42% of US travelers say finding the right accommodation is one of the most time-consuming parts of planning a trip. Existing platforms fall short in three key ways:

- **Personalization Gap** - Booking platforms don't adapt to a traveler's unique preferences, making it hard to find accommodations that truly fit.
- **Time-Consuming Research** - Sifting through hundreds of reviews leads to information overload and missed details.
- **Inefficient Interaction** - The absence of conversational interfaces forces travelers to navigate clunky UIs and discourages them from getting the help they need.

---

## Features

### Neural Search
Matches natural language user queries against hotel descriptions and reviews using semantic vector search via Qdrant, going far beyond simple keyword matching.

### Sentiment Analysis
Analyzes hotel reviews and generates comprehensive sentiment-based ratings so travelers can quickly gauge the real guest experience without reading everything themselves.

### QnA Chatbot
An integrated conversational chatbot lets users ask follow-up questions about specific hotels and get detailed clarifications powered by OpenAI and augmented with the Ares API for real-time information.

### Traversaal AI API Integration
Fetches live data about nearby locations; attractions, restaurants, and transportation so travelers get full context around each hotel, not just the property itself.

### Decoder Model
Explains *why* a particular hotel was recommended for a given query, providing transparent, traveler-specific reasoning instead of a black-box result.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend / UI | Streamlit |
| Vector Database | Qdrant |
| Embeddings | `sentence-transformers` |
| LLM & Chat | OpenAI API (`langchain`) |
| Real-Time Search | Traversaal Ares API |
| NLP / Models | Hugging Face `transformers` |

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/travergo.git
cd travergo
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Set Environment Variables

Create a `.env` file in the root directory:

```env
OPENAI_API_KEY=your_openai_api_key
TRAVERSAAL_API_KEY=your_traversaal_ares_api_key
QDRANT_URL=your_qdrant_instance_url
QDRANT_API_KEY=your_qdrant_api_key
```

### 4. Run the App

```bash
streamlit run app.py
```

Open your browser to `http://localhost:8501`.

---

## Requirements

```
chatbot==1.5.2b0
langchain==0.1.6
openai==1.12.0
qdrant_client==1.7.3
Requests==2.31.0
sentence_transformers==2.3.1
streamlit==1.31.0
transformers==4.35.2
```

---

## Challenges We Faced

- **Learning the Framework** — Getting up to speed with LangChain's abstractions and chaining patterns from scratch.
- **Qdrant Pipeline** — Building a robust ingestion and vector search pipeline for hotel data with proper embedding alignment.
- **Streamlit Session State** — Managing multi-step conversational state across Streamlit reruns without losing context.
- **Ares API + OpenAI Integration** — Wiring the Traversaal Ares real-time search tool into the OpenAI chatbot as a callable function without breaking the conversation flow.
- **Chatbot Model** — Tuning the chatbot to stay grounded in hotel-specific context while still being able to answer general travel questions.

---

## License

This project was built as a hackathon submission. Feel free to build on it for educational and non-commercial purposes.
