# 📄 Resume Matcher - AI-Powered Resume Analysis Tool

Resume Matcher 🔍 | AI-Powered Resume Analyzer  An NLP-powered Streamlit app that compares your resume (PDF) with a job description to compute a match score and highlight key keywords. Built with Python, NLTK, and Plotly.  ✅ Resume Upload ✅ Match Score (Cosine Similarity) ✅ Keyword Visualization ✅ Tailored Suggestions

This is a Natural Language Processing (NLP) application built with **Streamlit**, designed to help job seekers match their resumes against job descriptions. It calculates a **match percentage** and provides **keyword insights** to assist users in tailoring their resumes for better alignment with specific roles.

---

## 🚀 Features

- Upload your resume in **PDF format**
- Paste a **job description**
- Get a **match score** using cosine similarity
- See **top keywords** from both documents
- Visualize keyword relevance using **Plotly**
- Receive **suggestions** to improve your resume

---

## 🧠 How It Works

### 1. Text Extraction
- **PDF Parsing:** Your resume PDF is read and converted to plain text using `PyPDF2`.
- **Cleaning:** Removes unnecessary characters, extra spaces, and lowercases the text.

### 2. Text Preprocessing (NLP)
- **Tokenization:** Splits text into individual words using NLTK's `word_tokenize`.
- **Stopword Removal:** Removes common words like "and", "the", etc., using `nltk.corpus.stopwords`.
- **Lemmatization:** Reduces words to their root form using `WordNetLemmatizer`.

```python
tokens = word_tokenize(text.lower())
tokens = [lemmatizer.lemmatize(token) for token in tokens if token.isalnum()]
tokens = [token for token in tokens if token not in stop_words]
```

### 3. Term Frequency and Cosine Similarity
- Calculates how often each word appears in resume and job description.
- Uses **cosine similarity** to measure how closely the two documents align in terms of keyword usage.

```python
similarity = dot_product / (resume_magnitude * job_magnitude)
```

This similarity is converted to a **match percentage**.

---

## 📊 Keyword Visualization

The top keywords from the resume and job description are displayed side-by-side using a **horizontal bar chart** with Plotly:

- Each keyword is scored by how frequently it appears.
- Scores are normalized and compared visually.
- Most relevant overlapping keywords are highlighted.

---

## 💻 User Interface

Built using **Streamlit**, the UI includes:

- **Job Description** input area
- **Resume Uploader** (PDF only)
- **Match Score** card
- **Keyword Graph** (interactive)
- **Analysis Summary** and **Improvement Suggestions**
- **Sidebar** with team information and usage instructions

---

## 🧰 Tech Stack

| Component     | Technology       |
|---------------|------------------|
| Web UI        | Streamlit        |
| NLP           | NLTK             |
| PDF Handling  | PyPDF2           |
| Visualization | Plotly           |
| Language      | Python           |

---

## 📝 Folder Structure

```
.
├── resume_matcher.py       # Main Streamlit app code
├── style.css               # Custom CSS styles
├── README.md               # You're here!
```

---

## 🔧 Setup Instructions

1. Clone the repository:

```bash
git clone https://github.com/rythmokay/resume-checker.git
cd resume-checker
```

2. Create a virtual environment and install dependencies:

```bash
pip install -r requirements.txt
```

3. Run the application:

```bash
streamlit run app.py
```

4. Access it in your browser at `http://localhost:8501`

---

## 📦 Dependencies

Make sure these packages are installed:

```bash
streamlit
PyPDF2
nltk
plotly
```

For NLTK resources, the script will automatically download:

- punkt
- stopwords
- wordnet

---

## 👨‍💻 Authors

- **Rythm** – Team Leader  
- **Rishabh** – Team Member  
- **Ayush** – Team Member  
- **Ekansh** – Team Member

---

## 📌 Tips for Better Results

- Use **text-based PDFs** (not scanned images)
- Keep the **job description detailed**
- Tailor your resume to **include relevant keywords**
- A match score of **70%+** indicates a strong alignment

---

## 📃 License

This project is for educational purposes. You are free to modify and use it for learning and development.

---

## 💡 Future Enhancements

- Resume feedback with grammar checks
- Integration with job boards
- Resume scoring by sections (skills, experience, education)

---

