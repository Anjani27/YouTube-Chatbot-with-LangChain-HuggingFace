# 🎥 YouTube Chatbot with LangChain & HuggingFace

This project is an end-to-end Retrieval-Augmented Generation (RAG) system that transforms YouTube video transcripts into a conversational Q&A interface using LLMs. It leverages Hugging Face models, LangChain tools, and FAISS vector search for scalable, context-aware AI responses.


## 🚀 Features

- 🔍 Retrieves video transcript directly using `youtube_transcript_api`
- 📄 Splits transcript text using `RecursiveCharacterTextSplitter`
- 🔎 Embeds & indexes chunks with `sentence-transformers` and `FAISS`
- 🤖 Answers user questions using HuggingFace-hosted `TinyLlama` model
- 🧠 Retrieval-augmented generation with context-injected prompts


## 🛠️ Tech Stack

- **LangChain**
- **HuggingFace (TinyLlama / Transformers)**
- **FAISS (Vector Store)**
- **Sentence Transformers**
- **YouTube Transcript API**
- **Python (Jupyter Notebook)**


## 📦 Installation

1. **Clone the repository**

```bash
git clone https://github.com/yourusername/yt-chatbot-langchain.git
cd yt-chatbot-langchain
````

2. **Install dependencies**

```bash
pip install -r requirements.txt
```

3. **Setup environment variables**

Create a `.env` file to include your Hugging Face API key:

```env
HUGGINGFACEHUB_API_TOKEN=your_hf_token_here
```



## ⚙️ How It Works

1. Extract transcript from a given YouTube video ID.
2. Split the transcript into overlapping chunks.
3. Generate embeddings using `all-MiniLM-L6-v2`.
4. Store and query chunks using FAISS.
5. Inject top `k` similar chunks into a prompt template.
6. Use `TinyLlama` (or any HF model) to generate grounded responses.



## 📌 Example Query

```python
question = "Is the topic of aliens discussed in this video?"
```

The model answers based on transcript content, or defaults to:
*"I don’t know"* if the context is insufficient — preventing hallucination.



## ✅ Status

* [x] Transcript ingestion & processing
* [x] Embedding + FAISS vector storage
* [x] Prompt construction
* [x] Response generation with HuggingFace
* [ ] UI frontend (future enhancement)



## 📎 Future Improvements

* Add multi-video retrieval
* Integrate UI with Gradio or Streamlit
* Support multilingual transcripts
* Switch to LangGraph for agentic flows



## 📄 License

This project is licensed under the MIT License.



## 🤝 Contributing

Pull requests are welcome! For major changes, open an issue first to discuss what you’d like to improve.

