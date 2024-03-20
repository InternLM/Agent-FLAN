# Agent-FLAN: Designing Data and Methods of Effective Agent Tuning for Large Language Models

[![arXiv](https://img.shields.io/badge/arXiv-2403.12881-b31b1b.svg)](https://arxiv.org/abs/2403.12881)
[![license](https://img.shields.io/github/license/InternLM/opencompass.svg)](./LICENSE)

## ✨ Introduction  

[[🤗 HuggingFace](https://huggingface.co/lovesnowbest/Agent-FLAN-7b)]
[[📃 Paper](https://arxiv.org/abs/2403.12881)]
[[🌐 Project Page](https://internlm.github.io/Agent-FLAN/)]

> Open-sourced Large Language Models (LLMs) have achieved great success in various NLP tasks, however, they are still far inferior to API-based models when acting as agents. How to integrate agent ability into general LLMs becomes a crucial and urgent problem. This paper first delivers three key observations: (1) the current agent training corpus is entangled with both formats following and agent reasoning, which significantly shifts from the distribution of its pre-training data; (2) LLMs exhibit different learning speeds on the capabilities required by agent tasks; and (3) current approaches have side-effects when improving agent abilities by introducing hallucinations. Based on the above findings, we propose Agent-FLAN to effectively Fine-tune LANguage models for Agents. Through careful decomposition and redesign of the training corpus, Agent-FLAN enables Llama2-7B to outperform prior best works by 3.5% across various agent evaluation datasets. With comprehensively constructed negative samples, Agent-FLAN greatly alleviates the hallucination issues based on our established evaluation benchmark. Besides, it consistently improves the agent capability of LLMs when scaling model sizes while slightly enhancing the general capability of LLMs.

## 🚀 What's New

- **[2024.3.21]** Paper available on [ArXiv](https://arxiv.org/abs/2403.12881). 🔥🔥🔥
- **[2024.3.20]** Release the dataset and model checkpoint for Agent-FLAN. 🎉🎉🎉

## ♟️ Agent-FLAN

Agent-FLAN series are finetuned on AgentInstruct and Toolbench by applying the data generation pipeline proposed in Agent-FLAN paper, which holds strong abilities on various agent tasks and tool utilization~

<div>
<center>
<img src="docs/figure/teaser.png">

Comparison of recent agent tuning approaches on Held-In, Held-Out tasks. Performances are normalized with GPT-4 results for better visualization. * denotes our re-implementation for a fair comparison.
</div>

### 🤗 HuggingFace Model & Dataset

Agent-FLAN is produced by mixed training on AgentInstruct, ToolBench, and ShareGPT datasets from the Llama2-chat series.

The models follow the conversation format of Llama-2-chat, with the template protocol as:
```python
dict(role='user', begin='<|Human|>െ', end='\n '),
dict(role='system', begin='<|Human|>െ', end='\n '),
dict(role='assistant', begin='<|Assistant|>െ', end='ി\n '),
```

The 7B model is available on Huggingface model hub.

|    Model    |                        Huggingface Repo                        |
| :---------: | :------------------------------------------------------------: |
| Agent-FLAN-7B  | [🤗Huggingface Link](https://huggingface.co/lovesnowbest/Agent-FLAN-7b)  |

The Agent-FLAN dataset is also available on Huggingface dataset hub.

|    Dataset    |                        Huggingface Repo                        |
| :---------: | :------------------------------------------------------------: |
| Agent-FLAN Dataset  | [🤗Huggingface Link](https://huggingface.co/datasets/lovesnowbest/Agent-FLAN)  |

## 💫 Detailed Results

<div>
<center>
<img src="docs/figure/performance.png" width="100%">
</div>

Main results of Agent-FLAN. Agent-FLAN significantly outperforms previous agent-tuning approaches by a large margin on both held-in and held-out tasks. * denotes our re-implementation with the same amount of training data for a fair comparison. Since FireAct does not train on AgentInstruct dataset, we omit its performance on the HELD-IN set. Bold: the best in API-based and open-sourced models.


## ❤️ Acknowledgements

Agent-FLAN is built with [Lagent](https://github.com/InternLM/lagent) and [T-Eval](https://github.com/open-compass/t-eval). Thanks for their awesome work!

## 🖊️ Citation

If you find this project useful in your research, please consider cite:
```
@article{chen2024agent,
  title={Agent-FLAN: Designing Data and Methods of Effective Agent Tuning for Large Language Models},
  author={Chen, Zehui and Liu, Kuikun and Wang, Qiuchen and Liu, Jiangning and Zhang, Wenwei and Lin, Dahua and Chen, Kai and Zhao, Feng},
  journal={arXiv preprint arXiv:2403.12881},
  year={2024}
}
```

## 💳 License

This project is released under the Apache 2.0 [license](./LICENSE).
