# Kaggle Playground-Series Season-5-Episode-11-Predicting-Loan-Payback

## 🌟 概述
### 项目描述
- 本项目基于信贷用户数据，通过特征工程与 XGBoost 模型构建，预测用户是否产生违约行为。模型旨在提升对高风险客户的识别能力，为金融风控提供可解释、可部署的参考方案。
### 核心任务
- 🛠 **频率编码**  
  利用特征本身的分布信息，将类别变量（Category）转换为数值变量（Frequency）。主要回答的问题是：这个类别在数据中有多常见？  
  适用场景：类别数量较多、强离散型变量  
  优点：轻量、可直接参与树模型训练  
- 🕳 **分箱**  
  将连续特征离散化，或者将已有分类变量的类别进行合并。主要回答的问题是：它属于哪个分组？  
- 🔄 **目标编码**  
   利用目标变量的信息，为每个类别创建一个最具预测性的数值编码。主要回答的问题是：在这个类别下，目标变量的期望是多少？	  
- 📏 **XGBosst分类器**  
  适合处理结构化数据中的复杂非线性关系，在本案例中使用AUC曲线来评估模型效果，本质上，XGBoost在这里扮演着"特征效果检测器"和"模型性能验证器"的双重角色。  
### 训练流程
- 🏗 数据划分 → 特征工程 → XGBClassifier 训练 → 模型预测 → 性能评估  

### 核心参数参考
| 参数 | 含义 | 作用 |
|-----|------|------|
| max_depth | 树深度 | 控制模型复杂度 |
| learning_rate | 学习率 | 决定每轮更新幅度 |
| n_estimators | 树数量 | 决定模型拟合能力 |
| subsample | 采样比例 | 提升泛化能力 |


### 📚 技术栈汇总

| 类别   | 工具 / 库          |
| ---- | --------------- |
| 数值计算 | pandas / numpy  |
| 模型构建 | xgboost         |
| 模型评估 | sklearn.metrics |
---

## 🛠️ 工具与第三方库依赖
```bash
# 核心库
pandas numpy matplotlib xgboost

# 进阶功能
XGBClassifier   # sklearn中xgboost模块的XGBClassifier函数
KFold           # K-折交叉验证
```
## 🙌 致谢
- **笔记来源1** [模型与主体部分](https://www.kaggle.com/code/yousefelshahat2/simple-xgboost-only-competition-data-s5e11)
- **笔记来源2** [目标编码与函数部分](https://www.kaggle.com/code/sidakou/simple-xgboost-baseline-for-loan-payback) 

## 📝 小结与可拓展方向

* XGBoost 对特征质量较敏感，特征工程会决定模型上限。
* 可进一步引入：
  * 树模型融合（LightGBM / CatBoost）
  * 信贷评分卡体系（Scorecard Scaling）
---
## ✨ 整理：KrisZheng @ GitHub
📅 更新日期：2025-11-10
