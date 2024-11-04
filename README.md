# **Local LLM Sandbox for RAG**

### **Overview**

Welcome to **Local LLM Sandbox for RAG**, an experimental setup designed to test and develop Retrieval-Augmented Generation (RAG) capabilities using local Large Language Models (LLMs). By leveraging Ollama for running LLMs and generating embeddings with `nomic-embed-text`, this sandbox offers a flexible environment to test document-based question answering. The project also incorporates Chroma as a vector database to store embeddings and a Streamlit web UI for enhanced user interaction.

### **Features**

- **Local Language Model**: Run LLMs locally with Ollama for efficient and private experiments.
- **RAG Document QA**: Utilize RAG to enable question-answering based on embedded document content.
- **User-Friendly Web UI**: Built with Streamlit, the UI offers an accessible, visual interface for configuring models and interacting with the document-based QA system.

### **Requirements**

To set up and run this sandbox, you’ll need:

- **Ollama version 0.1.26 or higher**
- **Python 3.x**

### **Installation**

1. **Clone the Repository**: 
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```

2. **Create and Activate a Virtual Environment**:
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate    # On Unix/MacOS
   .\.venv\Scripts\activate      # On Windows
   ```

3. **Install Required Packages**:
   ```bash
   pip install -r requirements.txt
   ```

### **Running the Project**

#### **Command Line Interface (CLI)**

1. **Activate** the virtual environment:
   ```bash
   source .venv/bin/activate    # Unix/MacOS
   .\.venv\Scripts\activate      # Windows
   ```

2. **Run the Main Script**:
   ```bash
   python app.py -m <model_name> -p <path_to_documents>
   ```
   - **Model Name (`-m`)**: Specify the model to use (defaults to `mistral`).
   - **Path to Documents (`-p`)**: Specify a path to documents for embedding and querying. Defaults to `Research` folder in the repo.

3. **Embedding Model**:
   - Optionally, specify an embedding model with `-e <embedding_model_name>`. Defaults to `nomic-embed-text`.

#### **Example**:
```bash
python app.py -m mistral -p Research -e nomic-embed-text
```

#### **Streamlit Web Interface**

1. **Activate** the virtual environment:
   ```bash
   source .venv/bin/activate    # Unix/MacOS
   .\.venv\Scripts\activate      # Windows
   ```

2. **Launch the Streamlit UI**:
   ```bash
   streamlit run ui.py
   ```

This will start a local server and open the Streamlit UI in your default browser.

### **Features Explained**

- **Local LLM Interaction**: The sandbox enables local interaction with an LLM, ensuring privacy and adaptability for experiments.
- **Document Embeddings**: Each document is chunked and embedded, making it searchable for question-answering tasks.
- **Intuitive Web UI**: Users can switch between models and specify folders for document sources via the Streamlit UI. This provides a more intuitive way to interact with the RAG system compared to command-line usage.

### **Technologies Used**

- **LangChain**: A library for managing LLMs and chains in Python.
- **Ollama**: A platform for running local LLMs.
- **Chroma**: A vector database for embedding storage and retrieval.
- **PyPDF**: Python library for processing PDF files.
- **Streamlit**: Framework for creating interactive web apps.

### **Project Workflow**

1. **Environment Setup**: After cloning, set up the environment by installing dependencies listed in `requirements.txt`.
2. **Running the Application**:
   - **CLI Mode**: Run `app.py` to interact via the command line.
   - **UI Mode**: Run `ui.py` for a graphical experience with the Streamlit UI.
3. **Document Loading and Embedding**: Documents are processed and embedded, enabling RAG for document-based question answering.
4. **User Interaction**: Ask questions via chat (in both CLI and UI modes), and the application will provide answers based on document embeddings.

### **Future Directions**

To further develop the Local LLM Sandbox for RAG, consider implementing:

- **Persistent Embeddings**: Cache embeddings to avoid reloading every session.
- **Advanced Retrieval**: Test multi-document querying and more sophisticated retrieval methods.
- **Custom Model Tuning**: Experiment with fine-tuning models to improve answers for specialized documents.

### **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
