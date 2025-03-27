# CineMood_Chatbot 🎬🎭

**CineMood_Chatbot** is a web-based chatbot recommending trending movies based on users' moods and preferences. It fetches the latest movie data from external APIs, generates embeddings for semantic search, and uses a vector database to provide contextually relevant movie suggestions.


## 🚀 Demo

🎭 **Try the app:** [CineMood Chatbot: Discover Films That Match Your Mood!](https://huggingface.co/spaces/thanhtungvudata/CineMood_Chatbot)  
📝 **Blog post:** [Building a Chatbot for Mood-Based Trending Movie Recommendation](https://medium.com/@tungvu_37498/building-a-chatbot-for-mood-based-trending-movie-recommendation-58db1c1fc8ed)

---

## ✨ Overview
This project combines **Retrieval-Augmented Generation (RAG)** with an NLP-based chatbot to provide movie recommendations tailored to users’ moods and interests. By continuously fetching trending movies, creating vector embeddings, and storing them in a ChromaDB instance, the chatbot can quickly retrieve relevant information and generate personalized suggestions.

Key points:

- **RAG Method**: Dynamically retrieves relevant movie details before generating responses, improving recommendation accuracy.
- **Semantic Search**: Uses embeddings to match user queries (e.g., "I want a thrilling movie") with movie overviews and metadata.
- **Streamlit Web Interface**: Offers an interactive chatbot experience, letting users ask for recommendations, browse trending titles, and discover new films.

---

## 🚀 Features

1. **Trending Movie Fetch**: Automatically pulls the latest trending movie data (e.g., from TMDB API).  
2. **Mood-Based Recommendations**: Uses user input about mood/preference to refine recommendations.  
3. **Embeddings & Vector Database**: Generates embeddings (e.g., using OpenAI) and stores them in [ChromaDB](https://docs.trychroma.com/) for efficient retrieval.  
4. **RAG Integration**: Combines retrieval of relevant data with a language model for more accurate and context-aware recommendations.  
5. **Continuous Updates**: GitHub Actions keep movie data and embeddings current without manual intervention.  
6. **User-Friendly UI**: Streamlit-based chatbot interface for conversational recommendations.  
7. **Deployment on Hugging Face**: Easily accessible on [Hugging Face Spaces](https://huggingface.co/spaces/), enabling quick demos and sharing.

---

## 📂 Project Structure
```
CineMood_v3
├── .github/workflows/
│   └── update_db.yml         # GitHub Actions workflow for auto-updates
├── chroma_db/                # Directory where ChromaDB stores vectors
├── LICENSE                   # MIT License
├── README.md                 # This file
├── app.py                    # Main Streamlit application
├── config.py                 # Configuration settings (e.g., API keys)
├── fetch_movies.py           # Script to fetch trending movies from APIs
├── generate_embeddings.py    # Script to generate vector embeddings
├── movie_embeddings.json     # Generated embeddings in JSON format
├── requirements.txt          # Project dependencies
├── store_in_chromadb.py      # Script to store embeddings into ChromaDB
└── trending_movies.json      # Latest trending movies data
```

---

## 🛠 Installation & Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/thanhtungvudata/CineMood_Chatbot.git
   cd CineMood_Chatbot
   ```

2. **Create and activate a virtual environment** (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install required dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up API keys or configuration** (if required):
   - Open `config.py` (or `.env` if you're using dotenv) and add any necessary API keys (e.g., TMDB API key, OpenAI API key, etc.).

---

## 🏃 Usage

1. **Fetch the latest trending movies**:
   ```bash
   python fetch_movies.py
   ```
   - This will retrieve fresh movie data (e.g., from TMDB) and store it in `trending_movies.json`.

2. **Generate embeddings**:
   ```bash
   python generate_embeddings.py
   ```
   - This script reads from `trending_movies.json`, generates vector embeddings, and writes them to `movie_embeddings.json`.

3. **Store embeddings in ChromaDB**:
   ```bash
   python store_in_chromadb.py
   ```
   - This script populates the ChromaDB instance (in `chroma_db/`) with your newly generated embeddings.

4. **Run the Streamlit app locally**:
   ```bash
   streamlit run app.py
   ```
   - This will launch the CineMood_v3 web interface in your browser.  
   - Explore trending movies, search via semantic similarity, and find recommendations.

5. **Deploy on Hugging Face Spaces**:
   - Push your repository to [Hugging Face Spaces](https://huggingface.co/spaces/).
   - Ensure the `requirements.txt` includes all dependencies.
   - Access the app from the provided Hugging Face URL.

---

## 🤖 Automation
- A GitHub Actions workflow (`.github/workflows/update_db.yml`) is configured to:
  - Periodically run `fetch_movies.py` and `generate_embeddings.py`.
  - Commit any changes to `movie_embeddings.json` or `trending_movies.json`.
  - This ensures your movie database is always up to date without manual intervention.

---

## 📜 License
This project is licensed under the **MIT License**.  
See [LICENSE](LICENSE) for full details.

---

## 💡 Future Enhancements
1. **User Feedback Integration**  
   Allow users to rate or save favorite movies, improving recommendations over time.
2. **Advanced RAG Enhancements**  
   Improve Retrieval-Augmented Generation by incorporating user preferences and contextual metadata.

---

## 🙌 Contributing
Pull requests are welcome! If you have ideas for improvements, open an issue to discuss what you’d like to change.

---

## ❤️ Acknowledgments
- [TMDB](https://www.themoviedb.org/) for movie data and trending API.
- [OpenAI](https://platform.openai.com/) or other NLP libraries for embedding generation.
- [ChromaDB](https://docs.trychroma.com/) for vector database services.
- [Streamlit](https://streamlit.io/) for the interactive UI framework.
- [Hugging Face Spaces](https://huggingface.co/spaces/) for hosting the app.

---

💡 **Built with ❤️ by [Thanh Tung Vu](https://thanhtungvudata.github.io/).**  
🌟 Star this repo if you find it useful!

---

🚀 **Enjoy mood-based movie recommendations! Let me know what you think! 🎬😊**

