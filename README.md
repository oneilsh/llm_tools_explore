## Langchain/langflow test

[Langflow]() is a GUI for experiments with langchain; `langflow_monarch_wrapper.json` can be imported to it (and langchain) and implements an OpenAPI agent toolkit, ostensibly mimicking ChatGPT plugins. The corresponding `openapi.json` is the JSON spec and assumes the [oai-monarch-plugin](https://github.com/monarch-initiative/oai-monarch-plugin) is running on localhost port 3434.

To try it, load it into the langflow UI and open the `openapi.json` and enter your OpenAI key. 

Altnernatively it can be run via python (not tested, so I'm not sure where the JSON spec and API key are provided):

```
from langflow import load_flow_from_json

flow = load_flow_from_json("langflow_monarch_wrapper.json")
# Now you can use it like any chain
flow("What genes are involved in Marfan's syndrome?")
```

## Basic tool using agent

The `chat_thought_agent.ipynb` notebook contains experiments allowing gpt-3.5/4 to call tools as a set of pre-determined safe python functions. TODO: figure out how to use poetry with jupyter notebooks for dep management.