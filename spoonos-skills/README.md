# SpoonOS Development Skills

Developer enablement skills for building agents and dApps with the SpoonOS framework.

## Core Skills

| Skill | Description | Use Case |
|-------|-------------|----------|
| [Agent Development](agent-development/SKILL.md) | Build AI agents with SpoonReactMCP | Custom agents, toolchains, prompts |
| [Graph Development](graph-development/SKILL.md) | StateGraph workflow construction | Multi-step workflows, routing, parallelism |
| [ERC-8004 Standard](erc8004-standard/SKILL.md) | Trustless agent identity | On-chain registration, reputation |
| [Tool Development](tool-development/SKILL.md) | MCP tools and extensions | BaseTool, FastMCP servers |

## Application Skills

| Skill | Description | Use Case |
|-------|-------------|----------|
| [Application Templates](application-templates/SKILL.md) | Ready-to-use agent templates | Trading bots, NFT minters, DAO assistants |
| [Platform Integration](platform-integration/SKILL.md) | Deploy to messaging platforms | Telegram, Discord, REST APIs |
| [Deployment Guide](deployment-guide/SKILL.md) | Production deployment patterns | Docker, AWS, GCP, Vercel |
| [Testing Patterns](testing-patterns/SKILL.md) | Testing strategies | Unit tests, mocking, CI/CD |

## Quick Start

### Create an Agent

```python
from spoon_ai.agents import SpoonReactMCP
from spoon_ai.chat import ChatBot
from spoon_ai.tools import ToolManager

agent = SpoonReactMCP(
    name="my_agent",
    llm=ChatBot(model_name="gpt-4o"),
    tools=ToolManager([MyTool()]),
    max_steps=15
)

result = await agent.run("Your query")
```

### Build a Workflow

```python
from spoon_ai.graph import StateGraph, END

graph = StateGraph(MyState)
graph.add_node("process", process_node)
graph.set_entry_point("process")
graph.add_edge("process", END)

app = graph.compile()
```

### Create a Tool

```python
from spoon_ai.tools.base import BaseTool

class MyTool(BaseTool):
    name: str = "my_tool"
    description: str = "Tool description"

    async def execute(self, **kwargs) -> str:
        return "Result"
```

## Directory Structure

```
spoonos-skills/
├── agent-development/      # Agent patterns
├── graph-development/      # Workflow graphs
├── erc8004-standard/       # On-chain identity
├── tool-development/       # Tool creation
├── application-templates/  # Ready-to-use templates
├── platform-integration/   # Platform deployment
├── deployment-guide/       # Production deployment
├── testing-patterns/       # Testing strategies
└── README.md
```

## Prerequisites

- Python 3.12+
- SpoonOS Core (`pip install spoon-ai`)

## Related

- [Web3 Skills](../web3-skills/README.md) - Blockchain integrations
