# FAQtiv
FAQtiv is a project that aims to improve reliability of interactions between users and their conversational AIs as they access enterprise systems and data. 
The core ideas that drive this project are:

- Code generation is a powerful mechansim for getting LLMs to perform actions that require multiple coordinated steps, and that by providing a set of domain specific functions for them to target, we greatly increase the reliability of the generated code by constraining the LLMs to a particular limited view of the world.

- Specialization and layering help us build bigger and better things. At one level this means intelligent agents can provide specialized knowledge or capabilities to general purpose conversational AIs. At another this means the agents themselves can be further broken into into a layer of access functions and a layer of LLM generated code that performs tasks using those functions. This allows for a natural separation of concerns where a developer builds the access functions and a subject matter expert trains the agent using natural language to perform tasks.

- Training an agent with parameterized Frequently Asked Questions both provides a core set of trusted, known good tools for the conversational AI, and a solid base of examples for few shot learning going forward. This increases the reliability of code generation as new tasks are added by the SME but also enables more reliable on-the-fly code generation for cases where the convesational AI can't compose a response from one or more of the existing functions/tasks.

The project is made up of several parts:

- [FAQtiv Agent Toolkit](https://github.com/geochap/faqtiv-agent-toolkit) -- An open source command line tool for creating agents

- [FAQtiv Desktop](https://github.com/geochap/faqtiv-desktop) -- An open source Electron based playground for developing and interacting with FAQtiv agents

Agents are exposed as one or more function calls to the LLM. We use OpenAI Assistant API within Desktop, but the Agent Framework will generate a JSON file that describes the functions in OpenAI format for integration with any compatible chatbot/LLM. 
