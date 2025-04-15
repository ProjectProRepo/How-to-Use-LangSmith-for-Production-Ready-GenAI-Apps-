# Trace and Tune Hugging Face Models in LangChain with LangSmith
A simple notebook tutorial to trace and debug LLM workflows with open-source models

---

## Overview

This tutorial walks you through building a minimal LangChain application powered by Hugging Face Transformers and traced with LangSmith. You'll learn how to:

- Set up and authenticate LangSmith and Hugging Face
- Use `@traceable` to monitor a function call
- Create a LangChain `LLMChain` with a Hugging Face model
- View trace results in your LangSmith dashboard

It’s a great starting point for prompt debugging, model experimentation, and building LLM-powered tools that you can observe and optimize in real time.

---

## Prerequisites

Before you begin, make sure you have:

- A LangSmith account
- A Hugging Face account and access token (some models require this)
- Python 3.9+ with pip installed
- Basic familiarity with Python and notebooks

---

## Step 0: LangSmith Setup

First, sign up at [smith.langchain.com](https://smith.langchain.com). Once logged in:

- Click your avatar in the top right and go to Account Settings
- Under the API Keys tab, create a new key (e.g., `notebook-demo`)
- Copy the key — you'll need it in your environment variables

---

## Step 1: Install Dependencies

Install LangChain, LangSmith, Hugging Face Transformers, Accelerate, and LangChain Community integrations. You can do this in a notebook or terminal.

---

## Step 2: Set Environment Variables

Set your LangSmith API key, project name, and enable tracing in your environment using `os.environ`. This lets LangSmith log and visualize your LangChain execution flow.

---

## Step 3: Authenticate Hugging Face

Use `notebook_login()` to sign into Hugging Face. This ensures you can load models, including those behind access gates like Mistral or Falcon.

---

## Step 4: Load a Hugging Face Model

Choose a lightweight model like `google/flan-t5-base` or use a more powerful one like `mistralai/Mistral-7B-Instruct-v0.1` if you have GPU access. Set generation parameters such as `temperature` and `top_k` to control the creativity of your outputs.

---

## Step 5: Create a Prompt and LLMChain

Build a prompt template and initialize a LangChain `LLMChain` using the Hugging Face pipeline. This chain takes a product description and returns a creative company name.

---

## Step 6: Add a Traceable Function

Wrap the chain in a Python function and decorate it with `@traceable`. This allows LangSmith to track each call, input, and output automatically — perfect for debugging and visualization.

---

## Step 7: Run and Observe

Call the function with a sample input (e.g., "eco-friendly smart lamps") and view the generated name. Then, visit your LangSmith dashboard to explore:

- Input/output logs
- Prompt history
- Model metadata
- Token usage and execution time

---

## Example Output

Input: eco-friendly smart lamps  
Output: Luminosity

If you're getting the same name repeatedly, try increasing the model's randomness using parameters like `temperature`, `top_p`, and `top_k`.

---

## Want the Full Code?

Read the full article for the code and a downloadable iPython notebook to try it in your own environment.

---

## Bonus Ideas

- Wrap it in a Gradio or Streamlit UI for interactive naming
- Batch generate names from a CSV file
- Evaluate outputs using LangSmith's feedback tools

---

Star this repo if you found it helpful!
