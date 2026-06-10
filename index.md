# 凌致新
男 | 行业：多模态大模型/推荐大模型
联系方式：13262792461（微信同号） | 邮箱：1069066484@qq.com  
个人主页：[凌致新个人主页](https://1069066484.github.io) | [Google Scholar主页](https://scholar.google.com/citations?user=-YEHw9gAAAAJ&hl=en)
当前岗位：快手-模型与应用部 推荐大模型组


## 教育经历
- **2020.09 ~ 2023.06** 复旦大学 软件工程 硕士
  - 核心绩点：3.60/4.00，核心绩点排名：12/47（25.53%）
  - 荣誉：上海市优秀毕业生
- **2016.09 ~ 2020.06** 上海交通大学 计算机科学与技术 学士
  - 核心学积分：89.49/100，核心学积分排名：29/146
  - 核心绩点：3.82/4.30，核心绩点排名：30/146（20.55%）


## 核心技术栈
- **模型架构**：ViT、DiT、Swin Transformer、UMM、MLLM、LLM4Rec、时序模型、图像检索、目标检测、图像生成
- **工程能力**：分布式训练（FSDP/SP/DP/Megatron）、大规模数据处理、训练基建搭建、自动化评估系统、模型转换与部署、量化加速
- **工具与语言**：Pytorch、SQL


## 工作经历
### 2024.04-至今 快手 模型与应用部 推荐大模型组
1. **[2026.02-至今 OneReason-8B推荐大模型 预训练方向主R](https://arxiv.org/abs/2606.06260)**
   - 主导业内首个CoT-推荐大模型的预训练体系搭建，设计多粒度预训练数据架构(Token→Item→Relational→User)
   - 几乎从零构建推荐域预训练语料（60B→417B），引入数据清洗、数据重标注、数据合成等全流程数据优化方案
   - 物料锚定相对提升160%，推荐核心指标相对提升65%；在快手本地生活业务落地，实现线上广告营收增幅超8%

2. **[2025.11-2026.01 Kelix-8B统一生成理解模型 预训练主训](https://arxiv.org/abs/2602.09843)**
   - 实现首个"理解-生成性能平衡"的完全离散自回归统一多模态架构，解决离散视觉token长期存在的信息瓶颈问题，核心创新为平行码本量化（PQ）+下一块预测（NBP）范式结合
   - 设计8并行子码本的PQ视觉tokenizer，验证理解性能随并行度scaling的关键特性，且该设计几乎不引入额外训推成本；基于SANA-DiT构建生图模块，支持1024×1024高分辨率图像生成
   - 完成SimVQ Tokenizer、LLM、DiT三个模块的全流程发版训练与联调
   - 模型在OCRBench达到86.7分（超越Qwen2.5-VL-7B的86.4），GenEval 87.6分（同期纯离散UMM中的SOTA），首次实现UMM理解性能追平并超越连续特征VLM

3. **[2025.08-2025.10 KeyeVL-671B-A37B视频理解模型 预训练主训](https://huggingface.co/Kwai-Keye/Keye-VL-671B-A37B)**
   - 负责当时国内最大开源视频理解模型（671B总参数、37B激活参数）的预训练工作，基于DeepSeek-V3-Terminus架构，搭载SlowFast架构的KeyeViT实现128K上下文长视频理解
   - 完成dataloader核心代码开发，基于Megatron框架完成三阶段KeyeVL-671B发版预训练
   - 实现KeyeVL-671B HuggingFace checkpoint初始化、Megatron格式双向转换及正确性验证，牵头对齐训推一致性
   - 模型在Video-MME达到73.0分，Video-MMMU达到66.0分，全面超越开源同级别模型

4. **[2025.06-2025.08 KeyeVL-1.5-8B视频理解模型 预训练主训](https://arxiv.org/abs/2509.01563)**
   - 搭建FSDP+UP混合并行训练框架，支持128K长序列多模态模型训练；基于该框架同步开发OpenOneRec系列推荐大模型训练基建
   - 主导序列扩长训练策略设计，在第三阶段平滑实现序列长度扩展；通过优化token配比解决MOE负载爆炸问题，同时平衡视觉理解与语言能力
   - 设计基于样本计算复杂度的动态负载均衡策略，无需预先组batch即可实时启动实验，硬件利用率提升30%；实现基于文件粒度的全局shuffle与样本粒度的local shuffle，以及样本级完美断点续训机制
   - 搭建全链路自动化评估与监控系统，模型在同尺寸模型中取得SOTA效果：Video-MMMU 66.0分（较Preview版提升8.4分），LongVideoBench 66.0分，MathVista 81.2分

5. **[2025.02-2025.06 KeyeVL-preview-8B模型 预训练主训](https://huggingface.co/Kwai-Keye/Keye-VL-8B-Preview)**
   - 从零建设Keye系列大模型的训练（FSDP+SP）、评估（vlmevalkit）基础设施，可支持72B稠密模型全流程训练
   - 模型在MMBench达到92.0分，MMMU_val 71.4分，为后续KeyeVL-1.5及671B版本奠定完整技术基础

6. **2024.08-2025.01 端到端多模态推荐大模型 主R**
   - 提出端到端使用短视频多模态内容代替传统ID训练精排模型的方案，将视频视觉、音频、文本表征深度融入精排模型
   - 设计视频去重与端到端训练优化策略，实现高吞吐训练，离线WUAUC取得0.5%的显著提升，为后续生成式推荐探索提供核心技术验证

### 2023.07-2024.03 度小满金融 数据智能应用部 用户增长组
- 实现四个核心序列模型（征信报告序列模型、内部序列模型、埋点序列模型和APPLIST序列模型），支撑多个核心业务需求
- 开发并上线多个业务预测模型，包括需求模型、放款预测模型、小微流水预测模型和年化风险预测模型


## 实习经历
- **2023.03-至今 灵均投资（600亿私募） 量化策略研究实习生**
  - 基于K线图与金融时序数据，挖掘预测股票涨跌的深度学习因子
- **2022.04-2022.10 字节跳动 计算机视觉实习生**
  - 探索广告海报前景物体生成技术，优化广告素材合成效果
  - 构建行业级配色数据集，实现图片中背景与前景物体的配色自动提取
  - 开发广告海报文案检索系统，支持广告海报的自动化合成


## 科研成果
### 代表性一作论文
1. [PanoSwin: a Pano-style Swin Transformer for Panorama Understanding](https://github.com/1069066484/PeronalOpenFiles/raw/main/%E9%99%84%E4%BB%B610-CVPR23_PanoSwin_A_Pano-style_Swin_Transformer_for_Panorama_Understanding.pdf)，CVPR 2023（CCF A）
2. [Multi-Level Region Matching for Fine-Grained Sketch-Based Image Retrieval](https://github.com/1069066484/PeronalOpenFiles/blob/main/%E9%99%84%E4%BB%B61-ACMMM2022_Multi_Level_Region_Matching_for_Fine_Grained_Sketch_Based_Image_Retrieval.pdf)，ACMMM 2022（CCF A）
3. [Conditional Stroke Recovery for Fine-Grained Sketch-Based Image Retrieval](https://github.com/1069066484/PeronalOpenFiles/blob/main/%E9%99%84%E4%BB%B64-Conditional_Stroke_Recovery_for_Fine_Grained_Sketch_Based_Image_Retrieval.pdf)，ECCV 2022（CCF B）

### 其他合作与在投论文
4. [Zero-Shot Sketch-Based Image Retrieval with Structure-aware Asymmetric Disentanglement](https://github.com/1069066484/PeronalOpenFiles/blob/main/%E9%99%84%E4%BB%B62-CVIU2022_Zero_Shot_Sketch_Based_Image_Retrieval_with_Structure_aware_Asymmetric_Disentanglement.pdf)，CVIU 2022（CCF B）
   - 负责模型细化、全流程实验设计与验证及部分论文写作
5. [Few-shot Single-view 3D Reconstruction with Memory Prior Contrastive Network](https://github.com/1069066484/PeronalOpenFiles/blob/main/%E9%99%84%E4%BB%B69-ECCV22_Few_shot_Single_view_3D_Reconstruction_with_Memory_Prior_Contrastive_Network.pdf)，ECCV 2022（CCF B）
6. [DoveNet: Deep Image Harmonization via Domain Verification](https://github.com/1069066484/PeronalOpenFiles/blob/main/%E9%99%84%E4%BB%B63-CVPR2020_DoveNet_Deep_Image_Harmonization_via_Domain_Verification.pdf)，CVPR 2020（CCF A）
7. [SKP: Selective Knowledge Preservation for Zero-Shot Sketch-Based Image Retrieval](https://github.com/1069066484/PeronalOpenFiles/blob/main/%E9%99%84%E4%BB%B66-Selective_Knowledge_Preservation_for_Zero_Shot_sketch_based_image_retrieval.pdf)，在投
   - 提出有选择性的多尺度导师学习方法解决零示例草图-图像检索问题
   - 对图片进行多尺度分割，精准选择含目标物体的区域施加知识保留损失
   - 提出SketchMix和RandomThickening两种创新草图数据增强方法


## 工程项目
1. [将Yolo目标检测框架适配于全景图片目标检测](https://github.com/1069066484/PeronalOpenFiles/blob/main/%E9%99%84%E4%BB%B67-%E5%B0%86%E7%9B%AE%E6%A0%87%E6%A3%80%E6%B5%8B%E6%A1%86%E6%9E%B6%E9%80%82%E5%BA%94%E4%BA%8E%E5%85%A8%E6%99%AF%E5%9B%BE%E7%89%87%E7%9A%84%E7%9B%AE%E6%A0%87%E6%A3%80%E6%B5%8B%E9%97%AE%E9%A2%98.pptx)
   - 在数据增强、测试方法、边缘补充等维度进行针对性优化，解决全景图畸变导致的检测精度下降问题

2. [支持纹理压缩的全景图片展示系统](https://github.com/1069066484/PanoView)
   - 前端采用HTML+JS+THREE.js实现全景图片3D渲染
   - 后端用Python封装编译后的Basis压缩算法，大幅减少全景图片传输时间

3. [基于Qt5框架的双人贪吃蛇游戏](https://github.com/1069066484/DoubleSnake)
   - 支持两只贪吃蛇独立设置速度、难度和角色属性
   - 实现自带地图编辑器、多难度AI对战、PvP及局域网联机功能


## 工作兴趣与业务经验
- **工作兴趣**：目标检测、时序模型、全景图片理解、图像生成、多模态大模型、推荐大模型
- **业务经验**：广告创意生成、量化深度因子挖掘、金融风控建模、用户增长算法


## 公益实践经历
- 2021.3-2021.6，作为主要负责人参与烛心社福建蕉坑小学远程阅读项目
- 2021.7-2021.8，参与烛心社福建蕉坑小学支教项目，负责宣传小组工作
- 2021.9-2022.8，担任复旦大学大型公益性社团烛心社社长，组织上海公益行、虹口社区服务、福建远程阅读等多个大型公益项目，获得多项集体及个人荣誉


## 其他身份
AI创作UP主：[B站空间](https://space.bilibili.com/390033239)
