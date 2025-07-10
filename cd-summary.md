# Continuous Deployment (CD) Setup Summary

## ✅ Objective:
Set up Continuous Deployment using *GitHub Actions* to automatically deploy a static site to *GitHub Pages* when code is pushed to the main branch.

---

## 🔧 Steps Performed:

1. *Created GitHub Repository*
   - Repository name: my-first-repo
   - Initialized with a basic index.html file for the static webpage.

2. *Set Up GitHub Pages*
   - Enabled GitHub Pages from repository settings.
   - Deployed from the main branch using /root as the source.

3. *Created .github/workflows/cd.yml*
   - Added a GitHub Actions YAML file to define the CD workflow.
   - This workflow triggers on every push to main branch.

4. *Configured cd.yml with Deployment Steps*
   - Uses actions/checkout to get repo files.
   -  Uses peaceiris/actions-gh-pages to deploy the site to GitHub Pages.

5. *Commit & Push*
   - Committed all changes and pushed to main.
   - Verified that the GitHub Actions workflow ran successfully.

6. *Verified Deployment*
   - Visited the live deployed site at:  
     🔗 [https://monisha2118.github.io/my-first-repo/](https://monisha2118.github.io/my-first-repo/)

---

## ✅ Outcome:
The site is successfully deployed using Continuous Deployment.  
Any future changes pushed to the main branch will *automatically trigger deployment* via GitHub Actions.

---

## 📂 Workflow File: cd.yml

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./
