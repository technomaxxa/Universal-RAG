# 🗂️ Universal Multi-File RAG Assistant

[![Python](https://img.shields.io/badge/Python-3.11.7-3776AB?logo=python\&logoColor=white)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-App-FF4B4B?logo=streamlit\&logoColor=white)](https://streamlit.io/)
[![LangChain](https://img.shields.io/badge/LangChain-Powered-1C3C3C?logo=langchain\&logoColor=white)](https://www.langchain.com/)
[![Gemini](https://img.shields.io/badge/Google-Gemini-4285F4?logo=google\&logoColor=white)](https://ai.google.dev/)
[![ChromaDB](https://img.shields.io/badge/Vector_DB-ChromaDB-FF6B35)](https://www.trychroma.com/)

> **Chat with multiple documents using Retrieval-Augmented Generation (RAG), local embeddings, ChromaDB, and Google Gemini AI.**

**Universal Multi-File RAG Assistant** is a document intelligence application built with **Python, Streamlit, LangChain, HuggingFace embeddings, ChromaDB, and Google Gemini**.

Upload multiple documents, automatically extract and index their content, and interact with the combined knowledge base through a conversational AI interface.

### 🔗 Live Demo

**[Launch Universal RAG Assistant →](https://lynxrag.streamlit.app/)**

---

# ✨ Features

## 📁 Multi-Format Document Support

Upload and process multiple file formats from a single interface:

| Format               | Extension |
| -------------------- | --------- |
| PDF                  | `.pdf`    |
| Microsoft Word       | `.docx`   |
| Microsoft Excel      | `.xlsx`   |
| Microsoft PowerPoint | `.pptx`   |
| Text                 | `.txt`    |
| CSV                  | `.csv`    |

---

## 🤖 AI-Powered Document Chat

Ask natural-language questions about your uploaded documents and receive context-aware answers generated using **Google Gemini**.

### Example Questions

```text
Summarize all the uploaded documents.
```

```text
What are the key findings in the report?
```

```text
Compare the revenue figures between these two Excel files.
```

```text
Which slide discusses the project architecture?
```

```text
Find the section related to employee benefits.
```

---

## 🧠 Retrieval-Augmented Generation

The application uses a **RAG pipeline** to retrieve relevant document chunks before generating an answer.

Instead of relying only on the AI model's pretrained knowledge, the system retrieves relevant information directly from your uploaded files and provides that context to the model.

---

## 🔎 Source-Aware Retrieval

Relevant document content can be associated with its originating file and metadata, making it easier to understand where information was retrieved from.

---

## 🆓 Local Embeddings

The application uses open-source **HuggingFace / Sentence Transformers** models for embeddings.

Embedding generation can run locally, reducing the need for a separate paid embedding API.

---

## 🗄️ ChromaDB Vector Store

Document chunks are converted into vector representations and stored in **ChromaDB**, allowing semantically relevant information to be retrieved when users ask questions.

---

## 🔬 Vector Database Inspector

The application provides database inspection functionality to examine how uploaded documents are:

* Split into chunks
* Converted into embeddings
* Stored in the vector database
* Retrieved during question answering

This makes the RAG pipeline easier to understand and debug.

---

# 🧠 How RAG Works

**RAG = Retrieval-Augmented Generation**

A traditional LLM answers questions primarily using knowledge learned during training.

A RAG application adds a retrieval layer that allows the model to reference an external knowledge base.

## Universal RAG Pipeline

```text
                 ┌─────────────────────┐
                 │   Upload Documents  │
                 │ PDF DOCX XLSX PPTX  │
                 │ TXT / CSV           │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │  Document Parsing   │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │   Text Chunking     │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │  Local Embeddings   │
                 │ HuggingFace / ST     │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │      ChromaDB       │
                 │   Vector Storage    │
                 └──────────┬──────────┘
                            │
                      User Question
                            │
                            ▼
                 ┌─────────────────────┐
                 │ Semantic Retrieval  │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │    Google Gemini    │
                 │  Answer Generation  │
                 └──────────┬──────────┘
                            │
                            ▼
                 ┌─────────────────────┐
                 │    Final Answer     │
                 └─────────────────────┘
```

---

# 🎯 Why RAG?

RAG provides several advantages:

* **Grounded responses** — answers are based on retrieved document content.
* **No model retraining required** — documents can be added dynamically.
* **Private knowledge bases** — your own documents become the retrieval source.
* **Lower embedding costs** — local embedding models can eliminate external embedding API usage.
* **Multi-document retrieval** — multiple files can be processed into one searchable knowledge base.

> **Important:** RAG can significantly reduce hallucinations, but it cannot guarantee that an AI system will never produce an incorrect answer. Retrieval quality, document quality, prompts, and the underlying LLM all affect the final response.

---

# 🛠️ Technology Stack

| Category        | Technology                          | Purpose                          |
| --------------- | ----------------------------------- | -------------------------------- |
| UI              | Streamlit                           | Web application interface        |
| Language        | Python 3.11.7                       | Application development          |
| LLM             | Google Gemini                       | AI response generation           |
| Orchestration   | LangChain                           | RAG pipeline and LLM integration |
| Embeddings      | HuggingFace / Sentence Transformers | Local text embeddings            |
| Vector Database | ChromaDB                            | Semantic document retrieval      |
| PDF             | PyPDF                               | PDF text extraction              |
| Word            | python-docx                         | DOCX processing                  |
| Excel / CSV     | Pandas + OpenPyXL                   | Spreadsheet processing           |
| PowerPoint      | python-pptx                         | Presentation extraction          |

---

# 📦 Dependencies

The project uses the following core Python packages:

```text
streamlit
pandas
openpyxl
python-docx
python-pptx
pypdf

langchain
langchain-core
langchain-community
langchain-text-splitters

langchain-google-genai
langchain-huggingface
langchain-chroma

sentence-transformers
torchvision
```

---

# 🚀 Getting Started

Follow the steps below to run **Universal Multi-File RAG Assistant** locally.

# 1. Prerequisites

Before installing and running **Universal Multi-File RAG Assistant**, make sure the following are installed and configured:

* **Python 3.11.7**
* **Git**
* **Google Gemini API Key**

---

## 🐍 Python 3.11.7

Python 3.11.7 is required to run this project.

### Windows

1. Download **Python 3.11.7** from the official Python website:

   https://www.python.org/downloads/release/python-3117/

2. Run the installer.

3. **Important:** Before clicking **Install Now**, make sure this option is checked:

```text
☑ Add python.exe to PATH
```

4. Complete the installation.

5. Open **Command Prompt** or **PowerShell** and verify the installation:

```bash
python --version
```

Expected output:

```text
Python 3.11.7
```

If `python` is not recognized, try:

```bash
py --version
```

---

### macOS

You can install Python using the official installer or Homebrew.

#### Option 1 — Official Installer

Download Python 3.11.7:

https://www.python.org/downloads/release/python-3117/

Install the downloaded `.pkg` file and follow the installation instructions.

Verify the installation:

```bash
python3 --version
```

Expected output:

```text
Python 3.11.7
```

#### Option 2 — Homebrew

If Homebrew is installed:

```bash
brew install python@3.11
```

Then verify:

```bash
python3.11 --version
```

Expected output:

```text
Python 3.11.x
```

---

### Linux

On Debian / Ubuntu-based systems, update the package list:

```bash
sudo apt update
```

Install Python:

```bash
sudo apt install python3.11 python3.11-venv python3-pip
```

Verify:

```bash
python3.11 --version
```

Expected output:

```text
Python 3.11.x
```

> **Note:** Python installation commands may differ between Linux distributions. If your distribution does not provide Python 3.11 through its default repositories, use the official Python documentation for the appropriate installation method.

---

## 🔧 Verify Python and pip

After installing Python, verify both Python and `pip`.

### Windows

```bash
python --version
```

```bash
python -m pip --version
```

### macOS / Linux

```bash
python3 --version
```

```bash
python3 -m pip --version
```

If `pip` needs to be updated:

### Windows

```bash
python -m pip install --upgrade pip
```

### macOS / Linux

```bash
python3 -m pip install --upgrade pip
```

---

# 2. Git

Git is required to clone the Universal Multi-File RAG Assistant repository.

## Windows

### Option 1 — Official Installer

Download Git for Windows:

https://git-scm.com/download/win

Run the installer and follow the default installation options.

After installation, open **Command Prompt** or **PowerShell** and verify:

```bash
git --version
```

Expected output will look similar to:

```text
git version 2.x.x
```

### Option 2 — Windows Package Manager

If `winget` is available:

```powershell
winget install --id Git.Git -e --source winget
```

Then verify:

```bash
git --version
```

---

## macOS

### Option 1 — Homebrew

If Homebrew is installed:

```bash
brew install git
```

Verify:

```bash
git --version
```

### Option 2 — Xcode Command Line Tools

macOS can also install Git through the Xcode Command Line Tools:

```bash
xcode-select --install
```

Then verify:

```bash
git --version
```

---

## Linux

### Ubuntu / Debian

Update the package list:

```bash
sudo apt update
```

Install Git:

```bash
sudo apt install git
```

Verify:

```bash
git --version
```

### Fedora

```bash
sudo dnf install git
```

Verify:

```bash
git --version
```

### Arch Linux

```bash
sudo pacman -S git
```

Verify:

```bash
git --version
```

---

# 3. Google Gemini API Key

The application uses **Google Gemini** to generate AI-powered responses based on the retrieved document content.

You need a Google Gemini API key before running the application.

## Get Your API Key

Create an API key through **Google AI Studio**:

https://aistudio.google.com/apikey

Sign in with your Google account and create an API key.

Copy the generated API key and keep it secure.

---

## Configure the API Key

For local development, you can configure the key as an environment variable.

### Windows — PowerShell

```powershell
$env:GOOGLE_API_KEY="YOUR_API_KEY"
```

### Windows — Command Prompt

```cmd
set GOOGLE_API_KEY=YOUR_API_KEY
```

### macOS / Linux

```bash
export GOOGLE_API_KEY="YOUR_API_KEY"
```

Replace:

```text
YOUR_API_KEY
```

with your actual Gemini API key.

---

## ⚠️ Keep Your API Key Secret

**Never publish your API key on GitHub.**

Do not put your real key directly into:

```text
app.py
README.md
requirements.txt
Git commits
Public repositories
```

For example, **do not** do this:

```python
GOOGLE_API_KEY = "AIzaSyXXXXXXXXXXXXXXXXXXXXXXXX"
```

Use environment variables or Streamlit Secrets instead.

If you use a `.env` file or Streamlit secrets, make sure sensitive files are included in `.gitignore`:

```gitignore
.env
.streamlit/secrets.toml
```

---

# 4. Verify All Prerequisites

Before continuing with the installation, verify that the required tools are available.

### Windows

```bash
python --version
```

```bash
git --version
```

```bash
python -m pip --version
```

### macOS / Linux

```bash
python3 --version
```

```bash
git --version
```

```bash
python3 -m pip --version
```

You should have:

```text
Python 3.11.7
Git installed
pip installed
Google Gemini API key configured
```

Once all prerequisites are ready, continue to:



---

# 2. Clone the Repository

Open your terminal or command prompt:

```bash
git clone https://github.com/technomaxxa/Universal-RAG.git
```

Then enter the project directory:

```bash
cd Universal-RAG
```

---

# 3. Create a Virtual Environment

Using a virtual environment is recommended to avoid dependency conflicts.

## Windows

```bash
python -m venv env
```

Activate it:

```bash
env\Scripts\activate
```

After activation, your terminal should show something similar to:

```text
(env)
```

## macOS / Linux

Create the environment:

```bash
python3 -m venv env
```

Activate it:

```bash
source env/bin/activate
```

---

# 4. Upgrade pip

It is recommended to update `pip` before installing the dependencies.

```bash
python -m pip install --upgrade pip
```

---

# 5. Install Dependencies

If the repository contains `requirements.txt`, simply run:

```bash
pip install -r requirements.txt
```

This is the **recommended installation method**.

### Manual Installation

If `requirements.txt` is not available, install the dependencies directly:

```bash
pip install streamlit pandas openpyxl python-docx python-pptx pypdf langchain langchain-community langchain-core langchain-text-splitters langchain-google-genai langchain-huggingface sentence-transformers langchain-chroma torchvision
```

---

# 🔑 6. Configure Google Gemini API

The application requires a **Google Gemini API key** for AI-powered responses.

Create your API key using **Google AI Studio**.

For local development, configure the API key as an environment variable.

## Windows PowerShell

```powershell
$env:GOOGLE_API_KEY="YOUR_API_KEY"
```

## Windows Command Prompt

```cmd
set GOOGLE_API_KEY=YOUR_API_KEY
```

## macOS / Linux

```bash
export GOOGLE_API_KEY="YOUR_API_KEY"
```

Replace:

```text
YOUR_API_KEY
```

with your actual Gemini API key.

> **Security:** Never commit your API key to GitHub. Never publish a real API key inside `app.py` or any other tracked source file.

---

# ▶️ 7. Run the Application

Once your virtual environment is activated and the dependencies are installed:

```bash
streamlit run app.py
```

Streamlit will start the local development server.

You can normally access the application at:

```text
http://localhost:8501
```

---

# ⚡ Quick Start

If Python and Git are already installed, the basic setup is:

## Windows

```bash
git clone https://github.com/technomaxxa/Universal-RAG.git
cd Universal-RAG

python -m venv env
env\Scripts\activate

python -m pip install --upgrade pip
pip install -r requirements.txt

streamlit run app.py
```

## macOS / Linux

```bash
git clone https://github.com/technomaxxa/Universal-RAG.git
cd Universal-RAG

python3 -m venv env
source env/bin/activate

python -m pip install --upgrade pip
pip install -r requirements.txt

streamlit run app.py
```

---

# 📖 Usage

## Step 1 — Upload Documents

Open the application and use the file uploader in the sidebar.

Supported formats:

```text
PDF
DOCX
XLSX
PPTX
TXT
CSV
```

You can upload multiple files and use them together as a single searchable knowledge base.

---

## Step 2 — Document Processing

The application processes the uploaded files by:

```text
Upload
   ↓
Document Parsing
   ↓
Text Extraction
   ↓
Text Chunking
   ↓
Embedding Generation
   ↓
ChromaDB Storage
```

The resulting vector database is then used for semantic retrieval.

---

## Step 3 — Ask Questions

Once processing is complete, use the chat interface to ask questions about your documents.

### Example

```text
Summarize the uploaded report.
```

```text
What are the main conclusions?
```

```text
Compare the two financial statements.
```

```text
Which presentation slide contains the project timeline?
```

```text
Find all references to the company's revenue.
```

---

## Step 4 — Inspect the Vector Database

Use the database inspection functionality to understand how the application processes and stores your documents.

You can inspect:

* Document chunks
* Embedding data
* Stored records
* Retrieved context

---

# 📂 Supported File Types

| Extension | Format               | Processing              |
| --------- | -------------------- | ----------------------- |
| `.pdf`    | PDF Document         | Text extraction         |
| `.docx`   | Microsoft Word       | Paragraph extraction    |
| `.xlsx`   | Microsoft Excel      | Spreadsheet processing  |
| `.pptx`   | Microsoft PowerPoint | Slide/text extraction   |
| `.txt`    | Plain Text           | Text ingestion          |
| `.csv`    | CSV Data             | Tabular data processing |

---

# 🔐 Security

If you plan to deploy this application publicly, follow these practices.

## Never Commit API Keys

### Do NOT do this:

```python
GOOGLE_API_KEY = "AIza..."
```

### Instead

Use environment variables or Streamlit secrets.


---

## Protect Uploaded Documents

Do not upload confidential or sensitive documents to a public deployment unless you understand how the application stores, processes, and transmits those files.

---



> The exact structure may vary depending on the current implementation.

---

# 🌐 Live Demo

Try the deployed application:

**https://lynxrag.streamlit.app/**

---

# 🧪 Example Use Cases

Universal Multi-File RAG Assistant can be useful for:

* Research papers and study materials
* Business reports
* Financial spreadsheets
* Company documentation
* Presentation analysis
* PDF document analysis
* Internal knowledge bases
* Technical documentation
* Multi-document research
* Report summarization

---

# ⚡ Why This Project?

Many document-chat applications are designed around a single file or a limited number of formats.

**Universal Multi-File RAG Assistant** takes a multi-document approach:

> **Upload your document collection and interact with it as one searchable knowledge base.**

The combination of:

```text
Multi-Format Ingestion
        +
Local Embeddings
        +
Vector Search
        +
Google Gemini
        +
LangChain
```

provides a flexible foundation for building document intelligence applications.

---

# 🗺️ Future Improvements

Potential improvements include:

* [ ] Streaming AI responses
* [ ] Conversation history
* [ ] Multiple independent knowledge bases
* [ ] Advanced metadata filtering
* [ ] Improved citation rendering
* [ ] Document preview
* [ ] Drag-and-drop document management
* [ ] Authentication and user accounts
* [ ] Persistent cloud vector storage
* [ ] Additional file formats
* [ ] Retrieval reranking
* [ ] Configurable embedding models
* [ ] Retrieval evaluation and analytics


---

# 👨‍💻 Author

## Sumanta Hens

**Developer • AI/RAG Enthusiast • Full-Stack Developer**

### Connect

* LinkedIn: https://www.linkedin.com/in/sumantahens/
* GitHub: https://github.com/technomaxxa

---

# ⭐ Support the Project

If you find **Universal Multi-File RAG Assistant** useful:

* ⭐ Star the repository
* 🐛 Report bugs
* 💡 Suggest improvements
* 🔀 Submit pull requests
* 📢 Share the project

---

<p align="center">

### 🗂️ Universal Multi-File RAG Assistant

**Built with Python • LangChain • ChromaDB • HuggingFace • Google Gemini • Streamlit**

</p>
