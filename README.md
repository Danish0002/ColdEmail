# Cold Email Generator

A Streamlit web application that automatically scrapes job postings from a careers page URL and generates personalized cold outreach emails using Llama models on Groq, customized with relevant links from your portfolio.

## Features
- **Scrape Careers Pages**: Uses LangChain WebBaseLoader to extract text from a careers URL.
- **Job Extraction**: Formats jobs found on the web page into JSON schema using `meta-llama/llama-4-scout-17b-16e-instruct` via Groq.
- **Semantic Portfolio Matching**: Stores portfolio project tech stacks in a ChromaDB vector database and queries them using semantic search for skills needed by the job description.
- **Cold Outreach Email Generation**: Automatically drafts a compelling, personalized cold email showcasing matching portfolio projects.

---

## Local Setup

### Prerequisites
- Python 3.11 (highly recommended; newer versions might cause DLL load failures with onnxruntime)
- A Groq API key

### 1. Clone the repository and navigate inside
```bash
git clone <your-repo-url>
cd ColdEmail
```

### 2. Create and activate virtual environment
```bash
python -m venv .venv
# On Windows (cmd):
.venv\Scripts\activate.bat
# On Windows (PowerShell):
.venv\Scripts\Activate.ps1
# On macOS/Linux:
source .venv/bin/activate
```

### 3. Install required packages
```bash
pip install -r requirements.txt
```

### 4. Set up environment variables
Create a `.env` file in the root of the project:
```env
GROQ_API_KEY=your_groq_api_key_here
```

### 5. Run the Streamlit app
```bash
streamlit run main.py
```

---

## Deployment on Streamlit Community Cloud (Free)

1. Push this folder (`ColdEmail_GitHub`) to a public repository on GitHub.
2. Log into [Streamlit Community Cloud](https://share.streamlit.io/) using your GitHub account.
3. Click **New app**, select your repository, branch, and set `main.py` as the entry file.
4. Click **Advanced settings...** and paste your secrets in the **Secrets** section:
   ```toml
   GROQ_API_KEY = "your_actual_groq_api_key_here"
   ```
5. Click **Deploy**.
