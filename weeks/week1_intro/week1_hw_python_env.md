# 🛠️ Homework 1 — Set up Python environment

Before we start with the course content, your first task is to **set up a Python development environment** on your computer.

---

## ✅ What You'll Be Doing

You will:

- Install Python using **Anaconda or Miniconda**
- Create a **dedicated environment** for this course
- Install the required **Python libraries**
- Set up a **code editor** (e.g., **VS Code**)
- Open and run **Jupyter notebooks**

---

## 1️⃣ Install Conda (Python + Environment Manager)

You can use **Miniconda** (lighter) or **Anaconda** (includes extra tools).

👉 Download and install:

- **Miniconda (recommended):** https://www.anaconda.com/docs/getting-started/miniconda/install
- Or **Anaconda:** https://www.anaconda.com/docs/getting-started/anaconda/install

Choose the version for your operating system (Windows, macOS, or Linux) and follow the instructions on the website.

> ⚠️ **Note:** Instructions and tools may look slightly different depending on your operating system.

---

## 2️⃣ Open a Terminal or Anaconda Prompt
> 🤯 If you don't know what's a **terminal**, check out this short intro:  **[Command line for beginners](https://www.freecodecamp.org/news/command-line-for-beginners/)**  

Once Conda is installed:

- **Windows**: Open the **Anaconda Prompt**
- **macOS/Linux**: Open your **Terminal**

---

## 3️⃣ Create a Conda Environment for This Course

In the terminal, run:

```bash
conda create -n applied_ml python=3.10
```

This creates a clean, isolated Python environment named applied_ml.

Activate it with:
```bash
conda activate applied_ml
```
---

## 4️⃣ Install the Required Packages

With the environment activated, install the packages we’ll use:

```bash
conda install pandas numpy matplotlib scikit-learn jupyter
```

---

## 5️⃣ Install VS Code (Recommended Editor)

Now you need to install a text editor or an integrated development environment (IDE), where you will edit your code. I recommend Visual Studio Code (VS Code) because it's:

- Beginner-friendly
- Works well with both scripts and notebooks
- Has great Python support
  
👉 Download: https://code.visualstudio.com/

After installing VS Code:

- Open it
- Install the Python extension (when prompted or via the Extensions tab)

> ⚠️ **Note:** You can use any other editor if you prefer (and know what you are doing).

--- 

## 6️⃣ Open and Run Jupyter Notebooks

You can open Jupyter Notebooks directly from VS Code!

Alternatively, you can run notebooks in browser as follows:

- Activate your environment again if needed:
```bash
conda activate applied_ml
```

- Start Jupyter:
```bash
jupyter notebook
```
This will open a browser window where you can open and run .ipynb files.



🧪 You're now ready to start coding!


## Test if it is working