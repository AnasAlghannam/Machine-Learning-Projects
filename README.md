# Machine Learning & AI Projects

**Author:** Anas AlGhannam
**Contributor:** [Anas AlGhannam (@AnasAlghannam)](https://github.com/AnasAlghannam)

A collection of machine learning, deep learning, and LLM-agent projects. Each project lives in
its own folder with a self-contained notebook and a README describing what it does, the techniques
used, and how to run it.

---

## LLM & Agent Projects

| Project | Description |
|---------|-------------|
| [InteractiveLLMAgentWithTools](InteractiveLLMAgentWithTools/) | Tool calling with LangChain — define tools, bind them to an LLM, and wrap the loop in an agent. |
| [ManualToolCallingAgent](ManualToolCallingAgent/) | A YouTube-analysis agent built from scratch, with manual, fixed-sequence, and recursive tool-calling chains. |
| [LLMDataScienceAgentLCEL](LLMDataScienceAgentLCEL/) | DataWizard — an agent that runs data-science tasks (load, summarize, model) over CSVs through natural language. |
| [TextToChartVisualizationAgent](TextToChartVisualizationAgent/) | Ask questions about a CSV in plain English and get answers plus generated charts, via a pandas dataframe agent. |
| [LangGraphStatefulWorkflows](LangGraphStatefulWorkflows/) | Stateful, graph-based AI workflows with LangGraph (auth, Q&A, and a cyclical counter). |
| [ReflectionAgentLangGraph](ReflectionAgentLangGraph/) | A self-improving reflection agent that drafts, critiques its own output, and rewrites it over several passes. |
| [AutomateEventPlanning](AutomateEventPlanning/) | crewAI multi-agent event planning: venue, logistics, and marketing agents. |
| [TailorJobApplicationsCrew](TailorJobApplicationsCrew/) | crewAI crew that tailors a resume to a job posting and preps interview talking points. |
| [ResearchAndWriteArticle](ResearchAndWriteArticle/) | crewAI planner → writer → editor crew that researches a topic and writes an article. |
| [MultiAgentFinancialAnalysis](MultiAgentFinancialAnalysis/) | Hierarchical crewAI system for stock analysis, strategy, execution, and risk. |
| [MultiAgentCustomerSupport](MultiAgentCustomerSupport/) | crewAI support + quality-assurance agents that answer and review customer inquiries. |
| [CustomerOutreachTools](CustomerOutreachTools/) | crewAI outreach crew showing built-in and custom tools (search + sentiment analysis). |
| [WeatherAgentFromScratch](WeatherAgentFromScratch/) | AI agents built from scratch in pure Python: a weather agent and a PDF-RAG chatbot. |

> The agent notebooks call LLMs through [Groq](https://console.groq.com/). Create a `.env` file
> (at the repo root or a parent folder) with `GROQ_API_KEY=...` — it is loaded automatically via
> `python-dotenv`. Some crewAI projects also need `SERPER_API_KEY` (web search), and the weather
> project needs `OPENWEATHER_API_KEY`. See each project's README for details.

---

## Deep Learning & Computer Vision

| Project | Description |
|---------|-------------|
| [AircraftDamageClassificationCaptioning](AircraftDamageClassificationCaptioning/) | Transfer learning (VGG16) to classify aircraft damage, plus BLIP image captioning. |
| [AnimeImageClassificationCNN](AnimeImageClassificationCNN/) | A custom PyTorch CNN for anime image classification. |
| [FashionMNISTClassification](FashionMNISTClassification/) | CNN classifier for Fashion-MNIST in PyTorch. |
| [WasteProductClassificationTransferLearning](WasteProductClassificationTransferLearning/) | Waste-product image classification with a fine-tuned VGG16. |
| [DataLoadingAugmentationKeras](DataLoadingAugmentationKeras/) | Efficient Keras image pipelines: custom generators vs. `image_dataset_from_directory`. |
| [DataLoadingAugmentationPyTorch](DataLoadingAugmentationPyTorch/) | PyTorch data pipelines with custom `Dataset`, `ImageFolder`, and `DataLoader`. |
| [MemoryVsGeneratorDataLoading](MemoryVsGeneratorDataLoading/) | Memory-based vs. generator-based data loading for satellite image classification. |

---

## Machine Learning

| Project | Description |
|---------|-------------|
| [AUSWeather](AUSWeather/) | Rain prediction on the Australian weather dataset (logistic regression, random forest). |
| [TitanicSurvivalPrediction](TitanicSurvivalPrediction/) | Titanic survival prediction with ensemble classifiers and pipeline tuning. |
| [LeagueOfLegendsMatchPredictor](LeagueOfLegendsMatchPredictor/) | Match-outcome prediction from game stats with a PyTorch neural network. |

---

## Getting started

Each project is independent and is meant to run in its **own virtual environment**, so their
dependencies never collide. Every project's `README.md` has the exact commands, but the pattern is:

```bash
cd <ProjectFolder>
python3 -m venv .venv
source .venv/bin/activate            # Windows: .venv\Scripts\activate
pip install --upgrade pip
pip install <that project's dependencies> jupyter ipykernel
python -m ipykernel install --user --name <ProjectFolder> --display-name "Python (<ProjectFolder>)"
jupyter notebook "<ProjectFolder>.ipynb"      # then pick the matching kernel
```

> Prefer a per-project venv over base Anaconda — the crewAI projects in particular can break
> Anaconda's `protobuf` if installed into the base environment.

**API keys.** The LLM/agent projects read keys from a `.env` file (this repo's root works for all of
them, since it's discovered automatically). Copy [`.env.example`](.env.example) to `.env` and fill in
what you need: `GROQ_API_KEY` (all agent projects), `SERPER_API_KEY` (crewAI web-search projects),
`OPENWEATHER_API_KEY` (Weather project). `.env` is git-ignored — never commit it.
