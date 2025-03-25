## 📖 Usage Guide

### Document Management
1. Click "Upload Documents" in the sidebar.
2. Select one or more files to upload.
3. Wait for the indexing process to complete.
4. Use the document browser to view uploaded files.

### Asking Questions
1. Type your question in the chat input field.
2. Press Enter or click the send button.
3. View the AI-generated response with citations.
4. Continue the conversation with follow-up questions.

### Voice Interaction
1. Click the microphone button to activate voice input.
2. Speak your question clearly.
3. Toggle "Enable Voice Output" to have responses read aloud.
4. Use the stop button to interrupt voice input/output.

### Settings & Customization
1. Select your preferred language model.
2. Adjust RAG parameters for retrieval precision.
3. Configure voice settings if using speech features.
4. Toggle between dark and light themes.


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



```markdown
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
