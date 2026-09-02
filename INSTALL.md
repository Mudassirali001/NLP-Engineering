# Installation Guide

Complete step-by-step instructions for setting up the NLP Engineering project.

## Table of Contents
- [System Requirements](#system-requirements)
- [Installation Steps](#installation-steps)
- [Verifying Installation](#verifying-installation)
- [Troubleshooting](#troubleshooting)
- [Additional Setup](#additional-setup)

## System Requirements

### Minimum Requirements
- **Python:** 3.7 or higher
- **pip:** 20.0 or higher
- **RAM:** 2 GB minimum (4 GB recommended)
- **Disk Space:** 500 MB for libraries and data

### Supported Operating Systems
- Windows 10/11
- macOS 10.14+
- Linux (Ubuntu 18.04+, CentOS 7+, Debian 10+)

### Verify Your Python Version

Open a terminal/command prompt and run:

```bash
python --version
# or
python3 --version
```

**Expected output:** `Python 3.7.x` or higher

If you don't have Python installed, download it from [python.org](https://www.python.org/downloads/)

## Installation Steps

### Step 1: Clone or Download the Repository

**Option A: Clone with Git**
```bash
git clone <repository-url>
cd Week_5
```

**Option B: Download Manually**
- Download the repository as ZIP
- Extract the folder
- Navigate to the `Week_5` directory

### Step 2: Create a Virtual Environment (Recommended)

Virtual environments isolate project dependencies and prevent conflicts with other projects.

**Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

**macOS/Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

You should see `(venv)` at the beginning of your terminal prompt when activated.

### Step 3: Upgrade pip

Ensure you have the latest version of pip:

**Windows:**
```bash
python -m pip install --upgrade pip
```

**macOS/Linux:**
```bash
python3 -m pip install --upgrade pip
```

### Step 4: Install Dependencies

Install all required Python packages:

```bash
pip install -r requirements.txt
```

**Expected output:** Similar to below:
```
Successfully installed nltk-3.8 scikit-learn-1.0.0 ...
```

### Step 5: Download NLTK Data

NLTK requires additional data files for tokenization and other operations:

**Interactive Download (Recommended):**
```bash
python -m nltk.downloader
```

A GUI window will open. Download the following:
- `tokenize` - Tokenizers (punkt, RegexpTokenizer, etc.)
- `stopwords` - Stopwords list
- `wordnet` - WordNet lemmatizer database
- `averaged_perceptron_tagger` - POS tagger

**Command-line Download (Alternative):**
```bash
python -m nltk.downloader tokenize stopwords wordnet averaged_perceptron_tagger
```

**Automated Download (Script):**
Create a file `download_nltk_data.py`:
```python
import nltk

# Download required NLTK datasets
datasets = ['tokenize', 'stopwords', 'wordnet', 'averaged_perceptron_tagger']

for dataset in datasets:
    print(f"Downloading {dataset}...")
    nltk.download(dataset)

print("All NLTK datasets downloaded successfully!")
```

Run it:
```bash
python download_nltk_data.py
```

## Verifying Installation

### Test 1: Check Python Packages

Verify all packages are installed correctly:

```bash
pip list
```

You should see:
- nltk (3.8 or higher)
- scikit-learn (1.0.0 or higher)

### Test 2: Run the Main Script

Execute the NLP examples:

```bash
python nlp_engineering.py
```

**Expected output:**
```
Word Tokens: ['Python', ',', 'AI', 'and', 'NLP', 'are', 'amazing', '.']
Sentence Tokens: ['I love AI.', 'I play Cricket.', 'I watch Cricket']
Text Words: ['the', 'cat', 'is', 'sleeping', 'on', 'bed', '.']
...
```

### Test 3: Quick Python Test

Open Python interactive shell:

```bash
python
```

Run these commands:

```python
# Test NLTK
import nltk
from nltk.tokenize import word_tokenize
text = "Hello, World!"
tokens = word_tokenize(text)
print("Tokenization works:", tokens)

# Test scikit-learn
from sklearn.feature_extraction.text import CountVectorizer
print("scikit-learn works: ✓")

# Exit
exit()
```

Expected output:
```
Tokenization works: ['Hello', ',', 'World', '!']
scikit-learn works: ✓
```

## Troubleshooting

### Issue 1: ModuleNotFoundError

**Error:**
```
ModuleNotFoundError: No module named 'nltk'
```

**Solution:**
```bash
pip install nltk
```

Verify installation:
```bash
python -c "import nltk; print(nltk.__version__)"
```

### Issue 2: NLTK Data Not Found

**Error:**
```
LookupError: 
**NLTK Data not found, or nltk_data directory is empty!**
```

**Solution:**
Download NLTK data:
```bash
python -m nltk.downloader -d ~/nltk_data all
```

Or use the interactive downloader:
```bash
python -m nltk.downloader
```

### Issue 3: Virtual Environment Not Activating

**Windows - Command Prompt:**
```bash
venv\Scripts\activate.bat
```

**Windows - PowerShell:**
```bash
venv\Scripts\Activate.ps1
```

If you get an execution policy error, run PowerShell as administrator and execute:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

**macOS/Linux:**
```bash
source venv/bin/activate
```

### Issue 4: Permission Denied (macOS/Linux)

**Error:**
```
Permission denied while trying to connect to Docker daemon
```

**Solution:**
```bash
sudo pip install -r requirements.txt
# or
python -m pip install --user -r requirements.txt
```

### Issue 5: Conflicting Packages

**Error:**
```
ERROR: pip's dependency resolver does not currently take into account all the packages that are installed
```

**Solution:**
Create a fresh virtual environment:
```bash
# Deactivate current environment
deactivate

# Remove old environment
rm -rf venv  # On Windows: rmdir /s venv

# Create new environment
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# Reinstall packages
pip install -r requirements.txt
```

### Issue 6: Python Version Mismatch

**Error:**
```
This project requires Python 3.7 or higher
```

**Solution:**
Install the correct Python version from [python.org](https://www.python.org/downloads/)

Verify after installation:
```bash
python --version
```

## Additional Setup

### Using an IDE

#### VS Code
1. Install Python extension from VS Code Marketplace
2. Select Python interpreter: `Ctrl+Shift+P` → "Python: Select Interpreter"
3. Choose the interpreter from your virtual environment (`./venv/bin/python`)
4. Open integrated terminal and activate environment

#### PyCharm
1. Create new project → Choose existing environment → Select `venv/bin/python`
2. PyCharm will automatically activate the environment

#### Jupyter Notebook (Optional)

If you want to use Jupyter notebooks:

```bash
pip install jupyter notebook
jupyter notebook
```

Then open `nlp_engineering.py` in a notebook format or create new `.ipynb` files.

### Enable IDE Features

**VS Code - Python Extension Settings:**

Add to `.vscode/settings.json`:
```json
{
    "python.linting.enabled": true,
    "python.linting.pylintEnabled": true,
    "python.formatting.provider": "black",
    "python.linting.pylintArgs": ["--load-plugins=pylint_django"]
}
```

### Update Dependencies (Optional)

To upgrade all packages to their latest versions:

```bash
pip list --outdated
pip install --upgrade -r requirements.txt
```

## Getting Help

If you encounter issues not covered here:

1. Check [README.md](README.md) for general information
2. Review [CONTRIBUTING.md](CONTRIBUTING.md) for bug reporting
3. Check NLTK documentation: https://www.nltk.org/
4. Check scikit-learn documentation: https://scikit-learn.org/
5. Open an issue on GitHub with:
   - Python version
   - Error message
   - Steps to reproduce
   - Output of `pip list`

## Next Steps

After successful installation:

1. Read [README.md](README.md) for project overview
2. Run the examples: `python nlp_engineering.py`
3. Explore the code: `nlp_engineering.py`
4. Try modifying examples to learn
5. Check [CONTRIBUTING.md](CONTRIBUTING.md) to contribute

---

**Happy Learning!** 🎓

For detailed documentation, see [README.md](README.md)
