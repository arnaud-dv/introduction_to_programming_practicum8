# Practicum 8 — GitHub Collaboration & Pull Request Workflow

This file should be placed in the folder `~\dev\introduction_to_programming\practicum8`.

## Context

Until now you worked with **local Git repositories**.
In this practicum you will work like real developers by collaborating through **GitHub**.

You will work in **pairs (duo teams)** and practice:

* Remote repositories
* Feature branching
* Pull requests
* Code reviews
* Merge conflicts and conflict resolution
* Basic issue workflow

⚠️ Rules:

* All Git commands must be executed in the **WSL terminal**
* Use VS Code for editing only
* Both students must actively contribute
* Do NOT push directly to `main`

## Learning Goals

After this practicum you should be able to:

* Clone and connect to a remote repository
* Work safely in feature branches
* Create and review pull requests
* Resolve merge conflicts
* Understand collaborative Git workflows

## Preparation — Workspace Setup

Create a new folder `~/dev/introduction_to_programming/practicum8`

Open this folder in VS Code using your WSL environment.

## Step 1 — Duo Team Setup (Remote Repository)

One student becomes **Repository Owner**.

### Repository Owner

1. Create a new GitHub repository `introduction_to_programming_practicum8`
2. Add your partner as collaborator.
3. Clone the repository into `practicum8`.

Example:

```bash
git clone <repository-url> .
```

### Partner Student

Clone the same repository into your own `practicum8` folder.

Verify:

```bash
git remote -v
```

## Step 2 — Starter Project

### Student A starts the project

Create this structure:

```
practicum8/
 ├── main.py
 ├── calculator.py
 └── README.md
```

#### calculator.py

```python
def add(a, b):
    return a + b
```

#### main.py

```python
import calculator

print("Result:", calculator.add(2, 3))
```

#### README.md

Write your own readme that contains the following topics:

- Title of the project/program
- Collaborators
- Discription of the project/program
- How to install and use the project/program
- MIT License reference

#### First Commit

```bash
git add .
git commit -m "Initial project setup"
git push
```

### Student B does a new pull

```bash
git pull origin main
```

## Step 3 — Working in Feature Branches (Duo Split)

Now divide tasks.

### Student A — Feature Branch

Create a branch:

```bash
git checkout -b feature/multiply
```

Add to `calculator.py`:

```python
def multiply(a, b):
    return a * b
```

Modify `main.py`:

```python
print("Multiply:", calculator.multiply(2,3))
```

Commit your work.

### Student B — Feature Branch

Create another branch:

```bash
git checkout -b feature/subtract
```

Add:

```python
def subtract(a, b):
    return a - b
```

Modify `main.py` differently:

```python
print("Subtract:", calculator.subtract(5,2))
```

Commit your work.

## Step 4 — Push Feature Branches

Each student pushes their own branch:

```bash
git push origin feature/multiply
```

or

```bash
git push origin feature/subtract
```

## Step 5 — Create Pull Requests

Go to GitHub.

Each student creates a **Pull Request** to merge into `main`.

Before merging:

* Assign your partner as reviewer
* Add a short description

Example:

```
Adds multiply function to calculator module
```

## Step 6 — Code Review

Review your partner’s Pull Request.

Checklist:

* Does the code run?
* Are names clear?
* Any missing imports?
* Does README still make sense?

Add at least **one comment** in the review.

Approve the pull request.

## Step 7 — Create a Merge Conflict (Intentional)

⚠️ This part is intentional — conflicts are part of real development.

Both students must edit the **same line** in `README.md`.

### Student A edits README.md

Choose one of the lines in the README and make a change to it.

Commit and merge the PR.

### Student B edits README.md differently

In that same line of the README make a different change to it.

Push your branch.

Try to merge your PR.

👉 GitHub will show a **merge conflict**.

## Step 8 — Resolve the Merge Conflict

Open the repository locally.

Update your branch:

```bash
git pull origin main
```

You should see conflict markers like:

```
<<<<<<< HEAD
...
=======
...
>>>>>>> branch
```

Your task:

* Decide how the final README should look
* Remove conflict markers
* Keep both contributions

Commit the resolution:

```bash
git add README.md
git commit -m "Resolve merge conflict in README"
git push
```

Finish merging the Pull Request.

## Step 9 — Issues & Project Board (Basic)

Inside GitHub:

1. Create a new Issue:

```
Add divide functionality
```

Assign it to one student.

Link the Issue in a new Pull Request description using:

```
Closes #1 (Use the actual number of the issue!)
```

## Step 10 — Verification

Pull the latest version of `main`:

```bash
git checkout main
git pull
```

Run:

```bash
python3 main.py
```

Expected output should include:

```
Result: 5
Multiply: ...
Subtract: ...
```

(Exact formatting may differ.)

## Reflection — Add to README.md

Add a new section:

```
## Reflection
```

Answer together:

1. Why should developers use feature branches?
2. What caused the merge conflict?
3. How did GitHub help you resolve it?
4. Why are pull requests useful in teams?

Commit and push the final version.

## Bonus Challenge (If You Finish Early)

Try to:

* Create a new branch `feature/divide`
* Add error handling for division by zero
* Request a review before merging

## Expected Skills After This Practicum

You should now be able to:

* Collaborate using GitHub
* Work in feature branches
* Perform pull requests and reviews
* Resolve merge conflicts safely
* Understand basic team workflows

