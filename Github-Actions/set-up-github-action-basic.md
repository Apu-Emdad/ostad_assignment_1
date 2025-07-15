# Step-by-Step Guide to Set Up a GitHub Actions Workflow

### 1. Create Workflow Folder and File

In your local repo, create the directory for workflows:

```bash
mkdir - p.github / workflows;
```

Create a workflow file inside that directory, e.g.:

```bash
.github/workflows/read-hello.yml
```

### 2. Write Workflow YAML

Add this content, adjusting the branch name accordingly:

```yml
name: Read Hello File

on:
  push:
    branches:
      - master # or 'main', match your repo branch name

jobs:
  display-hello:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Display hello.txt content
        run: cat hello.txt
```

### 4. Add, Commit, and Push Workflow File

```bash
git add .github/workflows/read-hello.yml
git commit -m "Add workflow to read hello.txt on push"
git push origin master  # or your branch
```

### 5. Confirm Workflow Execution

- Go to your GitHub repo.
- Click the **Actions** tab.
- The workflow should be listed and show recent runs.
- Open the latest run and check the step logs to see `hello.txt` content.

### 6. Common Troubleshooting Tips

- Make sure the workflow file is **inside `.github/workflows/` directory**.
- The workflow triggers on the branch you pushed to (check your `branches` value).
- Ensure `hello.txt` exists in the pushed commit on that branch.
- Commit and push both the workflow file and `hello.txt` if needed.

# Explanation of the workflow YML

Here’s a block-by-block explanation of your workflow YAML:

```yml
name: Read Hello File
```

- Sets the name of the workflow visible in GitHub Actions UI.

---

```yml
on:
  push:
    branches:
      - master # or 'main', match your repo branch name
```

- Defines the event that triggers this workflow.
- Runs **whenever code is pushed to the `master` branch**.

---

```yml
jobs:
  display-hello:
```

- Defines a job named `display-hello`.
- A job is a set of steps executed on a runner.

---

```yml
  runs-on: ubuntu-latest
```

- Specifies the runner environment.
- Uses a **GitHub-hosted Ubuntu Linux runner** to execute the job.

---

```yml
  steps:
```

- Lists the steps to be run sequentially inside the job.

---

```yml
    - name: Checkout repository
      uses: actions/checkout@v2
```

- Checks out your repository’s code so the runner can access files.
- Uses the official `actions/checkout` action version 2.

---

```yml
    - name: Display hello.txt content
      run: cat hello.txt
```

- Runs a shell command (`cat hello.txt`) on the runner.
- Reads and prints the content of `hello.txt` file to the workflow log.

In summary:
When you push to the `master` branch, GitHub Actions runs this workflow on an Ubuntu runner, checks out your code, and prints the content of `hello.txt` to the logs.
