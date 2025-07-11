🧠 Mnemo-AI: Modular Intelligence for Healthcare Agents

Mnemo-AI is a composable agent framework built on the Model Context Protocol (MCP), designed to orchestrate Retrieval-Augmented Generation (RAG) pipelines and intelligent workflows.
It empowers developers to build real-time, domain-specific agents with memory, logic, and persistence—ideal for healthcare applications like nurse support, patient triage, and medical data analysis.

🚀 Features

- Composable Agent Architecture: Chainable agents with persistent memory and logic.
- MCP Integration: Real-time interaction with external tools, databases, and services.
- RAG-Native Workflows: Seamless integration with vector stores and unstructured data.
- Multimodal Reasoning: Supports text, images, structured documents, and speech.
- Tool-Oriented Execution: Agents can fetch, retrieve, and operate on data from MCP-compliant services.

🏥 Healthcare Use Cases
- Nurse Support Agents: Real-time Q&A over hospital protocols and patient records.
- Medical Data Retrieval: Context-rich answers from EMRs and clinical databases.
- Voice-First Interaction: Speech-ready agents for hands-free caregiving.
- Patient Monitoring: IoT-integrated agents for vitals tracking and alerts.

📦 Installation

`bash
pip install mnemo
Or using uv:

`bash
uv add "mnemo"
`

🧪 Quickstart

`python
from mnemo.app import MnemoApp
from mnemo.agents.agent import Agent
from mnemo.workflows.llm.augmentedllmopenai import OpenAIAugmentedLLM

app = MnemoApp(name="healthcare_agent")

async def run():
    async with app.run() as session:
        nurse_bot = Agent(
            name="nurse_support",
            instruction="Assist with patient queries and hospital protocols.",
            server_names=["fetch", "filesystem"]
        )
        async with nurse_bot:
            tools = await nursebot.listtools()
            llm = await nursebot.attachllm(OpenAIAugmentedLLM)
            response = await llm.generate_str("What is the protocol for post-op care?")
            print("Response:", response)

🧩 Architecture Overview

| Component        | Description                         |
|------------------|-------------------------------------|
| MnemoApp         | Core application wrapper            |
| Agent            | Modular agent with memory and logic |
| Workflows        | RAG pipelines and LLM orchestration |
| MCP Servers      | External tool/data connectors       |

📚 Documentation & Resources

You can explore the official GitHub repository for more examples and advanced configurations: MnemoAI/mnemo on GitHub
