# Radeon Cloud 用户指南

[English version](./README_en.md)

本指南介绍如何在 [Radeon Cloud](https://radeon-global.anruicloud.com/) 上申请 AMD Radeon GPU，并进入开发、训练和推理环境。

本文使用 `assets/` 目录中的最新界面截图；平台界面如有变化，请以实际页面为准。

## 1. 登录

打开 [Radeon Cloud](https://radeon-global.anruicloud.com/)，点击 **Login → Login with Email** 完成登录。

![Radeon Cloud 登录页面](./assets/login.png)

## 2. 进入开发环境

登录后，在实例配置页面依次完成以下选择：

1. 点击 **Customize**。
2. 选择合适的 GPU 数量，推荐选择 **4 GPUs**。
3. 在 **Image** 中选择 **robotwin**。
4. 在 **Mount a model** 中选择 **Devzone**。

![实例配置：Customize、4 GPUs、robotwin 和 Devzone](./assets/launch.png)

配置完成后进入实例，待页面显示 **Your workspace is ready (100%)**，点击 **Open Notebook**。

### 使用 JupyterLab

浏览器会打开 JupyterLab。在其中可以使用 Terminal、Notebook 和 File browser 完成开发工作。

![Open Notebook](./assets/open-notebook.png)

![JupyterLab 工作区](./assets/jupyterlab.png)

## 3. 销毁实例

使用完成后进入 Profile 的 **Active Instance**，点击红色 **Destroy Instance**，避免实例继续消耗积分。

![销毁实例](./assets/destroy-instance.png)

## 4. Robotwin 参考

可以参考 [Robotwin-radeon-cloud](https://github.com/ZiguanWang/Robotwin-radeon-cloud)，在 Radeon Cloud 上进行简单的 Robotwin 实验：

- **Robotwin closed-loop benchmark**：运行闭环任务并评估机器人策略表现。
- **LoRA training**：使用 LoRA 进行参数高效微调。
- **Full-parameter SFT training**：进行全参数监督微调训练。

具体环境配置、数据准备、训练命令和评测流程请以参考仓库说明为准。
