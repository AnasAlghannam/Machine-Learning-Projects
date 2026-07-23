# Build a Crew to Tailor Job Applications

**Author:** Anas AlGhannam  
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

A crewAI crew that tailors a job application to a specific posting. Agents research the candidate's profile and the target role, then customize a resume and prepare interview talking points.

## Techniques
- Multi-agent collaboration with crewAI
- File and web tools for reading a resume and researching a role
- Task chaining across agents
- Personalized resume tailoring and interview prep

## Setup

Run this project inside its own virtual environment so its dependencies stay isolated from other projects.

> **Note:** use a fresh virtual environment as shown below (not a base Anaconda environment). Installing crewAI into base Anaconda can break its `protobuf` and cause a `libprotobuf` load error.

```bash
cd TailorJobApplicationsCrew
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install crewai crewai-tools langchain-community python-dotenv jupyter ipykernel
```

Register the environment as a Jupyter kernel, then launch the notebook:

```bash
python -m ipykernel install --user --name TailorJobApplicationsCrew --display-name "Python (TailorJobApplicationsCrew)"
jupyter notebook "TailorJobApplicationsCrew.ipynb"
```

In the notebook, choose **Kernel → Change kernel → Python (TailorJobApplicationsCrew)**. Run `deactivate` when you're finished.

### API keys

This project calls Groq and Serper (web search). Create a `.env` file in this folder (or the repo root — it is discovered automatically) with:

```
GROQ_API_KEY=your_key_here
SERPER_API_KEY=your_key_here
```

Get keys at: [console.groq.com/keys](https://console.groq.com/keys), [serper.dev](https://serper.dev). `.env` is git-ignored — never commit it.
