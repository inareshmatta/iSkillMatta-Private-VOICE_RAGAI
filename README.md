# iSkillMatta's UNOS Private_VoiceRAG_AI 

  [![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/) 
  [![Streamlit](https://img.shields.io/badge/Streamlit-1.31.0-FF4B4B.svg)](https://streamlit.io/) 
  [![PyTorch](https://img.shields.io/badge/PyTorch-2.0.1-EE4C2C.svg)](https://pytorch.org/) 
  [![Transformers](https://img.shields.io/badge/Transformers-4.38.1-FFD700.svg)](https://huggingface.co/docs/transformers/) 
  [![FAISS](https://img.shields.io/badge/FAISS-1.7.4-0052CC.svg)](https://faiss.ai/) 
  [![gTTS](https://img.shields.io/badge/gTTS-Latest-FF69B4.svg)](https://pypi.org/project/gTTS/) 
  [![DeepSeekR1](https://img.shields.io/badge/DeepSeekR1-Supported-9400D3.svg)](https://deepseek.com/) 
  [![Gemma3](https://img.shields.io/badge/Gemma3-Supported-008000.svg)](https://ai.google.dev/gemma) 
  [![NumPy](https://img.shields.io/badge/NumPy-1.26.4-013243.svg)](https://numpy.org/) 
  [![Pillow](https://img.shields.io/badge/Pillow-10.2.0-ffa500.svg)](https://pypi.org/project/Pillow/) 
  [![Google Speech](https://img.shields.io/badge/Google_Speech-Optional-4285F4.svg)](https://cloud.google.com/speech-to-text) 
  [![Google TTS](https://img.shields.io/badge/Google_TTS-Optional-34A853.svg)](https://cloud.google.com/text-to-speech) 
  [![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)  



## 🌟 Features

### 📄 Document Intelligence
- **Multi-format Support**: Process PDF, DOCX, TXT, XLSX, CSV, and more
- **Smart Indexing**: Efficiently index and search through document content
- **Context-aware Responses**: Get answers that reference specific parts of your documents

### 🧠 AI Capabilities
- **Local LLM Integration**: Uses DeepSeek-R1 and Gemma-3B models for privacy and speed
- **Hybrid RAG Architecture**: 
  - Local Retrieval-Augmented Generation (RAG)
  - Offline Document Processing
  - Optional Online Components
- **Customizable Parameters**: Adjust context length, temperature, and other generation settings

### 💻 User Experience
- **Intuitive Chat Interface**: Simple, conversational UI for asking questions
- **Dark/Light Mode**: Choose your preferred visual theme
- **Session Persistence**: Chat history and document indexes are preserved between sessions

### 🎤 Voice Interaction (Optional)
- **Voice Input**: Ask questions using your microphone
- **Voice Output**: 
  - Optional Text-to-Speech (TTS)
  - Uses Google TTS (online service)
- **Device Selection**: Choose from available microphones and speakers

## 🔍 System Architecture

### Component Flow
```mermaid
flowchart TB
    A[User Interaction] --> B{Input Type}
    B -->|Text| C[Local Text Processing]
    B -->|Voice| D[Speech Recognition]
    
    C --> E[Document Search]
    D --> E
    
    E --> F[Context Retrieval]
    F --> G[Local RAG Engine]
    G --> H[Response Generation]
    
    H --> I{Output Mode}
    I -->|Text| J[Display Response]
    I -->|Voice| K[Optional Online TTS]
    
    subgraph RAG Features
        direction LR
        LocalRAG[Local Document Indexing]
        LocalModel[Offline Language Models]
        OnlineTTS[Optional Online TTS]
    end
    
    style A fill:#f9f3e0,stroke:#333,stroke-width:2px
    style B fill:#e6f2ff,stroke:#333,stroke-width:2px
    style E fill:#d9ead3,stroke:#333,stroke-width:2px
    style H fill:#f0e68c,stroke:#333,stroke-width:2px
    style I fill:#98fb98,stroke:#333,stroke-width:2px
```

### System Mindmap
```mermaid
mindmap
  root((UNOS AI))
    Architectural Components
      Document Processing
        Multi-Format Support
          PDF Parsing
          DOCX Parsing
          CSV Handling
          Excel Processing
      Intelligence Layer
        Retrieval Augmented Generation
          Local Vector Database
          Semantic Search
          Contextual Retrieval
        Language Models
          DeepSeek-R1
          Gemma-3B
      User Interface
        Interactive Chat
        Document Management
        Customization Options
      Interaction Modes
        Text Input
        Voice Input
        Optional Voice Output
      Technology Stack
        Frontend
          Streamlit
        Backend
          PyTorch
          Transformers
        Search
          FAISS Vector Database
```

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
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Download the language models:
- DeepSeek-R1
- Gemma-3B

4. Run the application:
```bash
python -m streamlit run main.py
```

## 📖 Usage Guide

### Document Management
- Click "Upload Documents" in the sidebar
- Select one or more files to upload
- Wait for the indexing process to complete
- Use the document browser to view uploaded files

### Asking Questions
- Type your question in the chat input field
- Press Enter or click the send button
- View the AI-generated response with citations
- Continue the conversation with follow-up questions

### Voice Interaction
- Click the microphone button to activate voice input
- Speak your question clearly
- Toggle "Enable Voice Output" to have responses read aloud
- Use the stop button to interrupt voice input/output

### Settings & Customization
- Select your preferred language model
- Adjust RAG parameters for retrieval precision
- Configure voice settings if using speech features
- Toggle between dark and light themes

## 🏗️ Key Architecture Highlights
- **Local-First Approach**: Prioritizes user privacy and offline capabilities
- **Flexible RAG Engine**: Adaptable to various document types and query needs
- **Modular Design**: Easy to extend and customize

## 🛠️ Technologies Used
- Streamlit
- PyTorch
- Transformers
- FAISS
- Google Speech (Optional)
- Google TTS (Optional)
- NumPy
- Pillow

## 🤝 Contributing
Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments
- Built with Streamlit
- Powered by DeepSeek and Gemma language models
- Uses FAISS for vector search
- Optional speech features powered by Google APIs
