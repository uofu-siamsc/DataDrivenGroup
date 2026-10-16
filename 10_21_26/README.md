## Goal of today:
- Set up a development environment on your own laptop
- By the end you'll have a GitHub account and Git installed, and you'll be able to run Python code in a Jupyter notebook inside VS Code

Already have Python or Anaconda installed? You can keep it and skip step 3.

## Steps

### 1. Create a GitHub account
Sign up at [github.com](https://github.com/). Use an email you'll keep after graduation. You'll need it again in step 5.

### 2. Install Git
- **Windows:** Download the installer from [git-scm.com](https://git-scm.com/install/) and run it. The default options are fine, so just keep clicking **Next**.
- **Mac:** Open the **Terminal** app (press `Cmd + Space` and type "Terminal"), type `git --version`, and press Enter. If Git isn't installed yet, a pop-up will offer to install the "command line developer tools". Click **Install**.

### 3. Install Python
Download the latest Python 3 from [python.org/downloads](https://www.python.org/downloads/).
- **Windows:** Choose **Windows installer (64-bit)**. On the first screen of the installer, **check the box "Add python.exe to PATH"**, then click **Install Now**.
- **Mac:** Run the `.pkg` installer and accept the defaults.

### 4. Install VS Code and its extensions
1. Download and install [Visual Studio Code](https://code.visualstudio.com/).
1. Open VS Code and click the **Extensions** icon on the left sidebar (four small squares), or press `Ctrl + Shift + X` (Windows) / `Cmd + Shift + X` (Mac).
1. Search for and install these two extensions, both published by Microsoft:
   - **Python**
   - **Jupyter**

### 5. Link Git to your GitHub account
In VS Code, open a terminal from the top menu: **Terminal → New Terminal**. Type these two commands, replacing the text in quotes with your own name and **the same email you used for GitHub**:
```
git config --global user.name "Your Name"
git config --global user.email "your_github_email@example.com"
```
To check that it worked, run `git config --global --list`. You should see your name and email.

### 6. Make a test notebook
1. Make a folder for this workshop somewhere easy to find, for example `Documents/SIAM_workshop`.
1. In VS Code, go to **File → Open Folder...** and pick that folder. If it asks whether you trust the authors, click **Yes**.
1. Go to **File → New File...**, choose **Jupyter Notebook**, then save it (`Ctrl + S` / `Cmd + S`) as `test.ipynb`.
1. Click **Select Kernel** in the top right, then **Python Environments**, and choose the Python you installed in step 3 (the newest Python 3 version on the list).
1. Paste this into the first cell and run it by pressing `Shift + Enter`:
   ```
   %pip install numpy scipy matplotlib
   ```
   If VS Code says it needs to install `ipykernel`, click **Install**. Installing takes a minute or two.
1. Click **+ Code** to add a new cell, then paste this in and run it:
   ```python
   import numpy as np
   import scipy
   import matplotlib.pyplot as plt

   print("NumPy version:", np.__version__)
   print("SciPy version:", scipy.__version__)

   x = np.linspace(0, 2 * np.pi, 100)
   plt.plot(x, np.sin(x))
   plt.title("It works!")
   plt.show()
   ```
   If you see two version numbers and a sine wave, you're all set!

## Troubleshooting
- **"git" or "python" is not recognized / command not found:** Close and reopen VS Code, since it only notices new programs after a restart. If that doesn't fix it, restart your computer.
- **Your Python doesn't show up under Select Kernel:** Restart VS Code. On Windows, if it's still missing, run the Python installer again and make sure "Add python.exe to PATH" is checked.
- **`ModuleNotFoundError: No module named 'numpy'`:** Check that the kernel name in the top right is the Python from step 3. Then run the `%pip install` cell again and click **Restart** at the top of the notebook.
- Still stuck? Ask one of us. That's what we're here for!

## Helpful links:
- Downloading Git: https://www.youtube.com/watch?v=7ouVv6PFZGc
- Setting up Python and notebooks in VS Code (no Anaconda): https://www.youtube.com/watch?v=mTlY6MC58J8
- Jupyter notebooks in VS Code (official docs): https://code.visualstudio.com/docs/datascience/jupyter-notebooks
- Prefer Anaconda instead? Anaconda set-up: https://www.youtube.com/watch?v=WUeBzT43JyY
