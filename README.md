# Survey of Chain-of-Thought Reward Model

This is a collection of research papers on *Chain-of-Thought Reward Model (CoT RM)*.

Recent advances in industrial open-source LLMs suggest that CoT RM is more favorable than Classic RM.
The main advantages include:
- Less risk of reward hacking
- Interpretable reward signal
- Higher accuracy

---

## ⭐ Quote

**DeepSeek-V3**
>![image](https://github.com/user-attachments/assets/5d2881df-055a-46cf-b6fa-cbd1d32932f5)

**Kimi-k1.5**
>![image](https://github.com/user-attachments/assets/c1cc4c45-7e10-4701-908f-225e9233924a)



## 📖 Papers  

| Title | Publication Date | Link |
|---------------------------------|------------------------|---------------------------------|
| Inference-Time Scaling for Generalist Reward Modeling | 03 Apr 2025 | [ArXiv](https://arxiv.org/abs/2504.02495) |
| Scaling Evaluation-time Compute with Reasoning Models as Process Evaluators | 25 Mar 2025 | [Arxiv](https://arxiv.org/abs/2503.19877) |
| Learning to Plan & Reason for Evaluation with Thinking-LLM-as-a-Judge | 30 Jan 2025 | [Arxiv](https://arxiv.org/abs/2501.18099)|
| PairJudge RM: Perform Best-of-N Sampling with Knockout Tournament | 22 Jan 2025 | [Arxiv](https://arxiv.org/abs/2501.13007)|
| Self-Generated Critiques Boost Reward Modeling for Language Models | 25 Nov 2024 | [NAACL](https://arxiv.org/abs/2411.16646) |
| Beyond Scalar Reward Model: Learning Generative Judge from Preference Data | 01 Oct 2024 | [Arxiv](https://arxiv.org/abs/2410.03742v2) |
| Generative Verifiers: Reward Modeling as Next-Token Prediction | 27 Aug 2024 | [ICLR](https://arxiv.org/abs/2408.15240)|
| Critique-out-Loud Reward Models | 21 Aug 2024 | [Arxiv](https://arxiv.org/abs/2408.11791) |
| Improving Reward Models with Synthetic Critiques | 31 May 2024 | [Arxiv](https://arxiv.org/abs/2405.20850) |


## Notes

### **Scaling Evaluation-time Compute with Reasoning Models as Process Evaluators**
链接：https://arxiv.org/abs/2503.19877 <br>
日期：2025年3月25日 <br>
单位：CMU等 <br>
简介：核心是比较全面地分析了在评价阶段，采用long CoT推理能力对于评价准确性的影响。这里的scaling主要是通过（1）将答案拆分成N个step，并对每个step进行long CoT评价；（2）答案整体也会做一次long CoT评价。本质是在long CoT基础上同时集成过程奖励模型(PRM)和结果奖励模型(ORM)的策略。ORM得分采用输出位置上”1”和“0”的logits的二元softmax，PRM每个step得分计算方式类似，但是PRM总分采用mean_logits。最后整体分数采用 $\alpha \rm{ORM} + (1-\alpha)\rm{PRM}$ 的加权形式，$\alpha$ 默认0.5。

<img width="860" alt="image" src="https://github.com/user-attachments/assets/bd55c2bd-1a51-4ed8-959f-4083f8c96145" />


