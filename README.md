# 🤖 LangGraph Supply Chain Sentinel (Agentic Version)

> A "Smart" Supply Chain Agent that uses **Tool Calling** and **Human-in-the-Loop** to prevent shipping disasters.

## 🧠 The Architecture (Agentic)
Unlike standard linear pipelines, this agent uses the **ReAct Pattern**.
1.  **Observe:** It looks at the database first.
2.  **Think:** It decides *if* it needs to check for risks. (If the location is safe, it might skip the check).
3.  **Act:** If a risk check is needed, it calls the `check_external_risks` tool.
4.  **Pause:** If a critical risk (e.g., Typhoon) is found inside the tool, it **interrupts** execution to ask a human for help.

## 🛠️ Tech Stack
* **LangGraph:** For the cyclic `Agent <-> Tool` workflow.
* **Gemini 2.5 Flash:** The brain that decides which tools to call.
* **FAISS:** Vector database for retrieving real-time news.
* **Human-in-the-Loop:** Safety interrupts before critical actions.

## 🧩 The Workflow
`Database Node` → `Gemini Agent` ⇄ `Risk Tool (with Interrupt)`

## 🚀 How to Run
1.  Clone this repository.
2.  Install dependencies:
    ```bash
    pip install langgraph langchain-google-genai langchain-community faiss-cpu pandas
    ```
3.  Open `supply_chain_sentinel_agentic.ipynb`.
4.  Enter your Google API Key when prompted.
5.  Watch the Agent "think" and decide to call the risk tool!
---
**Created By Ketan Dilip Gaikwad**
