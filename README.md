# Embodied-AI-Challenge-AMD-Platform-2026-09

[English version](./README_en.md)

# 蚂蚁灵波具身大模型挑战赛 · AMD Radeon GPU 算力支持指南

本页面用于说明如何在「蚂蚁灵波具身大模型挑战赛」中获取 AMD Radeon GPU 算力资源，以及参赛开发者可享有的 AMD 专项福利。

作为本次赛事战略合作伙伴，AMD 将为参赛开发者提供基于 Radeon Cloud 平台 W7900D GPU（48GB GDDR6）和 ROCm 开源 AI 软件栈的开发资源支持，帮助开发者在 AMD 平台完成模型后训练，并进行 Robotwin 任务评测。赛事期间，符合条件的参赛者均可申请 AMD 专项算力资源。

## 一、如何获取 AMD Radeon GPU 资源

### Step 1：完成赛事报名

比赛入口：https://tianchi.aliyun.com/competition/entrance/532514

### Step 2：完成 AMD 开发者计划注册

![专属 ADP 注册二维码](./lingbot_contest_ADP.jpg)

或访问以下链接完成 AMD 开发者计划（ADP）注册：

https://developer.amd.com.cn/login?source=sSEUZ7cAA

### Step 3：加入官方比赛交流群

完成报名与 ADP 注册后，加入赛事官方交流群，获取算力申请入口及后续通知。

### Step 4：由团队代表提交 GPU 资源申请

完成赛事报名、AMD 开发者计划注册、并加入官方比赛交流群后，可由团队代表申请赛事专属 Radeon GPU 资源，申请时需提供AMD ADP会员ID。

> **重要：** AMD 将为符合条件的参赛队伍提供专属 Radeon GPU Credits，无需自备训练算力即可参与赛事开发与测试。具体的算力申请与使用规则请参阅 [AMD 算力申请与使用规则](./Radeon-Cloud-User-Guide/AMD_VLA_Contest_Compute_Rules.md)。

算力平台开放时间：**2026 年 9 月 15 日 14:00 至 10 月 26 日 20:00**。基础提供 **200 张 GPU**，后期将根据活动优先级动态调整开放规模。算力仅限用于本次比赛用途，如有发现用于其他场景，将回收算力平台使用资格。

## 二、Radeon Cloud 使用指南

Radeon Cloud 的登录、实例配置、JupyterLab 使用和实例销毁流程，请参阅 [Radeon Cloud User Guide](./Radeon-Cloud-User-Guide/README.md)。

AMD Radeon GPU 可用于：

- Robotwin 任务评测
- LingBot-VLA 2.0 模型复现与训练

## Robotwin 参考

可以参考 [Robotwin-radeon-cloud](https://github.com/ZiguanWang/Robotwin-radeon-cloud)，在 Radeon Cloud 上进行简单的 Robotwin 实验，包括：

- Robotwin closed-loop benchmark：运行闭环任务并评估机器人策略表现。
- LoRA training：使用 LoRA 进行参数高效微调。
- Full-parameter SFT training：进行全参数监督微调训练。

具体环境配置、数据准备、训练命令和评测流程请以参考仓库说明为准。

## 三、AMD 开发者专项福利总览

| 福利项 | 说明 |
| --- | --- |
| 专属算力 | 符合条件的参赛队伍均可获得 AMD Radeon GPU Credits |
| 开发环境 | AMD Radeon Cloud 平台提供 W7900D GPU（48GB GDDR6）+ ROCm 开源 AI 软件栈 |
| 积分奖励 | 通过 AMD 平台完成作品开发并提交赛事成果，可获得额外 AMD 开发者积分，有机会兑换额外免费算力 |
| 官方曝光 | 优秀项目有机会获得 AMD 官方开发者社区专题报道、技术直播分享计划、ROCm 社区曝光等资源 |
| 实物大奖 | 特别优秀的作品将有机会在决赛获得 AMD Radeon 显卡实物大奖 |
| 内容互动激励 | 在小红书分享 AMD 平台开发实践并 @AMD 开发者中心账号，优质内容有机会获得官方转发、社区推荐及 Spotlight 展示 |

## 四、AMD 开发者内容互动激励（小红书）

AMD 同样鼓励参赛选手记录基于 AMD Radeon GPU 与 ROCm 开源软件栈的开发实践，并在小红书分享参赛心得、技术教程、模型训练经验、性能优化成果、真机调试过程及创新 Demo 展示内容。

发布内容时，可带话题 #AMDev #ROCm #AMDAI，并关注及 @AMD开发者中心 账号。

AMD 将定期选取优质开发者内容进行官方转发、社区推荐及 Spotlight 展示。

## 五、AMD GPU 算力问题咨询

如在申请或使用 AMD Radeon GPU Credits 过程中遇到问题，欢迎扫码咨询 AMD 算力支持团队。

![AMD GPU 算力支持团队二维码](./AMD_GPU_support_group.jpg)
