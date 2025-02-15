# gh-deployment-workflow

# GitHub Pages Deployment with GitHub Actions

## Overview

This project demonstrates an automated deployment workflow for a static website using **GitHub Actions** and **GitHub Pages**. The workflow is triggered whenever changes are made to the `index.html` file, ensuring only relevant updates are deployed.

## Project Structure

```
GitHub Pages Deployment with GitHub Actions

Overview

This project demonstrates an automated deployment workflow for a static website using GitHub Actions and GitHub Pages. The workflow is triggered whenever changes are made to the index.html file, ensuring only relevant updates are deployed.

Project Structure/gh-deployment-workflow
├── .github/workflows/deploy.yml   # GitHub Actions workflow file
├── index.html                     # Static website homepage
├── README.md                      # Project documentation
```

## Features

✅ Automatic deployment to **GitHub Pages**
✅ Deploys only when `index.html` is modified
✅ GitHub Actions workflow for continuous integration

## Deployment URL https://github.com/teciedesk/gh-deployment-workflow.git

Once deployed, the website will be available at:

```
https://<your-username>.github.io/gh-deployment-workflow/
```

Replace `<your-username>` with your actual GitHub username.

## Setup and Usage

### 1️⃣ **Create the GitHub Repository**

1. Navigate to [GitHub](https://github.com/) and create a new repository, e.g., `gh-deployment-workflow`.
2. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/gh-deployment-workflow.git
   cd gh-deployment-workflow
   ```

### 2️⃣ **Add the Static Website**

1. Create an `index.html` file:
   ```html
   <html>
   <head><title>My Static Site</title></head>
   <body><h1>Hello, GitHub Actions!</h1></body>
   </html>
   ```
2. Commit and push the changes:
   ```bash
   git add index.html
   git commit -m "Add index.html"
   git push origin main
   ```

### 3️⃣ **Set Up the GitHub Actions Workflow**

1. Create the **workflow directory**:
   ```bash
   mkdir -p .github/workflows
   ```
2. Add `deploy.yml` inside `.github/workflows/`:
   ```yaml
   name: Deploy to GitHub Pages

   on:
     push:
       paths:
         - 'index.html'
       branches:
         - main

   jobs:
     deploy:
       runs-on: ubuntu-latest
       steps:
         - name: Checkout Repository
           uses: actions/checkout@v3

         - name: Deploy to GitHub Pages
           uses: peaceiris/actions-gh-pages@v3
           with:
             github_token: ${{ secrets.GITHUB_TOKEN }}
             publish_dir: .
   ```
3. Commit and push:
   ```bash
   git add .github/workflows/deploy.yml
   git commit -m "Add GitHub Actions workflow"
   git push origin main
   ```

### 4️⃣ **Enable GitHub Pages**

1. Go to your repository on GitHub.
2. Navigate to **Settings → Pages**.
3. Under "Branch", select `main`, then click **Save**.
4. Your site will be available at:\
   **`https://<your-username>.github.io/gh-deployment-workflow/`**

## Checking Deployment Status

1. Go to your repository and click on the **Actions** tab.
2. Look for the latest workflow run and ensure it succeeded.
3. If there’s an error, click on the workflow run to view logs and debug.

## Stretch Goal: Using a Static Site Generator

To make this project more advanced, you can integrate a **static site generator** like **Hugo, Jekyll, or Astro**. This will allow you to create a more complex portfolio or documentation site.

## License

This project is open-source and free to use.

## Author

Developed by **OLUWATOBI ADDENIYI**

https://roadmap.sh/projects/github-actions-deployment-workflow

