# Flexynesis: A deep learning toolkit for bulk multi-omics data integration for precision oncology and beyond

## Defination

Cell Invasion(细胞侵袭)：细胞主动穿越周围屏障结构（基底膜、细胞外基质）并且进入临近组织
常见于 癌细胞转移、免疫细胞穿越血管壁
案例 乳腺癌细胞侵入基底膜→穿过基质→进入血管→形成转移灶

Cell Infiltration(细胞浸润)：大量细胞从血液 或 临近组织进入某个 组织或器官，代表一种炎症或免疫反应
常见于 肿瘤组织中的免疫细胞浸润（Tumor-Infiltration Lymphocytes, TILs）
响应与预后相关：高水平的CD8 T细胞浸润→往往提示 免疫活跃性肿瘤→对免疫检查点抑制剂可能更敏感

Supervision Heads(监督头)：用于输出并计算训练目标（loss）的模块或层，监督学习中通常对应着希望模型预测的目标值

Symmetric Encoder-Decoder(对称自编码器)：将高维输入数据压缩为低维隐藏表示，典型的Autoencoder结构，输入与输出属于同一模态
![image-20251111141458050](/Users/edwardchan/Library/Application Support/typora-user-images/image-20251111141458050.png)

Fully Connected Network, FNC(全连接网络)：也叫**多层感知机**（Multi-Layer Perception, MLP）
每个神经元接收前一层所有节点的输出，每个连接有一个权重，每个神经元有一个偏置，经过激活函数后传给下一层

## Existing Problem

Limited reusability or adaptability to different datasets and contexts.

Do not provide accompanying code.

## Advantages

Versability of Flexynesis: Drug response prediction, cancer subtype modelling, survival analysis, biomarker discovery

# [Optimal](https://jamanetwork.com/journals/jama/fullarticle/2831858《Optimal) Vasopressin Initiation in Septic Shock The OVISS Reinforcement Learning Study

## Object

The decision rule for when to initiate AVP specifically, at what hour and under what condition-is evaluated to determine whether it outperforms the average physician practice(primarily accessed by **in-hospital** mortality rates)

## Data input

Time sequence: From the "shock-onset", divided into epochs at **1-hour** intervals

Features: Record a set of time-varying variables every hour, **totaling 14 core characteristics** (vital signs, laboratory values, organ support, etc.). If a measurement is **not recorded** for a given hour, the **previous hour's value is carried forward**. If multiple measurements are recorded for the same hour, the average is taken.

Action: **Binary decision.** Only focus on **initiate timing**.

## Results

RL Rules: Initiating AVP "**in more patients and earlier**"
Approximate recommendation rate: 87%(physicians: 31%), 
Earlier initiation (median 4 hours vs. 5 hours), 
Initiation at lower NE doses (0.20 vs. 0.37 μg/kg/min)