# AI Agents: Principles, Capabilities, and Challenges

## Introduction

AI Agents represent a significant evolution in artificial intelligence systems. Unlike traditional AI systems that execute specific instructions provided by humans (one command, one action), AI Agents can independently determine the actions needed to achieve a given goal. They're designed to be autonomous and goal-oriented, with the ability to formulate their own plans, adapt to unforeseen circumstances, and interact with their environment in complex ways.

As noted in the source materials, "every person has a different AI Agent in their mind," so the definitions and concepts presented here may differ from other sources.

## Key Components and Operational Process

The core operational loop of an AI Agent involves a continuous cycle of:

1. **Goal**: A high-level objective assigned to the agent by the user
2. **Observation**: The current state of the environment as perceived by the agent
3. **Action**: The specific step the agent decides to execute based on its analysis
4. **Feedback**: Information from the environment indicating the impact of the action

This cycle repeats until the goal is achieved, with the agent constantly adjusting its strategy based on new observations and feedback.

## Evolution from Traditional AI to LLM-Powered Agents

There has been a significant shift from traditional AI agents with pre-defined behaviors (like AlphaGo's limited moves) to LLM-driven agents with "near-infinite possibilities" because they "can use tools."

Historically, AI agents were built using Reinforcement Learning (RL), where:
- A goal is converted into a reward
- The agent is trained to maximize this reward
- The agent learns through trial and error

With the advent of Large Language Models (LLMs), AI agents can now:
- Use pre-trained LLMs as their "brain"
- Leverage the LLM's existing knowledge and reasoning capabilities
- Adapt through instructions rather than retraining
- Use tools to extend their capabilities

## Key Capabilities of AI Agents

### Learning from Experience

AI Agents can adjust their behavior based on experience and feedback:

- **Direct Understanding**: Instead of reward-based adjustment, modern LLM AI Agents can directly read and understand errors (like compile errors) and modify their approach accordingly
- **Memory Management**: Agents need effective memory systems:
  - **Read Module**: Retrieves relevant past experiences (similar to RAG)
  - **Write Module**: Determines what information should be stored in long-term memory
  - **Reflection Module**: Re-evaluates stored information to create new insights and connections

### Tool Use

LLM agents can significantly extend their capabilities by leveraging external tools:

- **Types of Tools**:
  - Search engines
  - Code execution environments
  - Other AI models with specialized skills
  - APIs for specific functions (e.g., weather information)
  
- **Function Calling**: Tool use is essentially "calling these functions"
  - The agent doesn't need to understand how the tool works internally
  - It only needs to know the input/output format and how to call the tool

- **Tool Selection**: When many tools are available, agents need:
  - Memory to store tool descriptions
  - A selection mechanism to choose appropriate tools for the current task

- **Self-Building Tools**: Advanced agents can even "create their own tools" by writing programs/functions

### Planning

Effective AI Agents can plan their actions to achieve goals:

- **Plan Generation**: Agents should explicitly generate plans based on their initial observation and desired goal
- **Adaptability**: "Plans are meant to be changed" - agents must be flexible and adapt when faced with unexpected events
- **Re-planning**: The agent must decide whether to modify its plan based on new observations
- **World Models**: 
  - Internal simulations of how the environment might respond to actions
  - Allows the agent to explore different strategies in a "dream state" or "internal small theatre"
  - Similar to tree search algorithms in traditional AI
  - Helps avoid costly or irreversible mistakes by simulating outcomes first

## Challenges and Limitations

Despite their capabilities, AI Agents face several challenges:

### Judgment and Information Processing

- **Limited Judgment**: LLMs may blindly follow instructions from tools, even if the results are nonsensical
- **Information Reconciliation**: Agents must reconcile their internal knowledge with external information
- **Belief Strength**: The LLM may dismiss external knowledge if its previous beliefs are too strong
- **Source Bias**: AI agents may trust AI-generated information more than human-generated content

### Planning and Execution Limitations

- **Real-World Complexity**: Agents struggle with scenarios requiring constant plan revision
- **Irreversible Actions**: Some environments don't allow for trial and error
- **Computational Cost**: Path searching and simulation can have enormous computational requirements
- **Redundancy**: An agent can waste resources "doing the same steps as other people"
- **Overthinking**: Too much internal simulation can lead to "thinking giants and dwarves in action"

## Applications and Future Directions

As AI Agents continue to evolve, they have potential applications across numerous domains:
- Automated programming and debugging
- Personal assistants with greater autonomy
- Research assistants that can "propose hypotheses, design experiments, conduct experiments, and analyze results"
- Complex problem-solving in environments where goals are clear but paths are not

## Conclusion

AI Agents represent a significant step toward more autonomous and capable artificial intelligence systems. By combining the reasoning capabilities of LLMs with tool use, planning, and learning from experience, these agents can tackle complex tasks with less human intervention. However, challenges remain in areas of judgment, information reconciliation, and computational efficiency.

---

*Note: This content is synthesized from materials powered by Large Language Models*

**Source Video**: [Hung-yi Lee: 生成式AI時代下的機器學習(2025)】第二講：一堂課搞懂 AI Agent 的原理 (AI如何透過經驗調整行為、使用工具和做計劃)](https://www.youtube.com/watch?v=M2Yg1kwPpts)