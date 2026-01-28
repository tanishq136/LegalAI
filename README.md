 LegalAI – Intelligent Case Analysis System

An AI-powered legal decision support system that analyzes case descriptions and judicial judgments to identify applicable IPC sections, retrieve similar precedents, and provide structured legal reasoning using Legal-BERT + FAISS + Retrieval-Augmented Architecture.

📌 Project Overview

LegalAI assists legal professionals, students, and researchers by:

Analyzing legal case descriptions

Identifying applicable IPC sections

Retrieving similar judicial precedents

Displaying complete judgment text

Providing structured legal insights

The system works offline, ensuring privacy and cost efficiency.

🚀 Key Features

🔐 User authentication (JWT-based)

📄 PDF judgment text extraction

🧠 Legal-BERT semantic embeddings

🔍 FAISS vector similarity search

⚖️ IPC section recommendation with confidence

📚 Similar precedent retrieval

🧾 Full judgment text display (not chunks)

🗂 Case history tracking

🧠 RAG-based legal reasoning (without live LLM)

🏗️ System Architecture
User Interface
     ↓
Flask Backend API
     ↓
Case Classification Model
     ↓
PDF Text Extraction (PyPDF2)
     ↓
Text Preprocessing
     ↓
Legal-BERT Embeddings
     ↓
FAISS Vector Database
     ↓
RAG Reasoning Engine
     ↓
Legal Analysis Output

🧠 Technologies Used
Component	Technology
Backend	Flask
Database	SQLite + SQLAlchemy
Authentication	JWT
NLP Model	Legal-BERT
Vector DB	FAISS
PDF Processing	PyPDF2
Frontend	HTML, CSS, JavaScript
Language	Python
Environment	Virtual Environment
📁 Project Structure
LegalAI/
│
├── app/
│   ├── api/              # API routes
│   ├── agents/           # Classifier & RAG logic
│   ├── auth/             # Authentication
│   ├── core/             # Database config
│   ├── etl/              # PDF extractor
│   ├── models/           # DB models
│   ├── vector_store/     # FAISS logic
│   └── templates/        # HTML templates
│
├── data/
│   ├── legal_pdfs/       # Raw judgment PDFs
│   ├── pdf_texts/        # Extracted full text
│   └── uploads/          # Uploaded PDFs
│
├── run_extractor.py      # PDF extraction runner
├── main.py               # Flask application entry
├── requirements.txt
└── README.md

⚙️ Installation & Setup
1️⃣ Clone Repository
git clone https://github.com/your-username/LegalAI.git
cd LegalAI

2️⃣ Create Virtual Environment
python -m venv venv
venv\Scripts\activate

3️⃣ Install Dependencies
pip install -r requirements.txt


If needed:

pip install flask sqlalchemy sentence-transformers faiss-cpu PyPDF2

📄 PDF Preparation (Important)

Place all judgment PDFs here:

data/legal_pdfs/


⚠️ Only text-based PDFs are supported by default.
Scanned PDFs require OCR (future enhancement).

🔄 PDF Extraction (One-Time Step)

Run extractor to convert PDFs into text:

python run_extractor.py


This will generate:

data/pdf_texts/*.txt


These files are used for semantic search.

▶️ Run the Application
python main.py


Open in browser:

http://127.0.0.1:8000

🧪 Example Use Case

Input Case:

A car driver hit a pedestrian and ran away from the spot.

System Output:

Case classification

Applicable IPC sections

Confidence score

Similar judicial precedents

Complete judgment text

Structured legal opinion

🧠 RAG Explanation

This project follows Retrieval-Augmented Generation architecture, where:

Retrieval: FAISS + Legal-BERT embeddings

Augmentation: Similar precedents

Generation: Structured legal reasoning (template-based)

Note: No live LLM is used.
The system is designed to support future LLM integration.

⚠️ Limitations

OCR not enabled for scanned PDFs

Does not provide legal advice

Intended for academic and research use only

🔮 Future Enhancements

OCR support for scanned judgments

Auto re-indexing on new PDF upload

Highlight relevant judgment paragraphs

LLM-based legal reasoning

Citation-aware responses

Court / year / judge metadata extraction

🎓 Academic Use

This project is suitable for:

Final year engineering projects

Legal AI research

NLP + Information Retrieval studies

RAG system demonstrations

⚖️ Disclaimer

This system is not a substitute for legal advice.
Outputs are for educational and research purposes only.
