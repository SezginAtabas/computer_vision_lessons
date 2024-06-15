
## Setting Up a WSL Development Environment

**During this process you can use either mamba or conda command they do the same thing, I will use mamba for this guide.**

This guide provides step-by-step instructions for setting up a Windows Subsystem for Linux (WSL) environment, tailored for development purposes.

### Prerequisites

- **Visual Studio Code**: Install Visual Studio Code on Windows to interface with WSL for development. [Download it here](https://code.visualstudio.com/download).

### Installation Steps

1. **Connect Visual Studio Code to WSL**:
   - After installing VS Code, add the Remote Development extension pack.
   - Use the shortcut `Ctrl + Shift + P`, type `Connect to WSL`, and execute the command to connect.

2. **Install Ubuntu 22.04 LTS on WSL**:
   - Open Command Prompt and run the following command to install Ubuntu:
     ```cmd
     wsl --install -d Ubuntu-22.04
     ```
   - Update the WSL kernel:
     ```cmd
     wsl --update
     ```
   - Launch WSL via Command Prompt:
     ```cmd
     wsl
     ```

3. **Update Packages**:
   - Ensure all installed packages are up to date:
     ```bash
     sudo apt-get update && sudo apt-get full-upgrade
     ```

4. **Install CUDA Toolkit**:
   - Download and install the CUDA Toolkit for use within WSL:
     ```bash
     wget wget https://developer.download.nvidia.com/compute/cuda/repos/wsl-ubuntu/x86_64/cuda-keyring_1.1-1_all.deb
     sudo dpkg -i cuda-keyring_1.1-1_all.deb
     sudo apt-get update
     sudo apt-get -y install cuda-toolkit-12-5
     ```
   - Reboot WSL by shutting it down and starting it up again:
     ```cmd
     wsl --shutdown
     wsl
     ```

5. **Install Miniforge**:
   - Use Miniforge to manage different environments. During installation, agree to all prompts:
    ```bash
    curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
    bash Miniforge3-$(uname)-$(uname -m).sh 
    ```

6. **Set Up the Python Environment**:
   - Create and activate a new Mamba environment:
     ```bash
     mamba create -n torch_env python=3.10
     mamba activate torch_env
     ```
   - Install PyTorch and related packages:
     ```bash
     mamba install pytorch torchvision torchaudio pytorch-cuda=12.1 ultralytics -c pytorch -c nvidia
     ```
    - test PyTorch installation:
    ```bash
    python3
    import torch
    torch.cuda.is_available()
    torch.rand(5, 5)
    ```
---
