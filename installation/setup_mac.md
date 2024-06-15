## Setting Up a macOS Development Environment

**During this process you can use either mamba or conda command they do the same thing, I will use mamba for this guide.**

- **Visual Studio Code**: Install Visual Studio Code. [Download it here](https://code.visualstudio.com/download).

### Installation Steps

1. **Install Miniforge**:
   - We use Miniforge to manage different environments. During installation, agree to all prompts:
    ```bash
    curl -L -O "https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-$(uname)-$(uname -m).sh"
    bash Miniforge3-$(uname)-$(uname -m).sh 
    ```

2. **Set Up the Python Environment**:
   - Create and activate a new Mamba environment:
     ```bash
     mamba create -n torch_env python=3.10
     mamba activate torch_env
     ```
   - Install PyTorch and related packages:
     ```bash
     mamba install pytorch::pytorch torchvision torchaudio -c pytorch
     ```
   - install Ultralytics
     ```bash
     install -c conda-forge ultralytics
     ```
   - test PyTorch installation:
     ```bash
     python3
     import torch
     torch.rand(5, 5)
     ```
---