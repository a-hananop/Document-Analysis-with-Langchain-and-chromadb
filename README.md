# Document-Analysis-with-Langchain-and-chromadb

# 📚 PDF Vector Embedding with LangChain & Chroma

This project demonstrates how to build a **PDF-based retrieval system** using the **LangChain framework**, **HuggingFace embeddings**, and a **local Chroma vector database**.

With this setup, you can:
- Load and process PDF documents  
- Split them into manageable text chunks  
- Generate vector embeddings using `sentence-transformers`  
- Store and persist them in ChromaDB  
- Query your document intelligently to find the most relevant sections  

---

## 🚀 Features

✅ Load PDFs directly into LangChain  
✅ Automatically split text into logical chunks  
✅ Generate embeddings using a pre-trained HuggingFace model  
✅ Store and query embeddings locally with Chroma  
✅ Retrieve the top-k most relevant text chunks for any query  

---

## 🗂️ Project Structure

pdf_vector_repo/
│
├── src/
│ ├── init.py
│ ├── config.py # Configuration file (paths, model, chunk size)
│ ├── pdf_loader.py # Loads the PDF document
│ ├── text_splitter.py # Splits text into chunks
│ ├── embeddings_store.py # Creates embeddings and stores them in Chroma
│ └── query_engine.py # Handles similarity search queries
│
├── main.py # Main entry point
├── requirements.txt # Project dependencies
├── README.md # This file
└── .gitignore # Ignore cache, DB, logs, etc.


---

## 🧠 Workflow Overview

1. **Load the PDF**  
   Uses `PyPDFLoader` from `langchain_community` to extract text.  

2. **Split into Chunks**  
   Uses `RecursiveCharacterTextSplitter` to handle long text efficiently.  

3. **Generate Embeddings**  
   Uses the lightweight model:  
   `sentence-transformers/all-MiniLM-L6-v2`.  

4. **Store in Chroma**  
   Embeddings are stored locally in a persistent `chroma_db` directory.  

5. **Query the Document**  
   Enter a natural language question and retrieve the most relevant chunks.  

---

## ⚙️ Installation & Setup

### 1. Clone the repository
```bash
git clone <your_repo_url>
cd pdf_vector_repo

2. Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate      # macOS/Linux
venv\Scripts\activate         # Windows

3. Install dependencies
pip install -r requirements.txt

4. Configure paths

In src/config.py, update the path to your PDF:

PDF_PATH = r"C:\path\to\your\document.pdf"

▶️ Usage

Run the main script:

python main.py


You’ll see:

📄 Loading PDF...
✂️ Splitting text into chunks...
🧠 Creating and storing embeddings...
✅ Embeddings stored successfully.

💬 Enter your query:


Type your question (e.g., What is this document about?)
and you’ll get the top 3 most relevant text chunks from your PDF.

🧰 Requirements

Python 3.9+

LangChain

HuggingFace Transformers

ChromaDB

PyPDF2

All handled via:

langchain-community
langchain-text-splitters
langchain-huggingface
chromadb
pypdf
sentence-transformers
```

🧩 Example Output
💬 Enter your query: what is this document about?


# 🔍 Top relevant chunks:

Result (1):
This paper discusses the role of generative AI in modern chatbots...

<img width="550" height="234" alt="image" src="https://github.com/user-attachments/assets/fcfea270-d760-4ffa-b0a1-2673f7d9b11e" />


Result (2):
The document highlights advances in transformer-based models...

<img width="470" height="370" alt="image" src="https://github.com/user-attachments/assets/295a9827-a510-4f32-9d6a-dec85468218b" />


Result (3):
In conclusion, the paper emphasizes the importance of...

<img width="864" height="215" alt="image" src="https://github.com/user-attachments/assets/13e034be-9bb0-4eb7-84dd-35715b0e649c" />


🧱 How It Works Internally
| Step | Component                          | Description                                      |
| ---- | ---------------------------------- | ------------------------------------------------ |
| 1    | **PyPDFLoader**                    | Reads and extracts text from PDFs                |
| 2    | **RecursiveCharacterTextSplitter** | Breaks text into overlapping chunks              |
| 3    | **HuggingFaceEmbeddings**          | Converts text into dense numerical vectors       |
| 4    | **Chroma**                         | Stores vectors and performs similarity search    |
| 5    | **QueryEngine**                    | Retrieves and displays the most relevant content |



🧩 Customization

Change the embedding model in config.py:
```
EMBEDDING_MODEL = "sentence-transformers/all-mpnet-base-v2"
```


Adjust chunk size or overlap for better granularity:
```
CHUNK_SIZE = 1000
CHUNK_OVERLAP = 200
```

🧹 Cleanup

To clear your local Chroma database:
```
rm -rf chroma_db
```

🤝 Contributing

Feel free to fork this repository and open pull requests.
Suggestions and improvements are always welcome!

📜 License

This project is open-source under the MIT License.


💡 Credits

Developed using:
## LangChain
## HuggingFace Transformers
## Chroma
## Sentence Transformers


💬 “Empower your documents with intelligence — one vector at a time.”

```

✅ You can save this as `README.md` in your repository root — it’s fully formatted for GitHub display, includes all setup instructions, and works with your current codebase.
