# 📊 Sales Data Analyst AI Agent (n8n)

An AI-powered **Sales Data Analyst Agent** built using **n8n**, **LangChain**, and **OpenRouter (NVIDIA Nemotron-3 Nano Model)**. This automation enables natural-language sales data analysis directly from **Google Sheets**, without manual querying or calculations.

---

## 🚀 Overview

This agent listens to user chat messages, understands sales-related analytical questions, fetches the required data from Google Sheets, performs accurate calculations using tools, and returns concise, structured insights.

It is designed for:

* Sales teams
* Business analysts
* Founders and managers
* No-code / low-code automation workflows

---

## 🧠 Key Capabilities

* 💬 **Chat-based data analysis**
* 📈 **Sales metrics computation** (totals, averages, trends)
* 🧮 **Tool-based calculations (no hallucination)**
* 📄 **Live Google Sheets integration**
* 🧠 **Short-term memory for context-aware conversations**
* 🔒 **Strict non-fabrication & read-only data access**

---

## 🏗️ Architecture

**Core Components:**

1. **Chat Trigger**
   Entry point for user messages.

2. **AI Agent (LangChain)**
   Controls reasoning, tool usage, and response formatting.

3. **OpenRouter LLM**

   * Model: `nvidia/nemotron-3-nano-30b-a3b`
   * Optimized for structured reasoning and low latency.

4. **Google Sheets Tool (`getData`)**
   Read-only access to sales data.

5. **Memory Buffer**
   Maintains recent chat context (last 10 messages).

---

## 🧩 System Prompt Design

The agent operates under a strict system message that enforces:

### Role

* Dedicated **Sales Data Analyst** inside n8n

### Tools

* `getData` → Fetch only required spreadsheet data
* `calculator` → Perform **all** numerical calculations (optional)

### Instructions

* Understand request before acting
* Fetch data only when necessary
* Never assume spreadsheet structure
* Present results clearly and concisely

### Restrictions

* ❌ No data fabrication
* ❌ No guessing ranges or values
* ❌ No spreadsheet edits
* ❌ No opinions or speculation

---

## 📂 Google Sheets Setup

* Connect your Google Sheets account using OAuth
* Provide the **Spreadsheet URL**
* Select the appropriate **Sheet tab**
* Ensure the data is structured (headers recommended)

> ⚠️ The agent will ask for clarification if required information is missing.

---

## 💬 Example Use Cases

* "What is the total sales for last month?"
* "Calculate average daily revenue"
* "Which product has the highest sales?"
* "Show me a summary of this sheet"

---

## 🔧 Technologies Used

* **n8n** – Workflow automation
* **LangChain** – AI agent orchestration
* **OpenRouter** – LLM gateway
* **NVIDIA Nemotron-3 Nano** – AI model
* **Google Sheets API** – Data source

---

## 🛡️ Data Safety & Accuracy

* Read-only access to spreadsheets
* Tool-enforced calculations
* Zero hallucination policy
* Explicit clarification on missing inputs

---

## 📦 Importing the Workflow

1. Copy the workflow JSON
2. In n8n, go to **Import Workflow**
3. Paste JSON and save
4. Configure credentials:

   * OpenRouter API
   * Google Sheets OAuth

---

## 🌟 Future Enhancements

* Multi-sheet support
* Chart generation
* CSV export
* CRM integrations
* Scheduled sales reports

---

## 📄 License

MIT License

---

## 🙌 Acknowledgements

Built with ❤️ using n8n and NVIDIA Nemotron models.

---

**Author:** *apache2op*

## 🔄 Quick Start Checklist

Use this checklist when importing an n8n agent workflow for the first time:

1. Make sure your n8n instance is running.
2. Open the workflow JSON file from this repository.
3. Import the JSON into n8n using the workflow import option.
4. Review all AI Agent and tool nodes before running the workflow.
5. Configure the required credentials for services such as Google Sheets or LLM providers.
6. Replace any example configuration with your own values.
7. Test the workflow manually before activating it.
8. Activate the workflow only after confirming that all nodes work correctly.

### Security Checklist

- Never commit API keys, passwords, access tokens, or other secrets.
- Use n8n credentials or environment variables instead of hardcoding secrets.
- Review imported workflows before executing them.
- Use test data when evaluating a workflow for the first time.

This checklist provides a safer and more consistent setup process for users who are new to importing n8n AI-agent workflows.