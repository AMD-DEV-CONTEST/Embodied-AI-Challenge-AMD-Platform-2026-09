# Radeon Cloud User Guide

[中文版本](./README.md)

This guide explains how to obtain an AMD Radeon GPU on [Radeon Cloud](https://developer.amd.com.cn/radeon/) and enter an environment for development, training, and inference.

This guide uses the latest interface screenshots in the `assets/` directory. If the platform UI changes, follow the actual page.

## Step 1: Log in

Open [Radeon Cloud](https://developer.amd.com.cn/radeon/), click **Login** in the top-right corner, and choose **Login with Email**.

![Radeon Cloud login page](./assets/login.png)

### Switch to the new design

After logging in, users are taken to the **Classic** design by default. Click **Switch to the new design** in the bottom-right corner of the page to switch to the **New** design.

![Radeon Cloud Classic design](./assets/classic_radeon_cloud.png)

![Radeon Cloud New design](./assets/new_radeon_cloud.png)

### Add your SSH public key

Add your SSH public key on the Profile page:

1. Generate a key pair locally if you do not already have one. This works on macOS, Linux, and Windows PowerShell:

   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```

   By default, this creates `~/.ssh/id_ed25519` (private key) and `~/.ssh/id_ed25519.pub` (public key).
2. Copy the public key content:

   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

3. Click **Settings**, then click **New SSH Key**.
4. Paste the public key into the SSH key field, then click **New SSH Key** to save it.

![Add an SSH public key in Profile](./assets/ssh-key.png)

> ⚠️ Copy only the `.pub` public key. Never upload or share the `id_ed25519` private key.

## Step 2: Enter the development environment

After logging in, configure the instance as follows:

1. Click **Customize**.
2. Select the GPU count according to your needs: **4 GPUs** or **8 GPUs**.
3. Select **robotwin** under **Image**.
4. Under **Resource Pool**, select the resource pool for this competition: **Dev**.
5. Under **Workspace Storage**, select **Persistent /workspace**.
6. Select **Devzone** under **Mount a model**.

![Instance configuration: Customize, 4/8 GPUs, robotwin, and Devzone](./assets/launch.png)

After completing the configuration, enter the instance. When the page shows **Your workspace is ready**, the instance has started successfully.

### JupyterLab

Click **Open Notebook**. JupyterLab opens in a new browser tab. Use its Terminal, Notebook, and File browser for development.

![Open Notebook](./assets/open-notebook.png)

JupyterLab provides:

- **Terminal** for installing dependencies, downloading files, and starting services. Click `+` at the top and select Terminal.
- **Notebook (`.ipynb`)** for interactive code and output.
- **File browser** for uploading and managing files.

![JupyterLab workspace](./assets/jupyterlab.png)

### SSH access

When the instance shows **Instance running**, click it and copy the connection information from the SSH window. Connect from a local terminal:

```bash
ssh <user>@<host> -p <port>
```

Replace `<user>`, `<host>`, and `<port>` with the actual values shown on the page.

![SSH access and connection details](./assets/ssh-connect.png)

## Step 3: Destroy the instance

A running instance continuously consumes credits. When finished, open **Active Instance** in Profile and click the red **Destroy Instance** button.

![Destroy instance](./assets/destroy-instance.png)

## Step 4: Robotwin Reference

You can refer to [Robotwin-radeon-cloud](https://github.com/ZiguanWang/Robotwin-radeon-cloud) to run simple Robotwin experiments on Radeon Cloud, including:

- Robotwin closed-loop benchmark: run closed-loop tasks and evaluate robot policy performance.
- LoRA training: perform parameter-efficient fine-tuning with LoRA.
- Full-parameter SFT training: run supervised fine-tuning with all model parameters.

Refer to the example repository for the exact environment setup, data preparation, training commands, and evaluation procedures.
