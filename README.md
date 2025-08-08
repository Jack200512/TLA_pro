# TLA_pro
A beginner-level experiment: fine-tuning TinyLLaMA with LoRA on Alpaca data under limited GPU resources.
---
# LoRA 微调实验项目

本项目为一次基于 HuggingFace 生态与 LoRA 技术的微调实验，主要目标是探索不同训练参数（如 batch size、learning rate、训练轮数等）对模型性能（loss / perplexity）的影响，训练数据截取自 Alpaca 数据集。

实验过程中共进行了五轮训练，并整理了完整的训练参数、评估结果与调参分析，详见项目中的 `基于LoRA的TinyLlama微调实验_实验报告.md` 文件。

## 项目内容概览

- `训练脚本`：包含用于微调的核心代码与配置参数  
- `training_output`：部分训练轮次保存的模型权重  
- `基于LoRA的TinyLlama微调实验_实验报告.md`：完整记录了训练过程、参数设置、loss / perplexity 分析与个人反思
- `learning_notes`：学习笔记，包含常见数据集格式及特点、数据预处理与格式化、多轮对话记忆机制、超参数基础知识、模型结构与 tokenizer 关系、PEFT 与 LoRA 配置详解，以及训练代码实例分析和后续学习计划。

## 注意事项

- 实验过程中有一次训练未生成新的 checkpoint，初步判断可能与缓存或 Colab 平台资源限制有关，尚未进行修复，但不影响整体实验分析的连贯性。
- 训练脚本大多借助 AI 工具生成，并通过理解与调试完成修正，细节已在报告中注明。

---

如需进一步了解训练细节与分析，请阅读 [基于LoRA的TinyLlama微调实验_实验报告.md]。
学习笔记内容请见 learning_notes 文件夹。
