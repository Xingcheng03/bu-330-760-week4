# Homework 3: Math Agent with Tool Use

This project contains a ReAct math agent built with PydanticAI. The agent uses a calculator tool for arithmetic and a product lookup tool for questions that require catalog prices.

## Video Walkthrough

Add your video link here before submitting:

- Video link: `https://youtu.be/LPh8zWDTVsw`

## Setup

1. Install [uv](https://docs.astral.sh/uv/getting-started/installation/) if you do not already have it.
2. Copy `.env.example` to `.env`.
3. Add your API key to `.env`.

For Google AI Studio, set:

```bash
GOOGLE_API_KEY=your-key-here
```

If you want to use another provider, update the `MODEL` value in `agent.py` and set the matching API key in `.env`.

## Run

```bash
uv run agent.py
```

The agent reads the questions from `math_questions.md` and prints the full ReAct trace for each question, including tool calls and final answers.

## Files

- `agent.py` - main agent and tool definitions
- `calculator.py` - calculator tool
- `products.json` - product catalog
- `math_questions.md` - assignment questions
- `.env.example` - environment variable template
- `.gitignore` - prevents committing secrets

## What I Implemented

I implemented the `product_lookup` tool in `agent.py`. It:

- loads `products.json`
- returns the product price when the name exists
- returns the list of available product names when the name is not found
