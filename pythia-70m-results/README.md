# D2T Evaluation Results for the Pythia Model Suite

This repository contains the complete set of experimental results for the research paper titled *"Format Sensitivity in Language Models: A Study Across Scale and Training Dynamics"*.

## 📝 Project Overview

The core objective of this research is to systematically track and analyze how language models develop the capability to process structured data during pre-training. We evaluated the Pythia suite of models on a financial Question Answering (QA) benchmark. For each question, the contextual data was presented in three distinct formats: **CSV**, **JSON**, and **Markdown**.

This data allows for the in-depth analysis of several key research questions:
1.  How does accuracy on structured data tasks evolve with model scale and training duration?
2.  How sensitive are models to the input data format, and how does this sensitivity change over time?
3.  Are there critical thresholds in model scale or training where the ability to handle structured data significantly improves?

## 📂 Data Repository Structure

The repository is organized by model size. Each directory contains the raw JSON output files from the inference experiments for a specific model.

```
.
├── pythia-70m-results/
│   ├── pythia-70m_step0.json
│   ├── pythia-70m_step1000.json
│   └── ... (results for all 154 checkpoints)
├── pythia-160m-results/
│   └── ...
├── pythia-410m-results/
│   └── ...
├── pythia-1b-results/
│   └── ...
├── pythia-1.4b-results/
│   └── ...
├── pythia-2.8b-results/
│   └── ...
└── pythia-6.9b-results/
│   └── ...
└── README.md
```

## 📊 Experimental Data Details

-   **Model Suite**: This repository contains results for the following Pythia models: `70M`, `160M`, `410M`, `1B`, `1.4B`, `2.8B`, and `6.9B`.
-   **Checkpoints**: Each model was evaluated at 154 checkpoints throughout its pre-training, from `step0` to `step143000`.
-   **Dataset Basis**: The methodology for our financial QA benchmark is inspired by the **TAT-QA (Tabular and Textual Question Answering)** dataset. We gratefully acknowledge its foundational contribution to the field.
    -   **TAT-QA Paper:** [https://arxiv.org/abs/2105.07624](https://arxiv.org/abs/2105.07624)
    -   **TAT-QA GitHub:** [https://github.com/NExTplusplus/TAT-QA](https://github.com/NExTplusplus/TAT-QA)
-   **Data File Format**: Each `.json` file within the directories has the following structure:
    ```json
    {
      "model": "pythia-1.4b",
      "checkpoint": "step1000",
      "results": [
        {
          "id": "a1b54eff...",
          "question": "What is the average revenue...?",
          "gold_answer": ["5623"],
          "markdown_table_response": "The model's generated answer for the Markdown format.",
          "csv_string_response": "The model's generated answer for the CSV format.",
          "json_rows_response": "The model's generated answer for the JSON format."
        }
      ]
    }
    
    
---