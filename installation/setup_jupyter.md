## Setting up Jupyter

**During this process you can use either mamba or conda command they do the same thing, I will use mamba for this guide**

1. install jupyter lab
```bash
# activate the environment.
mamba activate torch_env

# install Jupyter lab
mamba install jupyterlab
```

2. Install vscode jupyter extension
go to extensions (ctrl + shift + x), type type jupyter in search bar, install the Jupyter extension.

3. You can use either jupyterlab or mamba environment or jupyterlab kernel when running notebooks.

    for running with jupyter lab:
    ```bash
    jupyter lab
    ```
    Then copy the link, click choose kernel on top right of any notebook then select `existing jupyter server` and paste the link.

    To run directly using mamba env:
    Click choose kernel on top right of any notebook, select `python environments`then choose your mamba environment.

    NOTE: you may need to add your the folder folder you installed the enviroment to. You can select by:
    1. ctrl + shift + p , then type `Preferences: Open settings (UI)` and click it.
    2. In the settings search bar type `venv path ` you will see a setting called `Python: Venv Path`
    3. Enter the path to the folder that stores your created environments. In miniforge by default this is `/home/your_user_name/miniforge3/envs`.

    