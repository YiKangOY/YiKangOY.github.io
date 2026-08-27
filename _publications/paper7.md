---
title: "Retrieve, Schedule, Reflect: LLM Agents for Chip QoR Optimization"
collection: publications
permalink: /publication/paper7
date: 2026-03-14
venue: 'ACM/IEEE Workshop on Machine Learning for CAD (MLCAD), Jeju, 2026'
authors: '<strong>Yikang Ouyang</strong>, Yang Luo, Dongsheng Zuo, Yuzhe Ma'
paperurl: 'https://arxiv.org/abs/2603.13767'
---

Modern chip design requires multi-objective optimization of timing, power, and area under stringent time-to-market constraints. Although powerful optimization algorithms are integrated into EDA tools, achieving high QoR hinges on effective long-horizon scheduling, which relies heavily on manual expert intervention. To address this issue and automate chip design, we propose an agentic LLM framework that schedules chip optimizations through direct interaction with EDA tools. The agent is grounded in natural language expertise expressed as a search tree through retrieval-augmented generation (RAG). We further improve scheduling quality with Pareto-driven QoR feedback through language reflection. Experimental results show that, compared with black-box search methods such as reinforcement learning, our framework achieves 10% greater timing improvement while consuming less power and area, with more than 4x speedup. The post-optimization QoR is also comparable to that achieved by human experts. Finally, the agent supports customized tasks expressed in natural language, enabling preferential QoR trade-offs. The code and chip design data will be publicly available at [https://github.com/YiKangOY/Open-LLM-ECO](https://github.com/YiKangOY/Open-LLM-ECO).
