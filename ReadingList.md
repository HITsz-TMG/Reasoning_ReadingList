# Reasoning
* [Neuro-symbolic reasoning](#neuro-symbolic)
    * [2022](#2022)
    * [2020](#2020)
    * [2016](#2016)
* [Commonsense reasoning](#commonsense)
    * [2022](#2022-1)
    * [2020](#2020-1)
* [Graph reasoning](#graph)
    * [2022](#2022-2)
    * [2020](#2020-2)

## Neuro-symbolic reasoning

### 2022
1. **An Interpretable Neuro-Symbolic Framework for Task-Oriented Dialogue Generation.** ACL. [[code](https://github.com/shiquanyang/NS-Dial)] [[pdf](https://arxiv.org/abs/2203.05843)]

    *Shiquan Yang, Rui Zhang, Sarah Erfani, Jey Han Lau*

2. **AdaLoGN: Adaptive Logic Graph Network for Reasoning-Based Machine Reading Comprehension** ACL. [[code](https://github.com/nju-websoft/AdaLoGN)] [[pdf](https://arxiv.org/pdf/2203.08992.pdf)]

    *Xiao Li, Gong Cheng, Ziheng Chen, Yawei Sun, Yuzhong Qu*

### 2020
1. **Conversational Neuro-Symbolic Commonsense Reasoning.** AAAI. [[code, data](https://github.com/ForoughA/CORGI)] [[pdf](https://arxiv.org/abs/2006.10022)]

    *Forough Arabshahi, Jennifer Lee, Mikayla Gawarecki, Kathryn Mazaitis, Amos Azaria, Tom Mitchell*

    提出了一个数据集，把数据转化成"if...then...because..."的形式，任务目标是推理出合适的"because..."以实现从"if"到"then"的推理证明。首先参考了Prolog进行了文本的转化，再使用symbolic的方法进行了目标的解耦与组合，并使用neuro的方式来gap不同表述的相似前提对于KB中既定事实的差异。实际操作中采用了树状深搜的策略来确定合理的推理证明。

### 2016
1. **Logic Tensor Networks: Deep Learning and Logical Reasoning from Data and Knowledge** Arxiv. [[pdf](https://arxiv.org/pdf/1606.04422.pdf)]

    *Luciano Serafini, Artur d'Avila Garcez*

## Commonsense reasoning

### 2022
1. **Diversifying Content Generation for Commonsense Reasoning with Mixture of Knowledge Graph Experts.** Findings of ACL. [[code](https://github.com/DM2-ND/MoKGE)][[pdf](https://arxiv.org/abs/2203.07285)]

    *Wenhao Yu, Chenguang Zhu, Lianhui Qin, Zhihan Zhang, Tong Zhao, Meng Jiang*

### 2020
1. **Conversational Neuro-Symbolic Commonsense Reasoning.** AAAI. [[code, data](https://github.com/ForoughA/CORGI)] [[pdf](https://arxiv.org/abs/2006.10022)]

    *Forough Arabshahi, Jennifer Lee, Mikayla Gawarecki, Kathryn Mazaitis, Amos Azaria, Tom Mitchell*

## Graph reasoning
KG reasoning can be roughly categroized according to the following two tasks: first, inference of missing triples(KG completion or link prediction), and second, predicting the truth value of triples(triple classification). (Written in **Reasoning on Knowledge Graphs with Debate Dynamics**[[pdf](https://arxiv.org/pdf/2001.00461.pdf)])
### 2022
1. **Towards Large-Scale Interpretable Knowledge Graph Reasoning for Dialogue Systems.** Findings of ACL. [[pdf](https://arxiv.org/abs/2203.10610)]

    *Yi-Lin Tuan, Sajjad Beygi, Maryam Fazel-Zarandi, Qiaozi Gao, Alessandra Cervone, William Yang Wang*

### 2020
1. **Reasoning on Knowledge Graphs with Debate Dynamics** AAAI. [[code](https://github.com/m-hildebrandt/R2D2)][[pdf](https://arxiv.org/pdf/2001.00461.pdf)]

    *Marcel Hildebrandt, Jorge Andres Quintero Serna, Yunpu Ma, Martin Ringsquandl, Mitchell Joblin, Volker Tresp*

    本篇工作聚焦于使用Debate Dynamics的方法解决知识图谱补全任务中的三元组分类问题。大体上可以理解为两个持相反态度的agents对于某一具体三元组事实进行双向论证（即事实是否成立），并由judge通过两个agents的推理过程做出最后的判断。训练采用了强化学习的方法。ps: 本文第二部分对入门者来说很棒。作者对知识图谱定义，问题定义以及相关工作都有非常清楚的表述。

2. **Grounded Conversation Generation as Guided Traverses in Commonsense Knowledge Graphs** ACL. [[code](https://github.com/thunlp/ConceptFlow)] [[pdf](https://arxiv.org/pdf/1911.02707.pdf)]

    *Houyu Zhang, Zhenghao Liu, Chenyan Xiong, Zhiyuan Liu*
    
    感觉是很有启发性的工作。作者设计ConceptFlow的模型，它利用常识知识图谱对会话流进行显式建模。论文将Zero-hop的节点表示与One-hop, Two-hop的节点表示（最多到2跳）分别作为Central Graph和Outer Graph进行encoding，同时也设计了合适的attention方式来对encoding效果进行优化。在输出端，通过gate来判断具体使用哪一块的输出。实验相当充分，效果也很好。

3. **Knowledge Aware Conversation Generation with Explainable Reasoning on Augmented Graphs** EMNLP. [[pdf](https://arxiv.org/pdf/1903.10245v2.pdf)]

    *Zhibin Liu, Zheng-Yu Niu, Hua Wu, Haifeng Wang*
    论文采用了基于强化学习的推理模型MINERVA来实现知识选择模块，以此推理过程模拟会话中的知识跳转过程（基于路径选择的推理）。ps: 很多时候都是采用强化学习的方法以实现基于路径选择的推理方式。个人认为这是因为很难在对话过程中提供一个有效的监督信号；若是能够在对话历史中有效建模用于路径选择推理的监督信号，将会较好地提高该推理方式的效果。
