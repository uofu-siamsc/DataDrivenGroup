## Goal of today:
- Set up a development environment on your own laptop
- Download (clone) our workshop repository and learn the one Git command you'll use each week
- By the end you'll be able to run Python code in a Jupyter notebook inside VS Code
- Work through a short introduction to Python and Jupyter notebooks

Already have Python or Anaconda installed? You can keep it and skip step 3.

## What are these tools?
- **Git and GitHub:** Git is a program that keeps track of the files in a folder (called a *repository*, or *repo*) and every change made to them. GitHub is a website that stores repos online so they can be shared. We post each week's notebooks and data to our GitHub repo. With Git you download the whole repo once, then get each week's new files with a single command. Git is also the standard way programmers and scientists share code, so it's worth knowing.
- **VS Code:** A free code editor, which is where you'll write and run your code. It works with Jupyter notebooks (documents that mix code, output, plots and notes) and has a built-in *terminal*, a window where you type commands instead of clicking.
- **Python and pip:** Python is the programming language we'll use. On its own it only has basic tools, so we add *packages*: NumPy (arrays and linear algebra), SciPy (scientific computing) and Matplotlib (plots). pip is Python's package installer. Running `pip install numpy` downloads NumPy from the internet and installs it so your code can `import numpy`.

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

### 6. Clone the workshop repo
In the same terminal, run these two commands:
```
cd ~/Documents
git clone https://github.com/uofu-siamsc/DataDrivenGroup.git
```
The first command moves the terminal into your Documents folder. The second downloads our repo into a new folder called `DataDrivenGroup`. If your Mac asks whether VS Code can access your Documents folder, click **Allow**.

Now open the repo in VS Code: go to **File → Open Folder...** and choose `Documents/DataDrivenGroup`. If it asks whether you trust the authors, click **Yes**.

### 7. Make a test notebook
1. Go to **File → New File...**, choose **Jupyter Notebook**, then save it (`Ctrl + S` / `Cmd + S`) in the `DataDrivenGroup` folder as `my_test.ipynb`.
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

### 8. Work through the intro notebook
1. In VS Code's file list on the left, open the `10_21_26` folder.
1. Make your own copy of `intro_to_python.ipynb`: right-click it, choose **Copy**, then right-click and choose **Paste**. (Why make a copy? See step 3 of the next section.)
1. Open your copy, select the same kernel as in step 7, and run the cells from top to bottom.

## What you'll do each week
1. Open VS Code. It usually reopens `DataDrivenGroup` on its own. If it doesn't, use **File → Open Folder...**.
1. Open a terminal (**Terminal → New Terminal**) and run:
   ```
   git pull
   ```
   This downloads any new notebooks and data we've posted. Each session gets its own folder, named by date (e.g. `10_28_26`).
1. **Before running or editing one of our notebooks, make a copy of it.** Right-click it in VS Code's file list, choose **Copy**, then right-click and choose **Paste**. Work in the copy. Running cells changes the file too, because the output gets saved in it. If you change our original and we later update it, `git pull` will refuse to run.
1. Open the notebook. If it asks you to select a kernel, pick the same Python as in step 7.

That's all the Git you need for this workshop. If you want to learn more, or keep your own version of the repo on your GitHub account, ask us about *forking* the repo.

## Troubleshooting
- **"git" or "python" is not recognized / command not found:** Close and reopen VS Code, since it only notices new programs after a restart. If that doesn't fix it, restart your computer.
- **Can't find the `DataDrivenGroup` folder (common on Windows with OneDrive):** In the terminal where you ran `git clone`, run `pwd`. It prints the folder that `DataDrivenGroup` was created in, so browse there in **File → Open Folder...**.
- **Your Python doesn't show up under Select Kernel:** Restart VS Code. On Windows, if it's still missing, run the Python installer again and make sure "Add python.exe to PATH" is checked.
- **`ModuleNotFoundError: No module named 'numpy'`:** Check that the kernel name in the top right is the Python from step 3. Then run the `%pip install` cell again and click **Restart** at the top of the notebook.
- **`fatal: not a git repository`:** Your terminal isn't inside the `DataDrivenGroup` folder. Open that folder with **File → Open Folder...**, then open a new terminal.
- **`git pull` says "Your local changes ... would be overwritten":** You edited one of our files. Make a copy of each file listed in the message, then run `git restore .` followed by `git pull`. Make the copies first, because `git restore .` erases your edits to our files.
- Still stuck? Ask one of us. That's what we're here for!

## Helpful links:
- Downloading Git: https://www.youtube.com/watch?v=7ouVv6PFZGc
- Setting up Python and notebooks in VS Code (no Anaconda): https://www.youtube.com/watch?v=mTlY6MC58J8
- Jupyter notebooks in VS Code (official docs): https://code.visualstudio.com/docs/datascience/jupyter-notebooks
- Prefer Anaconda instead? Anaconda set-up: https://www.youtube.com/watch?v=WUeBzT43JyY
