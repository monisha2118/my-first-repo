# CI Setup – Week 1

## 📁 File Created
- .github/workflows/ci.yml

## ⚙️ What I Did

- Created a GitHub Actions workflow for Continuous Integration (CI).
- The workflow runs on every push or pull_request to the repository.
- It performs the following steps:
  1. *Checks out the code* using actions/checkout@v3.
  2. *Prints a message* using a simple echo command (Hello from GitHub Actions!).

## 🛠 Workflow Details

```yaml
name: Simple CI

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: checkout code
        uses: actions/checkout@v3

      - name: say hello
        run: echo "Hello from GitHub Actions!"
