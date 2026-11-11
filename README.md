# LangChain Essentials

My finished notebooks from the [LangChain Essentials (Python)](https://academy.langchain.com/courses/langchain-essentials-python) course on LangChain Academy.

I worked through all 9 Python lessons and committed them with their outputs, so you can read the results right here on GitHub without running anything. The lesson material and starter code come from LangChain's [lca-langchainV1-essentials](https://github.com/langchain-ai/lca-langchainV1-essentials) repo. The runs are mine.

## What's covered

| # | Notebook | What it does |
|---|----------|--------------|
| 1 | [L1_fast_agent](python/L1_fast_agent.ipynb) | Builds a SQL agent over the Chinook music store database with `create_agent` |
| 2 | [L2_messages](python/L2_messages.ipynb) | Shows how messages move between the model, tools and the agent |
| 3 | [L3_streaming](python/L3_streaming.ipynb) | Streams tokens and agent steps so users aren't staring at a blank screen |
| 4 | [L4_tools](python/L4_tools.ipynb) | Writes custom tools with `@tool` and hands them to an agent |
| 5 | [L5_tools_with_mcp](python/L5_tools_with_mcp.ipynb) | Pulls tools from an MCP server (`mcp-server-time`) through `langchain-mcp-adapters` |
| 6 | [L6_memory](python/L6_memory.ipynb) | Keeps conversation state between calls with `InMemorySaver` |
| 7 | [L7_structuredOutput](python/L7_structuredOutput.ipynb) | Gets typed results back using `response_format` with Pydantic and `TypedDict` |
| 8 | [L8_dynamic](python/L8_dynamic.ipynb) | Rewrites the system prompt at runtime with `@dynamic_prompt` middleware |
| 9 | [L9_HITL](python/L9_HITL.ipynb) | Pauses the agent for human approval with `HumanInTheLoopMiddleware` |

The notebooks use OpenAI models (`gpt-5`, `gpt-5-mini` and `gpt-5-nano`).

## Repo layout

- `python/` has the notebooks I ran.
- `python/studio/` packages the SQL agent for LangSmith Studio.
- `python_local/` is the same course set up for locally hosted models. It's an untouched copy of the original.
- `js/` is the TypeScript version of the course, also untouched.

## Running it

You'll need Python 3.11 to 3.13, [uv](https://docs.astral.sh/uv/), and an OpenAI API key. A LangSmith key is optional (it turns on tracing).

```bash
git clone https://github.com/ParthTechie/Langchain-Essentials.git
cd Langchain-Essentials/python
cp example.env .env      # then paste your OPENAI_API_KEY into .env
uv sync
uv run jupyter lab
```

Lesson 5 launches the MCP server with `uvx`, so uv has to be on your PATH.

To poke at the L1 agent in LangSmith Studio:

```bash
cp .env studio/
cd studio
uv run langgraph dev
```

[python/README.md](python/README.md) has the full setup notes, including how to get LangSmith keys.

## What I changed

- Ran every notebook end to end and kept the outputs.
- Asked the L1 SQL agent my own question: "tell me about frank harris recent purchases".
- Fixed a typo in L2 ("Altenative" to "Alternative").

## Credits

The course, lesson text, diagrams and starter code are by [LangChain](https://www.langchain.com/). The Chinook sample database comes from [lerocha/chinook-database](https://github.com/lerocha/chinook-database).

## License

MIT, see [LICENSE](LICENSE). The original course code is MIT licensed by LangChain, Inc., and I've kept that notice next to mine.
