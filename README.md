# 🎬 Movie Recommender System

A content-based movie recommendation system built using machine learning techniques and the TMDB (The Movie Database) dataset. This system analyzes movie features like genres, keywords, cast, crew, and plot overview to recommend similar movies using cosine similarity.

## 🚀 Features

- **Content-Based Filtering**: Recommends movies based on content similarity rather than user ratings
- **Machine Learning**: Uses scikit-learn's CountVectorizer and cosine similarity for recommendations
- **Interactive Web Interface**: Built with Streamlit for easy user interaction
- **Movie Posters**: Fetches and displays movie posters using TMDB API
- **Dynamic Layout**: Adapts to the number of available recommendations
- **Data Processing**: Comprehensive data preprocessing pipeline in Jupyter notebook
- **Pickle Model Storage**: Pre-trained model saved for fast loading

## 🛠️ Technology Stack

- **Python 3.13+**
- **Streamlit** - Web application framework
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Scikit-learn** - Machine learning library
- **Requests** - HTTP library for API calls
- **Pickle** - Model serialization
- **Jupyter Notebook** - Data analysis and model development

## 📊 Dataset

The system uses the TMDB 5000 Movie Dataset which includes:
- **tmdb_5000_movies.csv**: Movie details (genres, keywords, overview, etc.)
- **tmdb_5000_credits.csv**: Cast and crew information

### Dataset Features Used:
- Movie title and overview
- Genres and keywords
- Cast (top 3 actors)
- Director information
- Movie ID for poster fetching

## 🔧 Installation & Setup

### Prerequisites
- Python 3.7 or higher
- Internet connection (for fetching movie posters)

### Step 1: Clone the Repository
```bash
git clone <repository-url>
cd movie-recommender-system-tmdb-dataset-main
```

### Step 2: Create Virtual Environment
```bash
python -m venv .venv
```

### Step 3: Activate Virtual Environment
**Windows:**
```bash
.venv\Scripts\activate
```
**macOS/Linux:**
```bash
source .venv/bin/activate
```

### Step 4: Install Required Packages
```bash
pip install streamlit pandas numpy scikit-learn requests
```

### Step 5: Prepare the Data
1. Run the Jupyter notebook `notebook86c26b4f17.ipynb` to process the data and create model files
2. This will generate the required pickle files in the `model/` directory:
   - `movie_list.pkl`
   - `similarity.pkl`

## 🚦 How to Run

### Method 1: Using Command Line
```bash
streamlit run app.py
```

### Method 2: Using Python Module
```bash
python -m streamlit run app.py
```

The application will start and display:
```
Local URL: http://localhost:8501
Network URL: http://192.168.x.x:8501
```

Open the local URL in your web browser to access the application.

## 💻 Usage

1. **Launch the Application**: Open http://localhost:8501 in your browser
2. **Select a Movie**: Choose a movie from the dropdown menu
3. **Get Recommendations**: Click the "Show Recommendation" button
4. **View Results**: Browse through recommended movies with their posters

## 🔍 How It Works

### Data Processing Pipeline:
1. **Data Loading**: Load movies and credits datasets
2. **Data Merging**: Combine datasets on movie titles
3. **Feature Extraction**: Extract genres, keywords, cast, and crew
4. **Text Processing**: Clean and preprocess text data
5. **Vectorization**: Convert text to numerical vectors using CountVectorizer
6. **Similarity Calculation**: Compute cosine similarity matrix
7. **Model Saving**: Save processed data and similarity matrix

### Recommendation Algorithm:
1. User selects a movie
2. System finds the movie's index in the dataset
3. Retrieves similarity scores for all movies
4. Sorts movies by similarity (excluding the selected movie)
5. Returns top N most similar movies
6. Fetches movie posters from TMDB API
7. Displays recommendations with posters

## 📁 Project Structure

```
movie-recommender-system-tmdb-dataset-main/
│
├── app.py                          # Main Streamlit application
├── notebook86c26b4f17.ipynb        # Data processing and model creation
├── README.md                       # Project documentation
├── tmdb_5000_movies.csv            # Movie dataset
├── tmdb_5000_credits.csv           # Credits dataset
│
├── model/                          # Model files directory
│   ├── movie_list.pkl             # Processed movie data
│   └── similarity.pkl             # Cosine similarity matrix
│
└── .venv/                         # Virtual environment
```

## 🎯 Key Functions

### `fetch_poster(movie_id)`
- Fetches movie poster from TMDB API
- Returns full poster URL

### `recommend(movie)`
- Main recommendation function
- Returns list of recommended movie names and poster URLs
- Handles edge cases for small datasets

## 🔑 API Configuration

The system uses TMDB API to fetch movie posters. The API key is embedded in the code:
- API Key: `8265bd1679663a7ea12ac168da84d2e8`
- Base URL: `https://api.themoviedb.org/3/movie/`
- Image Base URL: `https://image.tmdb.org/t/p/w500/`

## 🐛 Troubleshooting

### Common Issues:

**1. Module Not Found Error**
```bash
pip install streamlit pandas numpy scikit-learn requests
```

**2. Missing Model Files**
- Run the Jupyter notebook to generate pickle files
- Ensure `model/` directory exists with required files

**3. API Connection Issues**
- Check internet connection
- Verify TMDB API accessibility

**4. Port Already in Use**
```bash
streamlit run app.py --server.port 8502
```

## 🔮 Future Enhancements

- [ ] Add user rating-based collaborative filtering
- [ ] Implement hybrid recommendation system
- [ ] Add more movie metadata (year, runtime, ratings)
- [ ] Include movie trailers and reviews
- [ ] Add user authentication and preference saving
- [ ] Implement advanced NLP techniques (TF-IDF, Word2Vec)
- [ ] Add movie search functionality
- [ ] Include more diverse datasets

## 📈 Performance

- **Dataset Size**: Currently optimized for 5,000+ movies
- **Response Time**: < 1 second for recommendations
- **Memory Usage**: ~50MB for similarity matrix
- **Scalability**: Can handle larger datasets with minimal changes

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- **TMDB (The Movie Database)** for providing the movie dataset and API
- **Streamlit** team for the amazing web framework
- **Scikit-learn** contributors for machine learning tools
- **Pandas** team for data manipulation capabilities

---

**Made with ❤️ by [Your Name]**

For questions or support, please open an issue on GitHub.
