# Python_Project
STEP 1 — Create Project Folder
Go to D drive:
- cd /mnt/d
  
Create folder:
- mkdir Python_Project

Go inside:
- cd Python_Project

STEP 2 — Initialize Git
- git init

STEP 3 — Create Python File
- Create file:
  nano calc.py


````````
bash
def add(a, b):
    return a + b
`````````
STEP 4 — Create Test File
nano test_calc.py

`````
bash

from calc import add

def test_add():
    assert add(2, 3) == 5

`````````

STEP 5 — Create requirements.txt
- nano requirements.txt
   pytest
   pytest-html
   pytest-cov

STEP 6 — Create GitHub Workflow Folder

- mkdir -p .github/workflows

STEP 7 — Create Workflow File

- nano .github/workflows/python-test.yml

`````
bash
name: Python Testing Workflow

on:
  push:
    branches:
      - main

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Setup Python
        uses: actions/setup-python@v5
        with:
          python-version: "3.10"

      - name: Install Dependencies
        run: |
          pip install -r requirements.txt

      - name: Run Tests with Coverage
        run: |
          pytest --html=report.html --self-contained-html --cov=. --cov-report=html

      - name: Upload Report Artifact
        uses: actions/upload-artifact@v4
        with:
          name: test-report
          path: |
            report.html
            htmlcov

   ``````````

STEP 8 — Create GitHub Repository

- Create repository:
  Python_Project

STEP 9 — Connect Local Repo to GitHub

- git remote add origin git@github.com:mahajanhemangi8767-cyber/Python_Project.git


STEP 10 — Add Files

- git add .

STEP 11 — Commit Files

- git commit -m "Python testing workflow setup"

STEP 12 — Rename Branch

- git branch -M main

STEP 13 — Push Code

- git push -u origin main

STEP 14 — Open GitHub Actions
Open your repo
Click: Actions

You will see: Python Testing Workflow



