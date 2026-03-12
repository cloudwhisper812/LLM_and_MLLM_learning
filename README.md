# LLM/MLLM learning笔记

[![Commit Activity (week)](https://img.shields.io/github/commit-activity/w/cloudwhisper812/LLM-MLLM-learning/main?label=commits%2Fweek)](https://github.com/cloudwhisper812/LLM-MLLM-learning)
[![Commit Activity (month)](https://img.shields.io/github/commit-activity/m/cloudwhisper812/LLM-MLLM-learning/main?label=commits%2Fmonth)](https://github.com/cloudwhisper812/LLM-MLLM-learning)


这是一个以 **Markdown 笔记**为主的 LLM / MLLM 学习仓库，内容来自 **论文阅读 + 与大模型交互问答 + 个人理解整理**。不拘泥于公式推导，目标是 **快速召回、温故知新**。

- **内容定位**：知识梳理 / 论文笔记（非可运行训练代码仓库）
- **笔记分块**：**个人总结**、**基础知识**、**经典论文**
- **后续计划**：增加大模型 coding 相关内容

## 快速开始

- **阅读入口**：从下方目录开始点链接阅读
- **查找内容**：用编辑器全局搜索关键词（或在 GitHub 上用仓库搜索）
- **目录说明**：
  - `基础知识/`：概念与方法（偏体系化梳理）
  - `经典论文/`：论文阅读笔记（偏 paper 复盘）


## 一、个人总结

| 主题 | 内容 |
|------|------|
| [01. LLM模型架构与训练范式总结](基础知识/01.%20LLM模型架构与训练范式总结.md) | Encoder-only (BERT, BGE), Encoder-Decoder (T5, BART, UL2), Decoder-only (GPT, Llama) |
| [02. MLLM架构](基础知识/02.%20MLLM架构(llava,%20blip,%20flamingo,%20end2end).md) | LLaVA, BLIP (Q-Former, CapFilt), Flamingo (Perceiver, interleaved) |

---

## 二、基础知识

| 主题 | 内容 |
|------|------|
| [01. activation function](基础知识/03.%20activation%20function.md) | sigmoid, tanh, relu, GeLU, Swish, SwiGLU |
| [02. positional embedding](基础知识/04.%20positional%20embedding.md) | Sinusoidal PE, Learnable PE, RoPE, Alibi |
| [03. normalization](基础知识/05.%20normalization.md) | LN vs BN, Pre-Norm vs Post-Norm, RMSNorm |
| [04. scaling law](基础知识/06.%20scaling%20law.md) | Power Law, Chinchilla, D≈20N, C≈6ND |
| [05. MoE](基础知识/07.%20MoE.md) | Router, Experts, Load Balancing, Top-K, Expert Capacity |
| [06. optimizer](基础知识/08.%20optimizer.md) | Momentum, adaptive learning rate, adam, adamW |
| [07. KV cache](基础知识/09.%20kv%20cache.md) | 显存计算, MHA/MQA/GQA, PagedAttention |
| [08. Flash Attention](基础知识/10.%20flash%20attention.md) | 切块, Memory bandwidth, Online softmax |
| [09. LoRA](基础知识/11.%20LoRA.md) | Low-rank adaptation, 参数高效微调 |
| [10. RAG](基础知识/12.%20RAG.md) | 检索增强生成, 向量检索, 召回与重排 |
| [11. decoding strategy](基础知识/13.%20decoding%20strategy.md) | Greedy, Beam Search, Sampling, Top-k/top-p, Temperature |
| [12. tokenizer](基础知识/14.%20tokenizer.md) | BPE, WordPiece, SentencePiece, 特殊 token 处理 |
| [13. quantization](基础知识/15.%20quantization.md) | PTQ/QAT, INT8/INT4, 误差与部署 |
| [14. Distributed Training](基础知识/16.%20Distributed%20Training.md) | 数据并行/张量并行/流水线并行, 通信与显存 |
| [15. RL](基础知识/17.%20RL.md) | RLHF/RLAIF, PPO/DPO 等相关概念 |

---

## 三、经典论文
参考：
- https://github.com/Hannibal046/Awesome-LLM
- https://github.com/friedrichor/Awesome-Multimodal-Papers

| 主题 | 内容 |
|------|------|
| [stable diffusion + DIT](经典论文/stable%20diffusion%20+%20DIT.md) | LDM, VAE, U-Net, DiT |
| [siglip 1 and 2](经典论文/siglip%201%20and%202.md) | 二分类, MAP, NaViT, 自蒸馏, LocCa |

---

## 贡献方式（可选）

- **新增笔记**：在 `基础知识/` 或 `经典论文/` 下新增 `.md`，并在本 README 的表格里补一行链接
- **命名建议**：优先用 `NN. topic.md` 形式便于排序；文件名尽量稳定，避免频繁改名导致链接失效
