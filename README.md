🤖 Project Submission: SmartSupport AI (RAG Helpdesk Bot)
📌 Project Overview
SmartSupport AI is a document-grounded customer service automation system engineered within the n8n orchestration ecosystem. The solution addresses a critical challenge in corporate AI deployments: mitigating text hallucinations. By utilizing a Retrieval-Augmented Generation (RAG) pipeline, the agent cannot manufacture arbitrary claims; it is contextually bound to answer user queries utilizing exclusively verified, internal company reference documentation.
⚙️ Core Architecture & Tech Stack
The platform splits data processing into two separate, secure decoupled phases:
Workflow Automation Engine: n8n (Cloud Infrastructure)
Large Language Model Layer: Google Gemini
Vector Infrastructure Database: Pinecone (Cloud Index)
Mathematical Vector Model: Google Gemini Embedding (models/gemini-embedding-001 / 3072 dimensions)
Text Partition System: Token Text Splitter (Chunk size: 500 characters, Overlap: 50 characters)
🗺️ Detailed System Flow
Phase 1: Data Ingestion Pipeline (The Knowledge Engine)
This decoupled back-end script automates data parsing from cloud storage silos into analytical vector coordinates:
Ingestion: The system triggers an automatic download pipeline fetching corporate policy manuals directly from a cloud directory (Google Drive Storage Node).
Extraction: Raw binary formats are converted down into text variables using the Extract From File Node.
Partitioning: The document text is broken into precise chunks using a Token Text Splitter to maintain semantic integrity.
Mathematical Translation: Text strings pass into Google Gemini Embeddings, turning plain text into uniform 3072-dimensional math vectors.
Database Storage: The vectors are stored in a Pinecone Index using cosine similarity metrics.
Phase 2: Live Interactive Chat Pipeline (The Customer Facing Agent)
This execution architecture handles consumer questions in real-time:
UI Interface: The consumer inputs their inquiry into n8n’s built-in, native Chat Trigger Web Component.
Context Layer: The request accesses an ephemeral Simple Memory Node, attaching the last 5 turns of historical conversation context.
Search Extraction: The request is converted to a vector and matched against the Pinecone Database Index via the Vector Store Question Answer Tool Node.
Final Generation: The closest textual paragraphs match, stream straight into the AI Agent Node, and the Google Gemini Chat Model renders a highly secure, accurate, hallucination-free resolution to the user.
💡 Key Competitive Highlights & Innovations
Zero-Hallucination Guardrails: Built explicitly with rigorous prompt criteria enforcing a strict fallback response ("I am sorry, I do not have that information") if data matches drop below standard vector score thresholds.
Optimized Resource Management: Leveraged dynamic text splitting parameters to maximize system lookup accuracy while remaining well inside free-tier payload limits.
Seamless Production Integration: Uses visual, modular drag-and-drop orchestration logic, meaning any business enterprise can hot-swap components instantly without rebuilding underlying code databases.
