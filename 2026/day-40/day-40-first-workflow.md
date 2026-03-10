# Day 40 — My First GitHub Actions Workflow

## My Workflow YAML
```yaml
name: Greetings

on:
  push:

jobs:
  greet:
    runs-on: ubuntu-latest
    steps:
      - name: Code Checkout
        uses: actions/checkout@v4

      - name: Print Hello
        run: echo "Hello from GitHub Actions!"

      - name: Print Date and Time
        run: date

      - name: Print Branch Name
        run: echo "Branch is -> ${{ github.ref_name }}"

      - name: List Files in Repo
        run: ls -la

      - name: Print Runner OS
        run: cat /etc/os-release
```

## Screenshot of Green Run
![Green Run](screenshot.png)

## What Each Key Does

### on:
on: tells GitHub WHEN to start the workflow.
Like an alarm — when I push code, pipeline starts automatically.

### jobs:
jobs: contains all the work that needs to happen.
Each job runs on its own fresh Ubuntu machine.

### steps:
steps: are individual commands inside a job.
They run ONE BY ONE in order top to bottom.
If one step fails — all steps after it are skipped.

## What I Learned
- Workflow needs on: jobs: runs-on: to work
- uses: calls ready made action
- run: executes my own shell command
- All workflow files go inside .github/workflows/

<img width="1911" height="922" alt="image" src="https://github.com/user-attachments/assets/29abf4ba-7889-4a79-9127-10e34db66006" />

<img width="1890" height="795" alt="image" src="https://github.com/user-attachments/assets/87a61b5c-a69f-473b-9b41-930e6bff799c" />


