## Agentic Travel Planner using OpenAI
## Christopher Phillips
## August 7, 2025
## For Udacity Prompting for Effective LLM Reasoning and Planning

In this project, we build an agentic travel assistant system, the "AgentsVille Trip Planner"

### Requirements:
python 3.13.5

packages:
pydantic 2.11.7
pandas 2.3.1
openai 1.97.1
numexpr 2.11.0
json-repair 0.48.0

## The Scenario: Your Adventure in AgentsVille Awaits!

Imagine a traveler, eager to explore the unique (though entirely fictional) city of AgentsVille. They have a set of preferences – perhaps a long weekend focused on art galleries and technology meetups, or a week-long dive into cultural experiences and street food, all within a specific budget. **They turn to your AI-powered Trip Planner for help.**

Your challenge is to build an AI system that can:

1. **Understand and Interpret:** Take into account user preferences and constraints.

2. **Plan Comprehensively:** Generate a detailed, day-by-day itinerary that is not just a list of activities, but a coherent plan tailored to the individual travelers.

3. **Evaluate and Enhance:** Refine the itinerary by intelligently using a set of tools to evaluate the plan, fetch new information, and refine the schedule.

This isn't just about getting an LLM to output text; it's about designing a system that reasons, plans, and interacts with "external" information sources to provide a truly helpful trip planning experience.

### Project Description: Building Your AI Travel Assistant

Your "AgentsVille Trip Planner" will be a Jupyter Notebook application that orchestrates interactions with a Large Language Model (LLM) to perform two main functions:

1. **The Expert Planner (Initial Itinerary Generation):**
* **Your Task:** Based on a set of user-defined travel preferences (destination, duration, interests, budget), you will prompt the AI to act as an expert travel planner.

* **The Outcome:** The AI must generate a detailed, day-by-day travel itinerary for AgentsVille. This itinerary needs to be a structured JSON object that conforms to a predefined Pydantic model. This stage will heavily rely on your ability to craft prompts that elicit complex, structured output, guiding the LLM through a planning process.

2. **The Resourceful Assistant (Itinerary Enhancement with a Tool-Using ReAct Agent):**
* **Your Task:** Once an initial itinerary is generated, the user might have follow-up questions or request modifications. Additionally, we may have other requirements to satisfy before finalizing the itinerary. You will design an "AI Travel Assistant".

* **The Outcome:** This agent will analyze the user's request in the context of the current itinerary. It will then decide if any of its available "tools" — like calling the simulated activities API tool — can assist.

    * If a tool is needed, the agent will **THINK** about its plan and **ACT** by generating a structured request for the tool.

    * Your Python code will simulate the tool's execution and provide the result back to the agent as an **OBSERVATION.**

    * The agent will then use this observation to continue its reasoning or formulate a final, helpful answer to the user.