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

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

```bash
cd ManualToolCallingAgent
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install pytube youtube-transcript-api langchain langchain-community langchain-groq yt-dlp python-dotenv jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name ManualToolCallingAgent --display-name "Python (ManualToolCallingAgent)"
jupyter notebook "ManualToolCallingAgent.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (ManualToolCallingAgent)**. Run `deactivate` when you're finished.

### API keys

This project calls Groq. Create a `.env` file in this folder (or the repo root — it is discovered automatically) with:

```
GROQ_API_KEY=your_key_here
```

Get keys at: [console.groq.com/keys](https://console.groq.com/keys). `.env` is git-ignored — never commit it.
