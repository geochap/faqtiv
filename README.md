# FAQtiv
FAQtiv is a project that aims to improve reliability of interactions between users and their conversational AIs as they access enterprise systems and data. 
The core ideas that drive this project are:

- Code generation is a powerful mechansim for getting LLMs to perform actions that require multiple coordinated steps, and that by providing a set of domain specific functions for them to target, we greatly increase the reliability of the generated code by constraining the LLMs to a particular limited view of the world.
  
- Specialization and layering help us build bigger and better things. At one level this means intelligent agents can provide specialized knowledge or capabilities to general purpose conversational AIs. At another this means the agents themselves can be further broken into into a layer of access functions and a layer of LLM generated code that performs tasks using those functions. This allows for a natural separation of concerns where a developer builds the access functions and a subject matter expert trains the agent using natural language to perform tasks.

The project is made up of several parts:

- [FAQtiv Agent Toolkit](https://github.com/geochap/faqtiv-agent-toolkit) -- An open source command line tool for creating agents

- [FAQtiv Desktop](https://github.com/geochap/faqtiv-desktop) -- An open source Electron based playground for developing and interacting with FAQtiv agents

