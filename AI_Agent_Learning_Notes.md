# AI Agents: A Structured Learning Note

## Introduction to AI Agents

AI Agents represent an evolution in artificial intelligence systems that can autonomously work toward achieving goals with minimal human guidance. Unlike traditional AI systems that require explicit instructions for every action, AI Agents operate within a continuous cycle of observation, decision-making, and action to accomplish complex tasks.

## Definition and Core Operational Loop

### What are AI Agents?

AI Agents are systems designed to:
- Receive a goal from a user
- Observe their environment
- Determine appropriate actions
- Execute those actions
- Repeat this cycle until the goal is achieved

The fundamental difference between traditional AI systems and modern AI Agents lies in their approach to problem-solving. While traditional AI systems like AlphaGo had pre-defined behaviors with limited possibilities, LLM-powered AI Agents have "near-infinite possibilities" because they "can use tools" and adapt their behaviors based on observations.

### The Goal-Observation-Action Cycle

At the heart of every AI Agent is this operational loop:
1. **Goal setting**: The user provides a specific objective
2. **Observation**: The agent perceives its current environment
3. **Analysis**: The agent processes information and makes decisions
4. **Action**: The agent executes a chosen action
5. **New observation**: The environment changes in response
6. **Repeat**: The cycle continues until goal achievement

## Key Capabilities of AI Agents

### 1. Learning from Experience

AI Agents demonstrate sophisticated learning capabilities through:

- **Behavioral adjustment**: Modern LLM AI Agents can directly interpret feedback (like compile errors) and modify their behavior accordingly, moving beyond simple reward-based learning
  
- **RAG approach** (Retrieval-Augmented Generation): Combining retrieval of relevant past experiences with generation of new actions
  
- **Memory management**: Effective agents "only record important information" and determine what should be stored in long-term memory
  
- **Reflection**: Processing retrieved memories to create new ideas and establish connections, essentially building a knowledge graph

### 2. Tool Use

AI Agents can extend their capabilities by:

- **Leveraging external resources**: Using search engines or other specialized AI models
  
- **Function calling**: Tool use is essentially "calling these functions" to perform specific tasks
  
- **Prompt engineering**: Formatting instructions appropriately for specific tools, ensuring inputs and outputs are properly structured
  
- **Self-building tools**: Creating their own programs or functions to add to their toolkit

### 3. Planning

AI Agents demonstrate strategic thinking through:

- **Plan generation**: Creating explicit plans based on initial observations and goals
  
- **Adaptability**: Understanding that "plans are meant to be changed" when faced with unexpected events
  
- **Re-planning**: Evaluating whether to modify plans based on new observations
  
- **World models**: Simulating potential environmental changes in a "dream state" or "internal small theatre"
  
- **Balancing deliberation**: Avoiding overthinking, as models can become "thinking giants and dwarves in action"

## Challenges and Limitations

Despite their capabilities, AI Agents face several important challenges:

- **Judgment limitations**: May blindly follow tool instructions even when results are nonsensical
  
- **Tool dependency**: Risk of over-reliance on external tools without critical evaluation
  
- **Knowledge reconciliation**: Difficulty balancing internal knowledge against external information
  
- **Belief persistence**: May dismiss external knowledge if previous beliefs are too strong
  
- **Information bias**: Potential tendency to trust AI-generated information over other sources
  
- **Planning constraints**: Struggle with scenarios requiring constant plan revision or involving irreversible actions
  
- **Computational costs**: Path searching and redundant processing can consume significant resources

## Practical Applications

AI Agents can be applied to various domains, including:

- Scientific research (proposing hypotheses, designing experiments)
- Software development (debugging, feature implementation)
- Personal assistance (scheduling, information retrieval)
- Business operations (customer service, data analysis)
- Educational support (personalized tutoring, content creation)

## Conclusion

AI Agents represent a significant advancement in autonomous artificial intelligence systems. By combining the linguistic and reasoning capabilities of Large Language Models with the ability to observe, plan, learn from experience, and use tools, these agents can tackle complex goals with reduced human guidance. However, their effectiveness depends on addressing substantial challenges related to judgment, knowledge integration, and resource optimization.

## Sources

- [Video Lecture: 【生成式AI時代下的機器學習(2025)】第二講：一堂課搞懂 AI Agent 的原理 (AI如何透過經驗調整行為、使用工具和做計劃)](https://www.youtube.com/watch?v=M2Yg1kwPpts)

---

*Note: This learning content is powered by a Large Language Model and synthesized from provided materials on AI Agents. While comprehensive, it represents a summary of current understanding and should be supplemented with additional research as the field rapidly evolves.*
