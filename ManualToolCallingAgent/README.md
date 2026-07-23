# Build a Tool-Calling Agent

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

Builds a YouTube-analysis agent from the ground up. It defines LangChain tools to extract video IDs, fetch transcripts and metadata, search videos, and retrieve thumbnails, then demonstrates manual tool calling, a fixed-sequence summarization chain, and a recursive chain that decides which tools to use and when.

## Techniques
- Custom tools wrapping `pytube`, `youtube-transcript-api`, and `yt-dlp`
- Manual tool-call parsing and `ToolMessage` handling
- Fixed-sequence summarization chain with LCEL runnables
- Recursive/universal tool-calling chain
- End-to-end single-pass video summarization

## Setup
```bash
pip install pytube youtube-transcript-api langchain langchain-community langchain-groq yt-dlp python-dotenv
```

Create a `.env` file (in this folder or a parent) with your Groq API key:
```
GROQ_API_KEY=your_key_here
```
Get a free key at [console.groq.com](https://console.groq.com/keys). Then run:
```bash
jupyter notebook "ManualToolCallingAgent.ipynb"
```
