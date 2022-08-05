# PaddleNLP Transformer Model Zoo

随着深度学习的发展，NLP 领域涌现了一大批高质量的 Transformer 类预训练模型，多次刷新了不同 NLP 任务的 SOTA（State of the Art），极大地推动了自然语言处理的进展。PaddleNLP 提供了常用的预训练模型及其相应权重，包含百度自研模型和 NLP 社区开源模型，共计 50 多个主流模型、500 多个模型权重。

`model_zoo`精选开发者最常用的预训练模型，打通**模型预训练-微调-效果与性能加速-模型部署**全流程，提供各模型在多场景任务上的最佳实践，旨在为开发者提供极致的使用体验。

## 自研模型

- **ERNIE 3.0**

在文心大模型 ERNIE 3.0 基础上通过在线蒸馏技术得到的轻量级模型，包含多个不同尺寸的小模型，刷新了中文小模型的 SOTA 成绩。    
参考论文：[ERNIE-Tiny: A Progressive Distillation Framework for Pretrained Transformer Compression](https://arxiv.org/abs/2106.02241)

- **UIE**

通用信息抽取技术 UIE 实现了实体抽取、关系抽取、事件抽取、情感分析等任务的统一建模，使得模型在不同任务间具备良好的迁移和泛化能力。PaddleNLP 基于 ERNIE 3.0 知识增强预训练模型，开源了首个中文通用信息抽取模型 UIE，该模型可以支持不限定行业领域和抽取目标的关键信息抽取，实现零样本快速冷启动，并具备优秀的小样本微调能力，快速适配特定的抽取目标。     
参考论文：[Unified Structure Generation for Universal Information Extraction](https://arxiv.org/pdf/2203.12277.pdf)

- **ERNIE-Doc**

长文本理解模型 ERNIE-Doc 首创回顾式建模技术，突破了 Transformer 在文本长度上的建模瓶颈，实现了任意长文本的双向建模，模型具备超长文本的建模能力。    
参考论文：[ERNIE-Doc: A Retrospective Long-Document Modeling Transformer](https://aclanthology.org/2021.acl-long.227.pdf)


- **ERNIE-M**

多语言模型 ERNIE-M 采用了一种新颖的跨语言预训练方法，可利用单语语料库学习多种语言之间的语义对齐。具备96种语言的理解能力，在五个跨语言的下游任务和 XTREME 上均得到了 SOTA。   
参考论文：[ERNIE-M: Enhanced Multilingual Representation by Aligning
Cross-lingual Semantics with Monolingual Corpora](https://arxiv.org/pdf/2012.15674.pdf)

- **ERNIE-Health**

医疗预训练语言模型 ERNIE-Health 共学习了 60 多万的医疗专业术语和 4000 多万的医疗专业问答数据，以超越人类医学专家水平的成绩登顶中文医疗信息处理权威榜单 CBLUE 冠军，具备对医疗专业知识强大的理解和建模能力。    
参考论文：[Building Chinese Biomedical Language Models via Multi-Level
Text Discrimination](https://arxiv.org/pdf/2110.07244.pdf)

- **UNIMO-Text**

UNIMO 提出统一模态学习方法，同时解决单模与多模任务。UNIMO-Text 是 UNIMO 在文本单模态上的预训练模型，适用于文本摘要、问题生成等各类文本生成任务。    
参考论文：[UNIMO: Towards Unified-Modal Understanding and Generation via Cross-Modal Contrastive Learning](https://arxiv.org/pdf/2012.15409v4.pdf)

- **PLATO-XL**

PLATO-XL 是业界首个开源的百亿超大规模开放域对话预训练模型，其使用了参数共享（encoder-decoder 共享参数）的 UnifiedTransformer（prefix LM）模型架构，将模型参数量提升到了 11B 量级，经过了十亿级样本对话数据的预训练，并引入 role embedding 区分多方对话中的对话角色提升预训练效果，最终模型闲聊测试效果超过了众多代表性的对话模型，可以直接使用 PLATO-XL 构建高质量的开放领域对话机器人。

参考论文：[PLATO-XL: Exploring the Large-scale Pre-training of Dialogue Generation](https://arxiv.org/pdf/2109.09519.pdf)


## 社区模型


- **BERT**

最经典的预训练模型之一，以 Transformer 编码器为网络基本组件，针对掩码语言模型（Masked Language Model）和邻接句子预测（Next Sentence Prediction）两个任务在大规模无标注文本语料上进行预训练（pre-train），得到融合了双向内容的通用语义表示模型。    
参考论文：[BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/pdf/1810.04805.pdf)

- **ELECTRA**

ELECTRA 在 BERT 的基础上对其预训练过程进行了改进：预训练由 Generator 和 Discriminator 两部分网络组成，各自包含1个BERT模型。在多个NLP任务上效果优于BERT。     
参考论文：[ELECTRA: PRE-TRAINING TEXT ENCODERS AS DISCRIMINATORS RATHER THAN GENERATORS](https://arxiv.org/pdf/2003.10555.pdf)

- **GPT**

GPT-2/3 是以Transformer 解码器为网络基本组件，使用自回归的方式在大规模无标注文本语料上进行预训练得到的语言生成模型，适用于各类文本生成任务。

参考论文：[Language Models are Few-Shot Learners](https://arxiv.org/pdf/2005.14165.pdf)

- **TinyBERT**

TinyBERT 提出了两阶段的知识蒸馏方法，分别在预训练阶段和针对特定任务的学习阶段执行 transformer 蒸馏。该蒸馏方法可应用于BERT、ERNIE等预训练模型。   
参考论文：[TinyBERT: Distilling BERT for Natural Language Understanding](https://arxiv.org/pdf/1909.10351.pdf)
