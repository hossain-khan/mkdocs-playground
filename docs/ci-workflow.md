# Setting Up GitHub Actions to Build MkDocs Site

Follow these steps to automatically build your MkDocs site using GitHub Actions:

## 1. Create Workflow File

In your repository, create a file at `.github/workflows/mkdocs.yml`.

## 2. Add Workflow Configuration

Paste the following example workflow:

```yaml
name: Build MkDocs Site

on:
    push:
        branches: [ main ]
    pull_request:

jobs:
    build:
        runs-on: ubuntu-latest

        steps:
            - name: Checkout code
                uses: actions/checkout@v4

            - name: Set up Python
                uses: actions/setup-python@v5
                with:
                    python-version: '3.11'

            - name: Install dependencies
                run: |
                    pip install mkdocs

            - name: Build MkDocs site
                run: mkdocs build
```

## 3. Commit and Push

Commit and push the workflow file to your repository. The workflow will run on every push or pull request to the `main` branch.

## 4. Verify Workflow

Check the "Actions" tab in your GitHub repository to see the workflow run and verify the MkDocs build.
