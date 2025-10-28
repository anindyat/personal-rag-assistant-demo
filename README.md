# personal-rag-assistant-demo
Personal RAG Assistant
This project started as an experiment in Agentic AI — building an autonomous, context-aware assistant that could reason, retrieve, and respond based on my own data.

I didn’t spend a dollar on hosting or APIs — everything ran locally.

Here’s what I put together:

🧾 Data Foundation:
I began with a small family profile text file, describing who I am, my daughter, and basic family details — just enough context for grounding.

📧 Email Integration:
I connected securely to my personal email using an access key from my provider, limiting it to recent emails and attachments to keep the dataset lightweight.

🔢 Vectorization:
Using OpenAI Embeddings and an AutoEncoder-based open-source LLM, I vectorized both the family and email data, and stored them in a local Chroma vector datastore.

🧩 RAG Construction:
With LangChain, I stitched together a Retrieval-Augmented Generation (RAG) pipeline — combining local document retrieval with generative reasoning.

🎙️ Voice Input:
The Gradio chat interface accepts audio input.
The speech is first transcribed into text using the Whisper-1 model.

💬 Reasoning and Response:
The transcribed text is sent to an open-source LLM, augmented by RAG retrievals from Chroma — ensuring that responses are both contextually grounded and cost-efficient.

🔊 Voice Output:
Finally, the text response is converted back into speech using gpt-4o-mini-tts, completing a natural, conversational loop.

🔒 Privacy by Design

For security reasons, none of the data — not even embeddings — left my local environment.
All retrieval, inference, and storage were done entirely on my machine.
It’s not production-grade, but it’s good enough for personal use — and safe enough for private context.
