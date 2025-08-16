# VAR-Officiating: AI-Agents-Debate-using-Crewai

This project explores the use of AI agents to simulate structured debates on real-world sports governance issues. It leverages three AI agents - OpenAI GPT-4o, Anthropic Claude 3.5-sonnet, and DeepSeek R1 - to debate the motion:
________________________________________
"Should VAR officials be neutral organizations or individuals instead of being part of the referee team in the English Premier League?"
________________________________________

🤖 Agent Roles
```
•	OpenAI GPT-4o (Proposer): Acts as a passionate football fan with deep knowledge of the game, arguing FOR neutral VAR officials
•	Anthropic Claude 3.5-sonnet (Opposer): Embodies an experienced pundit with extensive football expertise, arguing AGAINST neutral VAR officials
•	DeepSeek R1 (Judge): Evaluates the debate and determines which side presents the strongest arguments
```
🎯 Project Overview

Using CrewAI, these agents engage in a multi-turn debate, presenting arguments, counterarguments, and nuanced perspectives. The goal is to examine how AI can model complex discussions, weigh pros and cons, and generate insightful reasoning on controversial topics in sports officiating.

🏆 Key Debate Points
Arguments FOR Neutral VAR Officials:
```
Eliminates conflicts of interest and potential bias
Enhances transparency and trust in decision-making
Improves accountability through specialization
Reduces pressure on on-field referees
Aligns with best practices in other sports
```

Arguments AGAINST Neutral VAR Officials:
```
Ensures seamless communication within referee teams
Maintains contextual awareness of match dynamics
Fosters unified responsibility and accountability
Preserves referee authority and game flow
Leverages Premier League-specific expertise
```
📁 Repository Structure

```
var_officiating/
├── config/
│   ├── agents.yaml              # Agent configurations (roles, goals, backstories, models)
│   └── tasks.yaml               # Task definitions for debate sequence
├── output/                      # Generated debate transcripts and analysis
├── crew.py                      # Agent and task decorators, Crew configuration
├── main.py                      # Entry point with debate motion and execution logic
├── pyproject.toml              # Project dependencies and configuration (uv)
├── .env.example                # Environment variables template
├── .env                        # Your API keys (not tracked in git)
└── README.md                   # This file
```

#### Key Files Explained:

• config/agents.yaml: Defines the three AI agents (Proposer, Opposer, Judge) with their specific models and characteristics
• config/tasks.yaml: Sequential task definitions for the debate flow
• crew.py: Python decorators and crew configuration using Process.Sequential
• main.py: Main execution file containing the VAR debate motion
• output/: Directory for debate transcripts and judge decisions



#### Prerequisites

Python 3.11+
uv (Python package manager)
CrewAI CLI
API keys for OpenAI, Anthropic, and DeepSeek
Recommended: Cursor AI code editor for enhanced development experience

#### Project Setup
This project was created using the CrewAI CLI framework. Here's how to replicate the setup:

1. Create the CrewAI Project
```bash
crewai create crew var_officiating
cd var_officiating
```
2. Install Dependencies
```bash
uv sync
```
3. Configure Environment Variables

Add your API keys to .env:

```bash
OPENAI_API_KEY=your_openai_key
ANTHROPIC_API_KEY=your_anthropic_key
DEEPSEEK_API_KEY=your_deepseek_key
```

### Configuration Files Modified

agents.yaml

Configured three agents with specific roles, goals, backstories, and models:
```
• Proposer (OpenAI GPT-4o): Passionate football fan arguing FOR neutral VAR officials
• Opposer (Anthropic Claude 3.5-sonnet): Experienced pundit arguing AGAINST neutral VAR officials
• Judge (DeepSeek R1): Impartial evaluator determining the stronger argument
```
tasks.yaml

Defined sequential tasks for each agent:
```
• Propose: Present case for neutral VAR officials
• Opposer: Present case against neutral VAR officials
• Decide : Evaluate both arguments and decide winner
```

crew.py

```
• Created agent and task decorators for each role
• Modified Crew configuration to use Process.Sequential instead of hierarchical
• Ensured proper sequential flow: Proposer → Opposer → Judge
```

main.py

```
Set the debate motion as input variable
Streamlined run, train, and test functions to focus on the VAR debate topic
Removed unnecessary input parameters
```

Running the Debate

```bash
crewai run
```

📊 Results Analysis & Judge's Decision

Final Verdict: NEUTRAL VAR OFFICIALS WIN

The DeepSeek R1 judge ruled in favor of having neutral organizations or individuals serve as VAR officials, separate from the referee team. Here's the complete decision breakdown:
Judge's Key Reasoning:
```
• Eliminates Conflicts of Interest: Neutral VAR officials provide objective review without subconscious loyalty or pressure that referee team members might experience
• Enhances Transparency and Trust: Independent viewpoint boosts credibility with fans, clubs, and players who are more likely to trust decisions from unconnected parties
• Improves Specialization: Dedicated experts focused solely on video analysis tend to yield higher accuracy and consistent rule application
• Reduces Referee Pressure: On-field referees can focus entirely on game management without VAR communication concerns
• Aligns with Best Practices: Successful implementation in tennis, rugby, and cricket provides evidence-based support
```
Acknowledged Opposition Strengths:

The judge recognized valid counterarguments about:
```
• Seamless communication within referee teams
• Contextual awareness of match dynamics
• Unified responsibility and authority
• Premier League-specific expertise requirements
```
Critical Decision Factor:

"The proposer's arguments confront broader systemic risks to fairness and trust that are foundational to the acceptability of VAR decisions... whereas perceived or real conflicts of interest are more difficult to mitigate intrinsically."

Why This Matters:

The judge prioritized foundational integrity over operational efficiency, determining that communication and contextual issues can be addressed through training and protocols, while bias concerns are inherently harder to resolve within integrated referee teams.
