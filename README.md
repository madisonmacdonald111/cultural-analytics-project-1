# INFO 230 Mini-Project 1: Human vs. AI Text 
**A Cultural Analytics Approach | Spring 2026**

Central Research Question: Can we tell human writing from machine-generated text, and if so, what does that difference actually look like? This project applies a full cultural analytics pipeline to the [Human vs. LLM Text Corpus](https://www.kaggle.com/datasets/starblasters8/human-vs-llm-text-corpus/data) from Kaggle to find out. 

For the full analysis, results, discussion, and all interpretations see the entire workflow in ```**code/project-workflow.ipynb**```. 

---
## Dataset 

**Source:** [Human vs. LLM Text Corpus](https://www.kaggle.com/datasets/starblasters8/human-vs-llm-text-corpus/data) -- Kaggle
**Full size:** 788,922 texts (~347k human, ~441k AI from 62 different LLMs)  
**Used in this project:** a reproducible 10,000-row sample (`RANDOM_SEED = 230`)

*The full `data.csv` is too large to push to the repo. Only the 10k sample (`ai_human_sample_10k.csv`) is included in `data/`.*

| File | Description |
|---|---|
| ```data.csv``` | Full corpus — download from Kaggle link above |
| ```ai_human_sample_10k.csv``` | The 10k sample used for all analysis |
| ```distribution.csv``` | Pre-computed stats across all 788k documents by source |
| ```prompts.csv``` | Writing prompts used to generate the texts |

---

## Repository Structure 
**A note on figures and models:** Static figures are saved to `figures/` but the interactive Plotly charts (feature importance, heatmaps) are only visible in the notebook directly (either from the repository or the github.io webpage). The saved BERTopic models (```bertopic_s1_model/```, ```bertopic_s2_model/```) are also too large to push but their successful run is visible from the notebook.

```
cultural-analytics-project-1/
├── code/
│   ├── project-workflow.ipynb      <- everything is here
|   └── project-workflow.html
├── data/
│   ├── ai_human_sample_10k.csv
│   └── chunks_s1_with_topics.csv
│   └── chunks_s2_with_topics.csv
│   └── chunks_strategy1.csv
│   └── chunks_strategy2.csv
├── figures/
│   ├── EDA_visuals.png
│   └── chunking_strategies.png
|   └── confusion_matrices.png
│   └── wordcloud.png
└── README.md
└── index.html
└── environment.yaml

```

---

## How to Run (if interested)
1. Clone the repo and download `data.csv` from the Kaggle link above into `data/`
2. Set up the environment: `conda env create -f environment.yaml` then `conda activate cultural_analytics`
3. Run `code/project-workflow.ipynb` top to bottom

All random operations use `RANDOM_SEED = 230` so results are fully reproducible. The pre-chunked CSVs are included so you can skip the slow fitting steps and jump straight to Steps 4–6 if needed.

--- 

## References 

*Course Content: visualizations and methods draw on various course notebooks including: ```explore_grimm_chunks.ipynb```, ```holmes_ner_v02.ipynb```*

Blei, D. M., Ng, A. Y., & Jordan, M. I. (2003). Latent Dirichlet Allocation. Journal of Machine Learning Research, 3, 993–1022. https://www.jmlr.org/papers/v3/blei03a.html

Grootendorst, M. (2022). BERTopic: Neural topic modeling with a class-based TF-IDF procedure. arXiv preprint arXiv:2203.05794. https://arxiv.org/abs/2203.05794

Hastie, T., Tibshirani, R., & Friedman, J. (2009). The Elements of Statistical Learning (2nd ed.). Springer. https://hastie.su.domains/ElemStatLearn/

Manning, C. D., Raghavan, P., & Schütze, H. (2008). Introduction to Information Retrieval. Cambridge University Press. https://nlp.stanford.edu/IR-book/

**The Kaggle Dataset:** 
Zachary Grinberg. (2024). Human vs. LLM Text Corpus [Dataset]. Kaggle. https://doi.org/10.34740/KAGGLE/DSV/7378735


## AI Disclosure

Claude (Anthropic) was used as an AI assistant throughout this project for help with code structure, debugging, implementation decisions, and writing feedback. All code was read through, understood, and retyped manually. All analytical decisions, interpretations, and conclusions are my own. Claude helped, but the thinking was mine.