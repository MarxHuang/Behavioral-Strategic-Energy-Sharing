# Dataset: A Behavioral-Strategic Market Mechanism for Energy Sharing

This repository contains the configuration files and the complete experimental results dataset for the paper **"A Behavioral-Strategic Market Mechanism for Energy Sharing: Integrating LLM-Driven Bounded Rationality with Regulatory Optimization"**, submitted to the *IEEE Transactions on Smart Grid*.

## 📖 Overview

Energy sharing markets are often theoretically efficient but practically vulnerable to the "Human Factor." Prosumers exhibit bounded rationality (e.g., cognitive biases, panic behaviors), which creates a "Reality Gap" that can lead to severe market instabilities. 

This dataset provides the full simulation logs and agent configurations used to validate our proposed **Bi-Level Regulatory Optimization Framework**. The lower level of this framework employs Neuro-Symbolic Agents powered by Large Language Models (LLMs) to instantiate high-fidelity bounded rationality, while the upper level dynamically adjusts regulatory price signals to stabilize the market and maximize social welfare.

## 📂 Repository Structure

```text
📦 Dataset-Root
 ┣ 📜 configs_semiREALITY.json     # Initial configurations for Neuro-Symbolic Agents
 ┗ 📂 exp_20251226_150854_FULL     # Full trajectory data of the bi-level optimization
    ┣ 📜 optimizer_summary.json    # Global convergence status and regulatory signals
    ┣ 📂 iter_0                    # Data for the initial iteration
    ┃  ┣ 📜 agent_actions.csv      # Bids, strategies, and reasoning of prosumers
    ┃  ┗ 📜 market_summary.csv     # Market clearing results and macro metrics
    ┣ 📂 iter_1
    ┣ ...
    ┗ 📂 iter_24                   # Data for the final convergence iteration (Iter 25)
```

📄 Data Description
1. configs_semiREALITY.json
This file defines the initial personas and behavioral parameters for the Neuro-Symbolic Agents participating in the local energy market.

agent_id: Unique identifier for each prosumer (e.g., PR_01, PR_24).

persona_type & persona_description: Socio-economic profiles and load characteristics (e.g., Risk-Averse Business Manager, Grid-Dependent Household).

behavior_params:

target_bias: The agent's trading inclination (positive for conservative/supply-oriented, negative for aggressive/demand-securing).

rigidity: The strategy rigidity coefficient, reflecting the agent's sensitivity to price fluctuations and their degree of bounded rationality.

reasoning_trace: The baseline logical reasoning prompt provided to the LLM.

2. exp_20251226_150854_FULL/
This directory contains the step-by-step trajectory data across 25 iterations of the bi-level game:

optimizer_summary.json: Logs the upper-level optimizer's objective function values, market stability metrics, and the generated regulatory pricing signals over the convergence process.

iter_*/agent_actions.csv: Details the lower-level game dynamics. It includes each agent's submitted energy volumes, expected prices, and the cognitive reasoning outputs from the LLM, illustrating how cognitive biases influence bidding behavior.

iter_*/market_summary.csv: Provides a snapshot of the market after each iteration, including social welfare, supply-demand balance ratios, and the quantified "Reality Gap" the system experiences.

⚙️ Usage
This dataset can be utilized to:

Reproduce the convergence trajectory of the proposed bi-level regulatory algorithm when confronted with human bounded rationality.

Analyze the bargaining dynamics and strategic evolution of LLM-driven agents with diverse personas in multi-round peer-to-peer (P2P) energy trading.

Serve as a benchmark for reinforcement learning or behavioral economics studies focused on microgrid and energy community market design.

💡 Citation
If you utilize this dataset in your research, please consider citing our manuscript:

J. Huang, T. Yu, Z. Pan, and Y. Wu, "A Behavioral-Strategic Market Mechanism for Energy Sharing: Integrating LLM-Driven Bounded Rationality with Regulatory Optimization," IEEE Transactions on Smart Grid (Under Review), 2026.

(The citation format will be updated upon the formal acceptance of the paper.)

🏛️ Acknowledgments
This research is supported by the National Natural Science Foundation of China (Grant Nos. 52207105, U24B6010) and the Guangdong Basic and Applied Basic Research Foundation (Grant No. 2025A1515010118).
