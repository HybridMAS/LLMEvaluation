# Evaluation of LLM and LLM based Systems
# Compendium of LLM Evaluation methods
---
### Introduction
The aim of this compendium is to assist academics and industry professionals in creating effective evaluation suites tailored to their specific needs. It does so by reviewing the top industry practices for assessing large language models (LLMs) and their applications. This work goes beyond merely cataloging benchmarks and evaluation studies; it encompasses a comprehensive overview of all effective and practical evaluation techniques, including those embedded within papers that primarily introduce new LLM methodologies and tasks. I plan to periodically update this survey with any noteworthy and shareable evaluation methods that I come across.
I aim to create a resource that will enable anyone with queries—whether it's about evaluating a large language model (LLM) or an LLM application for specific tasks, determining the best methods to assess LLM effectiveness, or understanding how well an LLM performs in a particular domain—to easily find all the relevant information needed for these tasks. Additionally, I want to highlight various methods for evaluating the evaluation tasks themselves, to ensure that these evaluations align effectively with business or academic objectives.

My view on LLM Evaluation: [Deck](LLMEvaluation.pdf), and  [video](https://community.analyticsvidhya.com/c/datahour/evaluating-llms-and-llm-systems-pragmatic-approach) (by [Andrei Lopatenko](https://www.linkedin.com/in/lopatenko/))

![Evals are surprisingly often all you need](greg.png)

# Table of contents
- [Reviews and Surveys](#reviews-and-surveys)
- [Leaderboards and Arenas](#leaderboards-and-arenas)
- [Evaluation Software](#evaluation-software)
- [LLM Evaluation articles in tech media and blog posts from companies](#llm-evaluation-articles-in-tech-media-and-blog-posts-from-companies)
- [Large benchmarks](#large-benchmarks)
- [Evaluation of evaluation, Evaluation theory, evaluation methods, analysis of evaluation](#evaluation-of-evaluation-evaluation-theory-evaluation-methods-analysis-of-evaluation)
- [HITL (Human in the Loop)](#hitl-human-in-the-loop)
- [LLM as Judge](#llm-as-judge)
- [LLM Evaluation](#llm-evaluation)
    - [Embeddings](#embeddings)
    - [In Context Learning](#in-context-learning)
    - [Hallucinations](#hallucinations)
    - [Multi Turn](#multi-turn)
    - [Reasoning](#reasoning)
    - [Multi-Lingual](#multi-lingual)
    - [Multi-Modal](#multi-modal)
    - [Instruction Following](#instruction-following)
    - [Ethical AI](#ethical-ai)
    - [Biases](#biases)
    - [Safe AI](#safe-ai)
    - [Code Generating LLMs](#code-generating-llms)
    - [LLM  quality (generic methods: overfitting, redundant layers etc)](#llm--quality-generic-methods-overfitting-redundant-layers-etc)
    - [Software Performace (latency, throughput, memory, storage)](#software-performance)
    - [Agent LLM architectures](#agent-llm-architectures)
    - [Various unclassified tasks](#various-unclassified-tasks)
- [LLM Systems](#llm-systems)
    - [RAG Evaluation](#rag-evaluation)
    - [Conversational systems](#conversational-systems)
    - [Copilots](#copilots)
    - [Search and Recommendation Engines](#search-and-recommendation-engines)
    - [Task Utility](#task-utility)
  - [Verticals](#verticals)
    - [Healthcare and medicine](#healthcare-and-medicine)
    - [Science (generic)](#science-generic)
    - [Financial](#financial)

---
### Reviews and Surveys
- Evaluating Large Language Models: A Comprehensive Survey , Oct 2023 https://arxiv.org/abs/2310.19736
- A Survey on Evaluation of Large Language Models Jul 2023 https://arxiv.org/abs/2307.03109
- Through the Lens of Core Competency: Survey on Evaluation of Large Language Models, Aug 2023 , https://arxiv.org/abs/2308.07902
---
### Leaderboards and Arenas
- LMSys Arena https://chat.lmsys.org/?leaderboard (explanation: https://lmsys.org/blog/2023-05-03-arena/)
- MTEB https://huggingface.co/spaces/mteb/leaderboard
- SWE Bench https://www.swebench.com/
- Gorilla, Berkeley function calling Leaderboard https://gorilla.cs.berkeley.edu/leaderboard.html https://gorilla.cs.berkeley.edu/blogs/8_berkeley_function_calling_leaderboard.html
- WildBench WildBench: Benchmarking LLMs with Challenging Tasks from Real Users in the Wild https://huggingface.co/spaces/allenai/WildBench
- Enterprise Scenarios, Patronus https://huggingface.co/blog/leaderboard-patronus
- Vectara Hallucination Leaderboard https://github.com/vectara/hallucination-leaderboard
- Ray/Anyscale's LLM Performance Leaderboard https://github.com/ray-project/llmperf-leaderboard (explanation: https://www.anyscale.com/blog/comparing-llm-performance-introducing-the-open-source-leaderboard-for-llm)
---
### Evaluation Software
- MTEB https://huggingface.co/spaces/mteb/leaderboard
- OpenICL Framework https://arxiv.org/abs/2303.02913
- RAGAS https://docs.ragas.io/en/stable/
- EleutherAI LLM Evaluation Harness https://github.com/EleutherAI/lm-evaluation-harness
- OpenAI Evals https://github.com/openai/evals
- ML Flow Evaluate https://mlflow.org/docs/latest/llms/llm-evaluate/index.html
- MosaicML Composer https://github.com/mosaicml/composer
- TruLens https://github.com/truera/trulens/
- BigCode Evaluation Harness https://github.com/bigcode-project/bigcode-evaluation-harness
﻿---
### LLM Evaluation articles in tech media and blog posts from companies <a id="articles"></a>
- https://techcrunch-com.cdn.ampproject.org/c/s/techcrunch.com/2024/03/23/why-its-impossible-to-review-ais-and-why-techcrunch-is-doing-it-anyway/amp/
- https://blog.mozilla.ai/exploring-llm-evaluation-at-scale-with-the-neurips-large-language-model-efficiency-challenge/
- https://www.nytimes.com/2024/04/15/technology/ai-models-measurement.html
- 
---
### Large benchmarks
- SUPER-NATURALINSTRUCTIONS: Generalization via Declarative Instructions on 1600+ NLP Tasks EMNLP 2022, https://aclanthology.org/2022.emnlp-main.340.pdf
- MEASURING MASSIVE MULTITASK LANGUAGE UNDERSTANDING, ICLR, 2021,  https://arxiv.org/pdf/2009.03300.pdf
---
### Evaluation of evaluation, Evaluation theory, evaluation methods, analysis of evaluation
- Elo Uncovered: Robustness and Best Practices in Language Model Evaluation, Nov 2023 https://arxiv.org/abs/2311.17295
- Are Emergent Abilities of Large Language Models a Mirage? Apr 23 https://arxiv.org/abs/2304.15004
- Don't Make Your LLM an Evaluation Benchmark Cheater nov 2023 https://arxiv.org/abs/2311.01964
- Evaluating Question Answering Evaluation, 2019, https://aclanthology.org/D19-5817/
- Evaluating Open-QA Evaluation, 2023, https://arxiv.org/abs/2305.12421
- (RE: stat methods ) Prediction-Powered Inference jan 23 https://arxiv.org/abs/2301.09633  PPI++: Efficient Prediction-Powered Inference nov 23, https://arxiv.org/abs/2311.01453
- Lifelong Benchmarks: Efficient Model Evaluation in an Era of Rapid Progress, Feb 2024, https://arxiv.org/abs/2402.19472
- Are We on the Right Way for Evaluating Large Vision-Language Models?, Apr 2024, https://arxiv.org/pdf/2403.20330.pdf
- What Are We Measuring When We Evaluate Large Vision-Language Models? An Analysis of Latent Factors and Biases, Apr 2024, https://arxiv.org/abs/2404.02415

---
### HITL (Human in the Loop)
- Evaluating Question Answering Evaluation, 2019, https://aclanthology.org/D19-5817/
- Developing a Framework for Auditing Large Language Models Using Human-in-the-Loop, Feb 2024, https://arxiv.org/abs/2402.09346 

---
### LLM as Judge
- Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena Jun 2023, https://arxiv.org/abs/2306.05685
- The Generative AI Paradox on Evaluation: What It Can Solve, It May Not Evaluate, Feb 2024, https://arxiv.org/abs/2402.06204
- Benchmarking Foundation Models with Language-Model-as-an-Examiner, 2022, https://proceedings.neurips.cc/paper_files/paper/2023/hash/f64e55d03e2fe61aa4114e49cb654acb-Abstract-Datasets_and_Benchmarks.html
- ChatEval: Towards Better LLM-based Evaluators through Multi-Agent Debate, Aug 2023, https://arxiv.org/abs/2308.07201
- ALLURE: Auditing and Improving LLM-based Evaluation of Text using Iterative In-Context-Learning, Sep 2023, https://arxiv.org/abs/2309.13701
---
---
## LLM Evaluation
### Embeddings
- MTEB: Massive Text Embedding Benchmark Oct 2022 https://arxiv.org/abs/2210.07316 Leaderboard https://huggingface.co/spaces/mteb/leaderboard
---
### In Context Learning
- HellaSwag,  HellaSwag: Can a Machine Really Finish Your Sentence? 2019, https://arxiv.org/abs/1905.07830 Paper + code + dataset https://rowanzellers.com/hellaswag/ 
-  The LAMBADA dataset: Word prediction requiring a broad discourse context 2016, https://arxiv.org/abs/1606.06031 
---
### Hallucinations
- HaluEval: A Large-Scale Hallucination Evaluation Benchmark for Large Language Models, Dec 2023,  https://aclanthology.org/2023.emnlp-main.397.pdf 
- Long-form factuality in large language models, Mar 2024, https://arxiv.org/abs/2403.18802

---
### Multi Turn
- LMRL Gym: Benchmarks for Multi-Turn Reinforcement Learning with Language Models Nov 2023, https://arxiv.org/abs/2311.18232
- MT-Bench-101: A Fine-Grained Benchmark for Evaluating Large Language Models in Multi-Turn Dialogues Feb 24 https://arxiv.org/abs/2402.14762
- How Well Can LLMs Negotiate? NEGOTIATIONARENA Platform and Analysis Feb 2024 https://arxiv.org/abs/2402.05863
- MINT: Evaluating LLMs in Multi-turn Interaction with Tools and Language Feedback, Sep 2023, https://arxiv.org/abs/2309.10691
 
---
### Reasoning
- Comparing Humans, GPT-4, and GPT-4V On Abstraction and Reasoning Tasks 2023, [arxiv](https://arxiv.org/abs/2311.09247)
- LLM Reasoners: New Evaluation, Library, and Analysis of Step-by-Step Reasoning with Large Language Models, https://arxiv.org/abs/2404.05221
- Evaluating LLMs' Mathematical Reasoning in Financial Document Question Answering, Feb 24, https://arxiv.org/abs/2402.11194v2 
- Competition-Level Problems are Effective LLM Evaluators, Dec 23, https://arxiv.org/abs/2312.02143
---
### Multi-Lingual
- AlGhafa Evaluation Benchmark for Arabic Language Models Dec 23, ACL Anthology https://aclanthology.org/2023.arabicnlp-1.21.pdf https://aclanthology.org/2023.arabicnlp-1.21/ 
- Introducing the Open Ko-LLM Leaderboard: Leading the Korean LLM Evaluation Ecosystem https://huggingface.co/blog/leaderboard-upstage
- Heron-Bench: A Benchmark for Evaluating Vision Language Models in Japanese , Apr 2024 https://arxiv.org/abs/2404.07824
- AlignBench: Benchmarking Chinese Alignment of Large Language Models, Nov 2023, https://arxiv.org/abs/2311.18743
- The Invalsi Benchmark: measuring Language Models Mathematical and Language understanding in Italian, Mar 2024, https://arxiv.org/pdf/2403.18697.pdf
---
### Multi-Modal
- Holistic Evaluation of Text-to-Image Models Nov 23 https://arxiv.org/abs/2311.04287
- VBench: Comprehensive Benchmark Suite for Video Generative Models Nov 23 https://arxiv.org/abs/2311.04287
- Evaluating Text-to-Visual Generation with Image-to-Text Generation, Apr 2024, https://arxiv.org/abs/2404.01291
- What Are We Measuring When We Evaluate Large Vision-Language Models? An Analysis of Latent Factors and Biases, Apr 2024, https://arxiv.org/abs/2404.02415
- Are We on the Right Way for Evaluating Large Vision-Language Models?, Apr 2024, https://arxiv.org/pdf/2403.20330.pdf

---
### Instruction Following
- Evaluating Large Language Models at Evaluating Instruction Following Oct 2023, https://arxiv.org/abs/2310.07641
---
### Ethical AI
- Evaluating the Moral Beliefs Encoded in LLMs,  Jul 23 https://arxiv.org/abs/2307.14324
- AI Deception: A Survey of Examples, Risks, and Potential Solutions Aug 23 https://arxiv.org/abs/2308.14752
- Aligning AI With Shared Human Value, Aug 20 - Feb 23, https://arxiv.org/abs/2008.02275 Re: ETHICS benchmark
- What are human values, and how do we align AI to them?, Mar 2024, [pdf](https://static1.squarespace.com/static/65392ca578eee444c445c9de/t/6606f95edb20e8118074a344/1711733370985/human-values-and-alignment-29MAR2024.pdf)
---
### Biases
- FairPair: A Robust Evaluation of Biases in Language Models through Paired Perturbations, Apr 2024 https://arxiv.org/abs/2404.06619v1
---
### Safe AI
- Gradient-Based Language Model Red Teaming, Jan 24, https://arxiv.org/abs/2401.16656
- JailbreakBench: An Open Robustness Benchmark for Jailbreaking Large Language Models, Mar 2024, https://arxiv.org/abs/2404.01318
- Announcing a Benchmark to Improve AI Safety MLCommons has made benchmarks for AI performance—now it's time to measure safety, Apr 2024 [IEEE Spectrum](https://spectrum.ieee.org/ai-safety-benchmark)

---
### Code Generating LLMs
- Evaluating Large Language Models Trained on Code HumanEval Jul 2022 https://arxiv.org/abs/2107.03374
- CodeXGLUE: A Machine Learning Benchmark Dataset for Code Understanding and Generation Feb 21 https://arxiv.org/abs/2102.04664
- Copilot Evaluation Harness: Evaluating LLM-Guided Software Programming Feb 24 https://arxiv.org/abs/2402.14261
- SWE Bench SWE-bench: Can Language Models Resolve Real-World GitHub Issues? Feb 2024 https://arxiv.org/abs/2402.05863 https://www.cognition-labs.com/post/swe-bench-technical-report
- Gorilla Functional Calling Leaderboard, Berkeley https://gorilla.cs.berkeley.edu/blogs/8_berkeley_function_calling_leaderboard.html
- DevBench: A Comprehensive Benchmark for Software Development, Mar 2024, https://arxiv.org/abs/2403.08604

---
### LLM  quality (generic methods: overfitting, redundant layers etc)
- https://calculatedcontent.com/2024/01/23/evaluating-fine-tuned-llms-with-weightwatcher/
---
### Software Performance
- Ray/Anyscale's LLM Performance Leaderboard https://github.com/ray-project/llmperf-leaderboard (explanation: https://www.anyscale.com/blog/comparing-llm-performance-introducing-the-open-source-leaderboard-for-llm)
- MLCommons MLPerf benchmarks (inference) [MLPerf announcement of the LLM track](https://mlcommons.org/2023/09/mlperf-results-highlight-growing-importance-of-generative-ai-and-storage/)
---
### Agent LLM architectures
- Put Your Money Where Your Mouth Is: Evaluating Strategic Planning and Execution of LLM Agents in an Auction Arena, Oct 2023, https://arxiv.org/abs/2310.05746
- LLM-Deliberation: Evaluating LLMs with Interactive Multi-Agent Negotiation Games, Sep 2023, https://arxiv.org/abs/2309.17234
- AgentBench: Evaluating LLMs as Agents, Aug 2023, https://arxiv.org/abs/2308.03688
---
### Various unclassified tasks
- Table Meets LLM: Can Large Language Models Understand Structured Table Data? A Benchmark and Empirical Study Mar 24, WSDM 24, https://www.microsoft.com/en-us/research/publication/table-meets-llm-can-large-language-models-understand-structured-table-data-a-benchmark-and-empirical-study/
-  LLM Comparative Assessment: Zero-shot NLG Evaluation through Pairwise Comparisons using Large Language Models, jul 2023 https://arxiv.org/abs/2307.07889v3
- OpenEQA: From word models to world models, Meta, Apr 2024, Understanding physical spaces by Models,  https://ai.meta.com/blog/openeqa-embodied-question-answering-robotics-ar-glasses/?utm_source=twitter&utm_medium=organic_social&utm_content=video&utm_campaign=dataset
- ELITR-Bench: A Meeting Assistant Benchmark for Long-Context Language Models, Apr 2024, https://arxiv.org/pdf/2403.20262.pdf
- Is Your LLM Outdated? Benchmarking LLMs & Alignment Algorithms for Time-Sensitive Knowledge. Apr 2024, https://arxiv.org/abs/2404.08700
---
---

## LLM Systems
### RAG Evaluation
- RAGAS: Automated Evaluation of Retrieval Augmented Generation Jul 23, https://arxiv.org/abs/2309.15217
- ARES: An Automated Evaluation Framework for Retrieval-Augmented Generation Systems Nov 23, https://arxiv.org/abs/2311.09476 
---
### Conversational systems
- Foundation metrics for evaluating effectiveness of healthcare conversations powered by generative AI Feb 24, Nature https://www.nature.com/articles/s41746-024-01074-z.epdf
- https://towardsdatascience.com/how-to-make-the-most-out-of-llm-production-data-simulated-user-feedback-843c444febc7
- How Well Can LLMs Negotiate? NEGOTIATIONARENA Platform and Analysis Feb 2024 https://arxiv.org/abs/2402.05863
---
### Copilots
- Copilot Evaluation Harness: Evaluating LLM-Guided Software Programming Feb 24 https://arxiv.org/abs/2402.14261
---
### Search and Recommendation Engines
- Is ChatGPT a Good Recommender? A Preliminary Study Apr 2023 https://arxiv.org/abs/2304.10149 
---
### Task Utility
- Towards better Human-Agent Alignment: Assessing Task Utility in LLM-Powered Applications, Feb 2024, https://arxiv.org/abs/2402.09015
---
---
## Verticals
### Healthcare and medicine
- Foundation metrics for evaluating effectiveness of healthcare conversations powered by generative AI Feb 24, Nature https://www.nature.com/articles/s41746-024-01074-z.epdf
- Health-LLM: Large Language Models for Health Prediction via Wearable Sensor Data Jan 2024 https://arxiv.org/abs/2401.06866
- Evaluating LLM -- Generated Multimodal Diagnosis from Medical Images and Symptom Analysis, Jan 2024, https://arxiv.org/abs/2402.01730
### Science (generic)
- SciRepEval: A Multi-Format Benchmark for Scientific Document Representations, 2022, https://arxiv.org/abs/2211.13308

### Financial
- Evaluating LLMs' Mathematical Reasoning in Financial Document Question Answering, Feb 24, https://arxiv.org/abs/2402.11194v2 




