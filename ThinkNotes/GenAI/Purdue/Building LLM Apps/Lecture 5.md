## Langchain Agents

- Agents make use of external toos to perform specific actions. They act as decision-making entities that can use external tools dynamically.
- They involve an LLM to perform a series of steps:
	- **Decide:** Based on the user input or its previous outputs, the agents decides which action to perform.
	- **Perform:** The agent performs the chosen action
	- **Observe:** The agent observes the output of the action
	- **Repeat:** The agent repeats the first three steps until it completes the task defined in the user input to the best of its abilities.