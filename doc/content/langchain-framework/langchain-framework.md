# Introduction to LangChain

LangChain is an open-source Python framework for building applications powered by large language models (LLMs). It provides modular tools to create chatbots, agents, and data-augmented generation systems efficiently.

## Key Features

- **Chains**: Combine LLMs, prompts, and tools into flexible workflows.
- **Agents**: Enable dynamic decision-making and tool use.
- **Memory**: Add context retention to conversations.
- **Integrations**: Connect with OpenAI, Hugging Face, vector stores, and more.
- **Data Augmentation**: Retrieve and use external data in LLM workflows.


## Basic Usage

from langchain.llms import OpenAI
from langchain.prompts import PromptTemplate
from langchain.chains import LLMChain

llm = OpenAI(model_name="text-davinci-003")
prompt = PromptTemplate(input_variables=["topic"], template="Explain {topic} in simple terms.")
chain = LLMChain(llm=llm, prompt=prompt)

result = chain.run(topic="quantum computing")
print(result)


## Agentic Workflow Example

from langchain.agents import load_tools, initialize_agent, AgentType
from langchain.llms import OpenAI

llm = OpenAI(temperature=0)
tools = load_tools(["serpapi"], llm=llm)
agent = initialize_agent(tools, llm, agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION)

response = agent.run("What's the latest news about AI?")
print(response)

## Use Cases

* Conversational AI and chatbots
* Document Q&A
* Data extraction and summarization
* Autonomous agents
* Resources
* LangChain Documentation
* LangChain GitHub

License
LangChain is released under the MIT License.