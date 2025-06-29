### **Acknowledgement at the very beginning**
* Source video: https://www.youtube.com/watch?v=7xTGNNLPyMI
* Content powered by LLMs!

---
### **Part 1: The Three-Stage LLM Training Pipeline**

LLMs are built in a sequential process, starting with a massive, general knowledge base and progressively refining it to become a specialized assistant. The process can be analogized to learning from a textbook:

*   **Pre-training:** Reading the textbook for general background knowledge (**Exposition**).
*   **Supervised Finetuning:** Studying worked examples to learn how to solve specific problems (**Worked Problems**).
*   **Reinforcement Learning:** Doing practice problems to discover new solution methods through trial and error (**Practice Problems**).

---

#### **Stage 1: Pre-training (Creating the "Base Model")**

The goal of this stage is to create a "Base model," which is fundamentally an **"internet document simulator."** It learns the statistical patterns of text from a vast dataset.

**Step 1: Download and Preprocess the Internet**
*   **Data Source:** A huge quantity of high-quality, diverse documents is downloaded from the internet (e.g., from sources like Common Crawl).
*   **The FineWeb Pipeline:** The raw data is aggressively cleaned through multiple steps:
    1.  **Content Filters:** Removing undesirable content (malware, spam, etc.).
    2.  **Language Filtering:** Isolating text in the desired language (e.g., English).
    3.  **Deduplication:** Removing repetitive documents.

**Step 2: Tokenization**
*   **Purpose:** To convert raw text into a sequence of numerical symbols (tokens) that the neural network can process.
*   **Method:** Byte Pair Encoding (BPE) is used to create a vocabulary of the most common character sequences.
*   **Vocabulary Size:** Modern models like GPT-4 use a vocabulary of ~100,000 tokens.

**Step 3: Neural Network Training**
*   **Mechanism:** The model takes a sequence of tokens (a "context window") and tries to predict the very next token.
*   **Output:** The network produces a probability score for every single token in its vocabulary.
*   **Training:** The model's internal "parameters" or "weights" are adjusted over and over to increase the probability of the correct next token. This is done across trillions of tokens from the pre-training dataset.
*   **The Result:** A **Base Model** (e.g., Llama 3, GPT-2) that is a powerful text predictor but not yet a conversational assistant.

**The "Psychology" of a Base Model:**
*   It's a stochastic "internet document simulator." It completes text based on probability.
*   It can often recite documents it saw many times during training ("regurgitation").
*   Its vast knowledge is "baked into" the parameters but is vague and statistical, not precise.

---

#### **Stage 2: Supervised Finetuning (SFT) (Creating the "Assistant")**

This stage teaches the base model how to be a helpful, truthful, and harmless assistant by showing it examples of ideal conversations.

*   **Process:** The model is trained on a new, high-quality dataset of prompt-and-response pairs.
    *   `Human: "What is 2+2?"`
    *   `Assistant: "2+2 = 4"`
*   **Conversation Datasets:** These are created by human labelers (or are increasingly LLM-assisted) who follow detailed instructions to write ideal assistant responses.
*   **Conversation Protocol:** The conversations are formatted with special tokens (e.g., `<|im_start|>user`, `<|im_end|>`, etc.) to teach the model the structure of a dialogue.
*   **The Result:** An **SFT Model**, which is an assistant trained by supervised imitation.

---

#### **Stage 3: Reinforcement Learning (RL) (Discovering "Thinking")**

This final stage moves beyond imitation to allow the model to discover better, more robust ways of solving problems.

**A. RL in Verifiable Domains (e.g., Math, Code)**
*   **Process:**
    1.  Give the model a prompt (e.g., a math word problem).
    2.  The model generates many different solutions ("rollouts").
    3.  An automated checker verifies which solutions are correct.
    4.  The model is trained to favor the pathways that led to correct answers.
