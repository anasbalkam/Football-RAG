⚽ Football Reference AI
A highly structured, multi-agent Retrieval-Augmented Generation (RAG) system designed to act as an elite FIFA match official. This application dynamically queries the official IFAB Laws of the Game, processes complex chronological match events using Chain-of-Thought reasoning, and outputs deterministic, structured JSON for a custom-built frontend.

✨ Key Features
Multi-Agent Architecture: Utilizes a dual-agent system. An "Optimizer Agent" resolves pronouns and conversation history to engineer precise database queries, while a "Logic Agent" evaluates edge cases and generates final rulings.

Dynamic Contextual Memory: Implements unique session IDs via localStorage to isolate and maintain conversation history for multiple simultaneous users without cross-contamination.

Dual-Mode JSON Routing: The AI intelligently categorizes user intent, seamlessly switching its strict JSON schema between actionable match rulings (Decision, Restart, Disciplinary) and philosophical rule explanations.

IFAB-Specific RAG: Grounded entirely in official football documentation (Laws of the Game, VAR Protocols, Case Studies) via Pinecone vector embeddings to eliminate AI hallucination.

Vanilla Single-Page UI: A premium, responsive, and accessible frontend built entirely in HTML/JS/CSS, featuring dynamic UI rendering based on the AI's structured payload.

🛠️ Tech Stack
Backend Orchestration: n8n

Vector Database: Pinecone

LLM Engine: OpenRouter (gpt-4o / gpt-4o-mini)

Embeddings: OpenAI

Frontend: Vanilla HTML5, CSS3, JavaScript

Hosting: Vercel (Frontend) / n8n Cloud (Backend)

🧠 How It Works
User Input: The user submits a football scenario or rule question via the frontend.

Intent & Memory Optimization: The input and unique Session ID hit the n8n webhook. The Optimizer Agent checks the conversation history, resolves pronouns, and rewrites the query for optimal vector retrieval.

Knowledge Retrieval: The optimized query searches the Pinecone database to extract the exact IFAB laws relevant to the scenario.

Logic Processing: The Logic Agent applies a strict Chain-of-Thought protocol to analyze the timeline (e.g., checking for advantage or quick free kicks) and applies the retrieved rules.

Structured Output: The AI formats the ruling into a pristine JSON object and passes it back to the frontend, which dynamically renders the correct visual UI cards.
