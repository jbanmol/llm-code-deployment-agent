---
title: LLM Code Deployment Agent
emoji: rocket
colorFrom: blue
colorTo: green
sdk: docker
app_file: main.py
pinned: false
---

# LLM Code Deployment Agent

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-Agent_Service-009688?logo=fastapi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Deployment-2496ED?logo=docker&logoColor=white)
![GitHub Pages](https://img.shields.io/badge/GitHub_Pages-Automation-181717?logo=github&logoColor=white)
![LLM Agents](https://img.shields.io/badge/LLM_Agents-Code_Generation-7C3AED)

FastAPI service that receives natural-language app-building tasks, uses an LLM to generate or modify code, and deploys generated outputs through GitHub Pages.

## What This Demonstrates

- Agentic workflow orchestration around an LLM
- FastAPI request handling and validation with Pydantic
- GitHub repository creation and deployment automation
- Secret-based endpoint authentication
- Dockerized deployment for Hugging Face Spaces
- Multi-step task handling with status endpoints and error reporting

## System Flow

```text
Incoming task request
  -> authentication and validation
  -> prompt/task preparation
  -> LLM code generation
  -> repository update
  -> GitHub Pages deployment
  -> status response
```

## Endpoints

| Endpoint | Purpose |
|---|---|
| `GET /` | Health check |
| `GET /status` | Last task status |
| `POST /ready` | Main task ingestion endpoint |
| `GET /docs` | Swagger UI |

## Local Development

```bash
git clone https://github.com/jbanmol/llm-code-deployment-agent.git
cd llm-code-deployment-agent
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload --host 0.0.0.0 --port 7860
```

Required environment variables:

```env
OPENAI_API_KEY=your_openai_api_key
GITHUB_TOKEN=your_github_personal_access_token
STUDENT_SECRET=a_secure_secret_string
GITHUB_USERNAME=your_github_username
OPENAI_API_BASE=https://aipipe.org/openrouter/v1
```

## Tech Stack

Python, FastAPI, Pydantic, Docker, OpenAI-compatible APIs, GitHub API, Hugging Face Spaces.

## Professional Focus

This repository shows applied AI engineering: not just calling a model, but wrapping it in authentication, deployment, validation, and operational control.