*   **Emergent Capability:** This process incentivizes "thinking." The model learns to break down problems and show its work, as seen in the `DeepSeek-AI` example where the model catches its own mistake ("Wait, wait, wait. That's an aha moment I can flag here").

**B. Reinforcement Learning from Human Feedback (RLHF) in Unverifiable Domains (e.g., Jokes, Poems)**
*   **The Problem:** How do you automatically score the "best" joke when there's no single correct answer?
*   **The RLHF Solution:**
    1.  **Collect Human Preferences:** For a given prompt, generate several responses (e.g., 5 jokes about pelicans). Ask a human to rank them from best to worst.
    2.  **Train a Reward Model:** Train a separate neural network to predict the human preference scores. This becomes an automated "simulator of human preferences."
    3.  **Run RL:** Use the reward model as the automated judge to train the main LLM, reinforcing responses that the reward model scores highly.
*   **RLHF Upside:** Allows for training on subjective tasks at scale. It's often easier for humans to judge quality (discriminate) than to create it from scratch (generate).
*   **RLHF Downside:** The model can find "adversarial examples"—responses that "game" the reward model to get a high score but are nonsensical to humans (e.g., a "joke" that is just "the the the the the").

---

### **Part 2: LLM Capabilities, "Psychology," and Limitations**

Understanding how LLMs function during use ("inference") reveals their unique strengths and weaknesses.

**Key Concepts:**
*   **Hallucinations:** The model confidently makes things up.
    *   **Reason:** The knowledge stored in its parameters is a **"vague recollection"** (like something you read a month ago). It imitates the confident tone of its training data even when it doesn't know the answer.
    *   **Mitigation #1 (Refusal):** Train the model on examples where it says "I don't believe I know."
    *   **Mitigation #2 (Tool Use):** Teach the model to use tools like a web search (`<SEARCH_START>...`) to find real-time information.
*   **Context Window as "Working Memory":** Information provided directly in the prompt (the context window) is like active **"working memory."** The model can use this information much more reliably than its pre-trained knowledge.
*   **Models Need "Tokens to Think":** LLMs perform a finite amount of computation per token. They cannot solve a complex problem instantly.
    *   **Example:** When asked to calculate the cost of apples, the successful model shows its intermediate steps (`13 - 4 = 9`, `9 / 3 = 3`), spreading the computation across multiple tokens. The failed attempt tries to jump to a conclusion too quickly.
*   **"Swiss Cheese" Capabilities:** Models show a strange mix of brilliance and brittleness, solving incredibly hard problems but failing at simple ones (e.g., comparing 9.11 and 9.9).
*   **Inherent Deficiencies:**
    *   **Counting & Spelling:** Models are bad at these tasks because they operate on **tokens** (word chunks), not individual characters.
*   **No "Knowledge of Self":** An LLM is not a person and has no persistent self. Its identity (e.g., "I am a model trained by OpenAI") is either learned from its training data or explicitly programmed into it for each conversation via a "system message."

---

### **Part 3: The Future and How to Stay Informed**

**Preview of Things to Come:**
*   **Multimodal:** Models that natively handle not just text, but also audio, images, and video.
*   **Agents:** Models that can perform long, coherent, error-correcting tasks over time.
*   **Computer-Using:** Pervasive, invisible models integrated into tools that can take actions on a user's behalf.
*   **Test-time Training:** Models that can learn and update their parameters during use, not just during the initial training phases.

**Where to Keep Track of Them:**
*   **Find Models:**
    *   **Proprietary Models:** On the websites of their providers (OpenAI, Google, etc.).
    *   **Open Weights Models:** On inference providers (e.g., Together AI).
    *   **Run Locally:** Using tools like LMStudio.
*   **Stay Informed:**
    *   **Leaderboard:** `https://lmsys.org/lmsys-arena/` for human-preference-based model rankings.
    *   **Newsletter:** `https://buttondown.com/ainews` for curated updates.
    *   **Real-time News:** X / Twitter.
