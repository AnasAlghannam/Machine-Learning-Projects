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
| [ReflexionAgentExternalKnowledge](ReflexionAgentExternalKnowledge/) | A Reflexion research agent that critiques its own answer, searches the web for evidence, and revises with real citations. |
| [ReActAgentLangGraph](ReActAgentLangGraph/) | A ReAct agent that reasons step by step and calls tools — web search, a safe calculator, and a news summarizer. |
| [AutomateEventPlanning](AutomateEventPlanning/) | crewAI multi-agent event planning: venue, logistics, and marketing agents. |
| [TailorJobApplicationsCrew](TailorJobApplicationsCrew/) | crewAI crew that tailors a resume to a job posting and preps interview talking points. |
| [ResearchAndWriteArticle](ResearchAndWriteArticle/) | crewAI planner → writer → editor crew that researches a topic and writes an article. |
| [MultiAgentFinancialAnalysis](MultiAgentFinancialAnalysis/) | Hierarchical crewAI system for stock analysis, strategy, execution, and risk. |
| [MultiAgentCustomerSupport](MultiAgentCustomerSupport/) | crewAI support + quality-assurance agents that answer and review customer inquiries. |
| [CustomerOutreachTools](CustomerOutreachTools/) | crewAI outreach crew showing built-in and custom tools (search + sentiment analysis). |
| [RestaurantDataStructuring](RestaurantDataStructuring/) | Turns unstructured restaurant write-ups into validated JSON, with an LLM repair loop for records that fail the schema. |
| [MultimodalDataProcessing](MultimodalDataProcessing/) | Captions food and review images with a vision model and folds them into existing JSON records. |
| [MultimodalVectorIndex](MultimodalVectorIndex/) | Builds a searchable index over two modalities: sentence-transformer text vectors and CLIP image vectors in Chroma. |
| [SimilarityRetrievalFiltering](SimilarityRetrievalFiltering/) | Text→text, filtered, and image→image retrieval over the multimodal index. |
| [MultimodalFusionRanking](MultimodalFusionRanking/) | Blends text and image similarity into one ranked list with tunable per-modality weights. |
| [CrewAIMultiAgentBasics](CrewAIMultiAgentBasics/) | crewAI fundamentals — agents, tasks, crews and tools — building a research-to-article pipeline. |
| [CrewAIAgentVsTaskTools](CrewAIAgentVsTaskTools/) | Agent-centric vs. task-centric tool attachment, compared side by side on one FAQ chatbot. |
| [CrewAIMealGroceryPlanner](CrewAIMealGroceryPlanner/) | Four-agent meal and grocery planner returning Pydantic-typed structured output. |
| [WeatherAgentFromScratch](WeatherAgentFromScratch/) | AI agents built from scratch in pure Python: a weather agent and a PDF-RAG chatbot. |

> The agent notebooks call LLMs through [Groq](https://console.groq.com/). Create a `.env` file
> (at the repo root or a parent folder) with `GROQ_API_KEY=...` — it is loaded automatically via
> `python-dotenv`. Some crewAI projects also need `SERPER_API_KEY` (web search), and the weather
> project needs `OPENWEATHER_API_KEY`. See each project's README for details.

### Switching model provider

Every project reads its key from `.env`. Two providers are supported, and both speak the OpenAI
protocol, so switching is a matter of which key is present:

| Set this | Effect |
|---|---|
| `GROQ_API_KEY` | Default. Fast and free, but the free tier has a tight rate limit. |
| `OPENROUTER_API_KEY` | Takes priority when set. Fronts many models behind one key — useful when Groq's quota runs out, or when you need a model Groq does not host (vision models, for instance). |

Set `OPENROUTER_MODEL` to pick the model, e.g. `meta-llama/llama-3.3-70b-instruct`. Projects with a
central config module switch automatically; the rest name their model inline and take a one-line
edit.

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
