# EduAssist AI: LLMOps for Prompt Versioning, Performance Monitoring, and Cost Optimization

## Overview

EduAssist AI is an academic question-answering system developed to demonstrate LLMOps practices for prompt engineering, performance monitoring, cost analysis, and prompt lifecycle management.

The project evaluates multiple prompt versions of an educational assistant using the OpenAI API and compares their performance based on:

- Response latency
- Token consumption
- Cost per request
- JSON response validity
- Prompt version evolution

The project also uses MLflow for:

- Experiment tracking
- Metrics logging
- Prompt Registry
- Prompt version comparison
- Production prompt promotion

### Objectives

- Build an academic assistant using a Large Language Model (LLM)
- Measure response latency
- Track token usage and cost
- Evaluate multiple prompt versions
- Implement structured JSON outputs
- Track prompt evolution using MLflow Prompt Registry
- Promote the best-performing prompt to production

---

## Repository Structure

```text
eduassist-llmops-prompt-evaluation/
│
├── notebooks/
│   └── eduassist_llmops_prompt_evaluation.ipynb
│
├── outputs/
│   ├── latency_tokens_cost.csv
│   └── prompt_evaluation_results.csv
│
├── screenshots/
│   └── *.png
│
├── .env
├── mlflow.db
├── requirements.txt
└── README.md
```

---

## Technology Stack

- Python
- OpenAI API
- Pandas
- Jupyter Notebook
- MLflow 3.x
- python-dotenv

---

## Setup

### Clone Repository

```bash
git clone https://github.com/2025ae05182/eduassist-llmops-prompt-evaluation.git

cd eduassist-llmops-prompt-evaluation
```

### Create Virtual Environment

```bash
python -m venv .venv
```

### Activate Environment

**Windows**

```bash
.venv\Scripts\activate
```

**Linux / macOS**

```bash
source .venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Configuration

Create a `.env` file in the project root directory:

```env
OPENAI_API_KEY=your_api_key
OPENAI_MODEL_NAME=gpt-4o-mini

INPUT_PRICE=0.15
OUTPUT_PRICE=0.60
```

> Pricing values can be updated based on the selected OpenAI model.

---

## Prompt Versions

### Prompt V1

**Baseline prompt**

```text
Answer the following student question clearly.
```

### Prompt V2

**Improved instructional prompt**

```text
You are an academic assistant.
Answer questions clearly and concisely.
```

### Prompt V3

**Structured JSON prompt**

```text
Return only valid JSON with:
- answer
- confidence
- key_points
```

---

## Evaluation Metrics

The following metrics are collected for every API request.

### Performance Metrics

- Latency (seconds)
- Mean latency
- Median latency
- Minimum latency
- Maximum latency
- Standard deviation

### Consumption Metrics

- Prompt Tokens
- Completion Tokens
- Total Tokens

### Cost Metrics

- Input Cost
- Output Cost
- Total Cost

### Quality Metrics

- JSON Validity Rate

---

## Results Summary

Three prompt versions were evaluated using the same set of academic questions.

### Evaluation Dimensions

- Average latency
- Token consumption
- Request cost
- JSON validity

### Prompt V3 Achieved

- Lowest latency
- Lowest request cost
- 100% JSON validity

Therefore, **Prompt V3** was selected as the production prompt.

---

## MLflow Integration

### Experiment Tracking

**Experiment Name**

```text
eduassist_llmops_assignment
```

### Metrics Logged

- avg_latency_seconds
- avg_input_tokens
- avg_output_tokens
- avg_cost_per_request
- valid_json

### Prompt Registry

#### Registered Prompt Versions

- Version 1 - Baseline Prompt
- Version 2 - Academic Assistant Prompt
- Version 3 - Structured JSON Prompt

### Production Alias

#### Production Prompt

**Version 3**

#### Selection Rationale

- Lowest cost
- Lowest latency
- Highest output consistency
- Valid structured JSON responses

---

## Detailed Results

### outputs/latency_tokens_cost.csv

Contains:

- Prompt version
- Latency
- Token usage
- Cost metrics
- Responses

### outputs/prompt_evaluation_results.csv

Contains:

- Average latency
- Average cost
- Token statistics
- JSON validity rate

---

## Running MLflow UI

Start MLflow:

```bash
mlflow ui
```

Open in browser:

```text
http://127.0.0.1:5000
```

---

## Key Learnings

- Prompt engineering significantly impacts latency and cost.
- Structured prompts improve consistency and machine readability.
- Output token reduction has a larger cost impact than prompt token growth.
- MLflow Prompt Registry provides traceability across prompt iterations.
- Production prompt promotion enables controlled prompt lifecycle management.

---

## Author

### Ravikumar N

**M.Tech Artificial Intelligence & Machine Learning**  
**BITS Pilani WILP**