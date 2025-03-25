# UNOS AI Assistant

<div align="center">
  <img src="https://via.placeholder.com/200x200.png?text=UNOS+AI" alt="UNOS AI Logo" width="200" />
  <p><em>Your documents, intelligently answered</em></p>
  
  [![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)  
  [![Streamlit](https://img.shields.io/badge/Streamlit-1.31.0-FF4B4B.svg)](https://streamlit.io/)  
  [![PyTorch](https://img.shields.io/badge/PyTorch-2.0.1-EE4C2C.svg)](https://pytorch.org/)  
  [![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
</div>

---

## 🌟 Features

### 📄 Document Intelligence
- **Multi-format Support:** Process PDF, DOCX, TXT, XLSX, CSV, and more.
- **Smart Indexing:** Efficiently index and search document content.
- **Context-aware Responses:** Retrieve answers that reference specific sections of your documents.

### 🧠 AI Capabilities
- **Local LLM Integration:** Uses DeepSeek-R1 and Gemma-3B models for privacy and speed.
- **Retrieval-Augmented Generation (RAG):** Combines document retrieval with generative AI.
- **Customizable Parameters:** Adjust context length, temperature, and other generation settings.

### 💻 User Experience
- **Intuitive Chat Interface:** Simple, conversational UI for asking questions.
- **Dark/Light Mode:** Choose your preferred visual theme.
- **Session Persistence:** Chat history and document indexes are preserved between sessions.

### 🎤 Voice Interaction (Optional)
- **Voice Input:** Ask questions using your microphone.
- **Voice Output:** Have responses read aloud with natural-sounding speech.
- **Device Selection:** Choose from available microphones and speakers.

---

## 🚀 Getting Started

### Prerequisites
- Python 3.8 or higher
- Windows operating system
- 8GB+ RAM recommended for optimal performance
- GPU acceleration supported but not required

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/unos-ai.git
   cd unos-ai


📖 Usage Guide
Document Management
Click "Upload Documents" in the sidebar.

Select one or more files to upload.

Wait for the indexing process to complete.

Use the document browser to view uploaded files.

Asking Questions
Type your question in the chat input field.

Press Enter or click the send button.

View the AI-generated response with citations.

Continue the conversation with follow-up questions.

Voice Interaction
Click the microphone button to activate voice input.

Speak your question clearly.

Toggle "Enable Voice Output" to have responses read aloud.

Use the stop button to interrupt voice input/output.

Settings & Customization
Select your preferred language model.

Adjust RAG parameters for retrieval precision.

Configure voice settings if using speech features.

Toggle between dark and light themes.

🏗️ Architecture
UNOS AI follows a modular architecture with these key components:

Document Processing: Handles parsing and indexing of various file formats.

RAG Engine: Manages document retrieval and context preparation.

Language Models: Generates responses based on queries and context.

UI Layer: Streamlit-based interface with responsive design.

Voice System: Optional speech recognition and synthesis capabilities.

For more details, see ARCHITECTURE.md.

🛠️ Technologies Used
Streamlit

PyTorch

Transformers

FAISS

Google Speech API

Google TTS

NumPy

Pillow

🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

Fork the repository.

Create your feature branch (git checkout -b feature/amazing-feature).

Commit your changes (git commit -m 'Add some amazing feature').

Push to the branch (git push origin feature/amazing-feature).

Open a Pull Request.

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

.

🙏 Acknowledgments
Built with Streamlit.

Powered by DeepSeek and Gemma language models.

Uses FAISS for vector search.

Speech recognition powered by Google Speech API.


# UNOS AI System Architecture

## System Overview
UNOS AI is a document-based question answering system that combines local language models with retrieval-augmented generation (RAG) to provide accurate answers based on user-provided documents. The system supports both text and voice interaction as input/output methods.

## Architecture Diagram
```mermaid
flowchart TD
    User[User] --> UI[Streamlit UI]
    UI --> DocUpload[Document Upload]
    UI --> QueryInput[Query Input]
    UI --> VoiceSystem[Voice System]
    
    DocUpload --> DocProcessor[Document Processor]
    DocProcessor --> Indexer[Document Indexer]
    Indexer --> VectorDB[Vector Database]
    
    QueryInput --> RAG[RAG Engine]
    VoiceSystem --> SpeechRecognition[Speech Recognition]
    SpeechRecognition --> RAG
    
    RAG --> VectorDB
    RAG --> LLM[Language Model]
    RAG --> ResponseGen[Response Generator]
    
    ResponseGen --> UI
    ResponseGen --> TTS[Text-to-Speech]
    TTS --> VoiceSystem
    
    style User fill:#f9d5e5,stroke:#333,stroke-width:2px
    style UI fill:#d0f0c0,stroke:#333,stroke-width:2px
    style RAG fill:#f0e68c,stroke:#333,stroke-width:2px
    style LLM fill:#add8e6,stroke:#333,stroke-width:2px

flowchart LR
    A[User Query] --> B[Document Search]
    B --> C[Context Retrieval]
    C --> D[Response Generation]
    D --> E[Response to User]
    
    style A fill:#f9d5e5,stroke:#333,stroke-width:2px
    style B fill:#eeeeee,stroke:#333,stroke-width:2px
    style C fill:#dddddd,stroke:#333,stroke-width:2px
    style D fill:#cccccc,stroke:#333,stroke-width:2px
    style E fill:#b5ead7,stroke:#333,stroke-width:2px

mindmap
  root((UNOS AI))
    Core Components
      Document RAG
        Document Processing
          PDF Parser
          DOCX Parser
          TXT Parser
          XLSX Parser
        Vector Database
          FAISS Index
          Embeddings
        Context Retrieval
          Semantic Search
          Relevance Ranking
        Response Generation
          LLM Integration
            DeepSeek-R1
            Gemma-3B
          Context Injection
          Citation Generation
      User Interface
        Streamlit Frontend
          Chat Interface
          Document Upload
          Settings Panel
        Theme Management
          Dark Mode
          Light Mode
        Session State
          Chat History
          User Preferences
      Voice System
        Speech Recognition
          Google Speech API
          Fallback Systems
        Text-to-Speech
          Google TTS
          Voice Settings
        Audio Device Management
          Microphone Selection
          Speaker Selection
    Data Flow
      Input Processing
        Text Input
        Voice Input
      Document Indexing
        Text Extraction
        Chunking
        Embedding Generation
      Query Processing
        Context Retrieval
        Response Generation
      Output Handling
        Text Display
        Voice Output
Core Components
1. Document RAG (Retrieval-Augmented Generation)
The DocumentRAG class in app/core/document_rag.py is the central component that:

Processes and indexes uploaded documents.

Searches for relevant context based on user queries.

Generates responses using the selected language model.

2. UI Components
The UI is built with Streamlit and organized into modular components:

main.py: Application entry point and session state management.

app/ui/styles.py: Custom CSS and theme management.

app/ui/sidebar.py: Document upload and settings sidebar.

app/ui/chat.py: Chat interface with optional voice capabilities.

3. Voice Interaction System
Voice capabilities are implemented as optional features:

Voice Input: Optional microphone button to speak queries.

Voice Output: Optional toggle to have responses read aloud using Google TTS.

Audio Settings: Configuration for microphones and speakers.

Data Flow
User uploads documents through the sidebar.

Documents are processed and indexed by the RAG engine.

User asks a question via text input or optionally via voice.

System searches for relevant context in the indexed documents.

Language model generates a response based on the context.

Response is displayed to the user as text.

Optionally, if voice output is enabled, the response is also read aloud.

Technology Stack
Category	Technologies
Frontend	Streamlit
Language Models	DeepSeek-R1, Gemma-3B
Embeddings	Sentence Transformers
Vector Search	FAISS
Document Processing	PyPDF2, python-docx, openpyxl, BeautifulSoup4
Speech Recognition	Google Speech API
Text-to-Speech	Google TTS (gTTS)
Design Patterns
Singleton Pattern: Session state management.

Factory Pattern: Document processor selection based on file type.

Strategy Pattern: Switching between different language models.

Observer Pattern: UI updates based on state changes.

Future Improvements
Implement caching for faster response generation.

Add distributed processing for handling larger document collections.

Implement streaming responses for a better user experience.

Add user authentication and document persistence.

Enhance voice recognition accuracy with custom models.
