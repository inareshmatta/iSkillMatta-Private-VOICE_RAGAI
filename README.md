# UNOS AI System Architecture

## System Overview

UNOS AI is a document-based question answering system that combines local language models with retrieval-augmented generation (RAG) to provide accurate answers based on user-provided documents. The system supports both text and voice interaction as input/output methods.

## Architecture Diagram

```mermaid
graph TD
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

graph LR
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

## Core Components
### 1. Document RAG (Retrieval-Augmented Generation)
The DocumentRAG class in app/core/document_rag.py is the central component that:

- Processes and indexes uploaded documents
- Searches for relevant context based on user queries
- Generates responses using the selected language model
### 2. UI Components
The UI is built with Streamlit and organized into modular components:

- main.py : Application entry point and session state management
- app/ui/styles.py : Custom CSS and theme management
- app/ui/sidebar.py : Document upload and settings sidebar
- app/ui/chat.py : Chat interface with optional voice capabilities
### 3. Voice Interaction System
Voice capabilities are implemented as optional features:

- Voice Input : Optional microphone button to speak queries instead of typing
- Voice Output : Optional toggle to have responses read aloud using Google TTS
- Audio Settings : Configuration for microphones and speakers
## Data Flow
1. User uploads documents through the sidebar
2. Documents are processed and indexed by the RAG engine
3. User asks a question via text input or optionally via voice
4. System searches for relevant context in the indexed documents
5. Language model generates a response based on the context
6. Response is displayed to the user as text
7. Optionally, if voice output is enabled, the response is also read aloud
## Technology Stack
- Frontend : Streamlit
- Language Models : DeepSeek-R1, Gemma-3B
- Embeddings : Sentence Transformers
- Vector Search : FAISS
- Document Processing : PyPDF2, python-docx, etc.
- Voice Features :
  - Speech Recognition : Google Speech API
  - Text-to-Speech : Google TTS (gTTS)
## Design Patterns
- Singleton Pattern : Session state management
- Factory Pattern : Document processor selection based on file type
- Strategy Pattern : Switching between different language models
- Observer Pattern : UI updates based on state changes
## Future Improvements
- Implement caching for faster response generation
- Add distributed processing for handling larger document collections
- Implement streaming responses for better user experience
- Add user authentication and document persistence
- Enhance voice recognition accuracy with custom models


This comprehensive architecture document includes:
1. A high-level system overview
2. A detailed component diagram showing system interactions
3. A linear flow diagram of the query process
4. A mindmap of the entire system structure
5. Detailed descriptions of core components
6. Information about data flow, technology stack, and design patterns
