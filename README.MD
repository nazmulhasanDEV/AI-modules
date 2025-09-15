

# Documentation: Anaconda + Environment Setup + VS Code + Jupyter

## 🔹 1. Install Anaconda

1. Download Anaconda (Linux `.sh` installer) from [official site](https://www.anaconda.com/download).
2. Open terminal in `Downloads`:

   ```bash
   cd ~/Downloads
   bash Anaconda3-2024.07-Linux-x86_64.sh
   ```
3. Follow prompts → accept license → press **Enter** for default install (`~/anaconda3`).
4. Activate Anaconda:

   ```bash
   source ~/anaconda3/bin/activate
   conda init
   ```
5. Restart terminal. You should see `(base)` before your prompt → ✅ Anaconda is installed.

---

## 🔹 2. Manage Conda Environments

### Check existing environments

```bash
conda env list
```

### Create new environment (example: NLP course)

```bash
conda create -n nlp-env python=3.11
```

### Activate environment

```bash
conda activate nlp-env
```

### Deactivate environment

```bash
conda deactivate
```

### Clone (copy) environment

```bash
conda create --name new-env --clone old-env
```

### Remove environment

```bash
conda remove --name old-env --all
```

---

## 🔹 3. Install Packages in Environment

Make sure you’re inside `nlp-env`:

```bash
conda activate nlp-env
```

### Install core packages

```bash
pip install spacy gensim scikit-learn pandas numpy matplotlib
```

### Download spaCy English model

```bash
python -m spacy download en_core_web_sm
```

### Install Jupyter + Kernel support

```bash
pip install ipykernel jupyterlab notebook
```

---

## 🔹 4. Register Environment in Jupyter

This step makes your environment selectable inside Jupyter/VS Code.

```bash
python -m ipykernel install --user --name=nlp-env --display-name "Python (nlp-env)"
```

---

## 🔹 5. Launch Jupyter

### Notebook

```bash
jupyter notebook
```

### JupyterLab (modern interface)

```bash
jupyter lab
```

Both will open in browser at `http://localhost:8888/tree`.

---

## 🔹 6. VS Code Configuration

### Install Extensions

* Open VS Code → Extensions (`Ctrl+Shift+X`).
* Install:

  * **Python** (by Microsoft)
  * **Jupyter** (by Microsoft)

### Open Project

* `File → Open Folder` → choose your project folder (e.g., `AI-modules`).

### Select Kernel

1. Open or create `.ipynb` file.
2. In top right, click the **kernel picker**.
3. Choose **Python (nlp-env)**.

Now VS Code will run cells inside your environment.

---

## 🔹 7. Running Python Scripts in VS Code

To make `.py` scripts use your env:

1. Open **Command Palette** (`Ctrl+Shift+P`).
2. Search for **Python: Select Interpreter**.
3. Pick **Python (nlp-env)**.

