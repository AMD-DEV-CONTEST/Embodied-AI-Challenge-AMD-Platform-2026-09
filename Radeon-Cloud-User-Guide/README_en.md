# Radeon Cloud User Guide

[中文版本](./README.md)

This guide explains how to obtain an AMD Radeon GPU on [Radeon Cloud](https://radeon-global.anruicloud.com/) and enter an environment for development, training, and inference.

This guide uses the latest interface screenshots in the `assets/` directory. If the platform UI changes, follow the actual page.

## Step 1: Log in

Open [Radeon Cloud](https://radeon-global.anruicloud.com/), click **Login** in the top-right corner, and choose **Login with Email**.

![Radeon Cloud login page](./assets/login.png)

## Step 2: Enter the development environment

After logging in, configure the instance as follows:

1. Click **Customize**.
2. Select a suitable number of GPUs; **4 GPUs** is recommended.
3. Select **robotwin** under **Image**.
4. Select **Devzone** under **Mount a model**.

![Instance configuration: Customize, 4 GPUs, robotwin, and Devzone](./assets/launch.png)

After completing the configuration, enter the instance. When the page shows **Your workspace is ready (100%)**, click **Open Notebook**.

### JupyterLab

JupyterLab opens in a new browser tab. Use its Terminal, Notebook, and File browser for development.

![Open Notebook](./assets/open-notebook.png)

JupyterLab provides:

- **Terminal** for installing dependencies, downloading files, and starting services. Click `+` at the top and select Terminal.
- **Notebook (`.ipynb`)** for interactive code and output.
- **File browser** for uploading and managing files.

![JupyterLab workspace](./assets/jupyterlab.png)

## Step 3: Destroy the instance

A running instance continuously consumes credits. When finished, open **Active Instance** in Profile and click the red **Destroy Instance** button.

![Destroy instance](./assets/destroy-instance.png)

## Step 4: Robotwin Reference

You can refer to [Robotwin-radeon-cloud](https://github.com/ZiguanWang/Robotwin-radeon-cloud) to run simple Robotwin experiments on Radeon Cloud, including:

- Robotwin closed-loop benchmark: run closed-loop tasks and evaluate robot policy performance.
- LoRA training: perform parameter-efficient fine-tuning with LoRA.
- Full-parameter SFT training: run supervised fine-tuning with all model parameters.

Refer to the example repository for the exact environment setup, data preparation, training commands, and evaluation procedures.
