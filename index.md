---
layout: default
title: Deploy React + Vite App to GitHub Pages
description: A step-by-step guide to deploy a React + Vite web application to GitHub Pages.
---

# **Introduction**
## **Background Information**
React is a popular JavaScript library for building user interfaces, while Vite is a modern frontend tool that enhances the development experience with fast builds and hot module replacement. GitHub Pages is a free hosting service that allows users to deploy static websites directly from a GitHub repository.

This guide will walk through the process of deploying a **React + Vite** web application to GitHub Pages, a task commonly encountered by software developers, frontend engineers, and students working on web-based projects. Deploying a React + Vite app is useful for showcasing portfolio projects, sharing interactive web applications, and testing web designs.

## **Context of Use**
- **For Developers:** Useful for quick prototyping and sharing React applications.
- **For Students:** Helps in publishing academic or portfolio projects without the need for paid hosting.
- **Common Challenges:** Users may face issues related to incorrect configurations, missing dependencies, or incorrect repository setup.

---
# **Requirements**
Before starting, ensure you have the following tools installed and configured on your system.

## **Hardware Requirements:**
- A computer (Windows, macOS, or Linux)
- Stable internet connection

## **Software Requirements:**
1. **Node.js (LTS version)** – Required to run JavaScript applications.
   - Download from: [https://nodejs.org/](https://nodejs.org/)
2. **Git** – Required for version control and pushing code to GitHub.
   - Download from: [https://git-scm.com/](https://git-scm.com/)
3. **GitHub Account** – Needed to create a repository and host the project.
   - Sign up at: [https://github.com/](https://github.com/)
4. **GitHub CLI (Optional)** – Simplifies authentication and repository management.
   - Install from: [https://cli.github.com/](https://cli.github.com/)

---
# **Safety Considerations**
- Be cautious when running commands in the terminal to avoid accidental file deletions.
- Ensure that you are working inside the correct directory before executing Git commands.
- Avoid committing sensitive data (e.g., API keys, credentials) to public repositories.
- Regularly update dependencies to prevent security vulnerabilities.

---
# **Step-by-Step Instructions**

## **Step 1: Set Up a React + Vite Project**
1. Open a terminal or command prompt.
2. Run the following command to create a new Vite project:
   ```sh
   npm create vite@latest my-vite-app --template react
   ```
3. Navigate into the project directory:
   ```sh
   cd my-vite-app
   ```
4. Install project dependencies:
   ```sh
   npm install
   ```

## **Step 2: Configure Vite for GitHub Pages**
1. Open `vite.config.js` in a text editor.
2. Add the following `base` property to the configuration:
   ```js
   import { defineConfig } from 'vite';
   import react from '@vitejs/plugin-react';

   export default defineConfig({
     plugins: [react()],
     base: '/<repo-name>/', // Replace <repo-name> with your actual GitHub repository name
   });
   ```

## **Step 3: Modify package.json for Deployment**
1. Open `package.json`.
2. Add the following scripts inside the `scripts` section:
   ```json
   "predeploy": "npm run build",
   "deploy": "gh-pages -d dist"
   ```
3. Install the GitHub Pages package:
   ```sh
   npm install gh-pages --save-dev
   ```

## **Step 4: Initialize Git and Push the Project to GitHub**
1. Initialize a Git repository:
   ```sh
   git init
   ```
2. Add the remote GitHub repository:
   ```sh
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   ```
3. Commit and push the code:
   ```sh
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git push -u origin main
   ```

## **Step 5: Deploy the App to GitHub Pages**
1. Run the deployment script:
   ```sh
   npm run deploy
   ```
   This builds the project and pushes the `dist/` folder to the `gh-pages` branch.

## **Step 6: Enable GitHub Pages**
1. Navigate to your **GitHub repository**.
2. Go to **Settings > Pages**.
3. Under **Branch**, select `gh-pages` and click **Save**.
4. Your site will be available at:
   ```
   https://<your-username>.github.io/<repo-name>/
   ```

---
# **Conclusion & Further Resources**
You have successfully deployed a **React + Vite** app to **GitHub Pages**! If you encounter issues, here are some additional resources:
- [Vite Documentation](https://vitejs.dev/guide/)
- [GitHub Pages Documentation](https://pages.github.com/)
- [GitHub CLI Documentation](https://cli.github.com/)

For accessibility and further assistance, check **GitHub Discussions** or **Stack Overflow** for troubleshooting common errors.

---
# **References**
- Node.js. (n.d.). Retrieved from [https://nodejs.org/](https://nodejs.org/)
- Git. (n.d.). Retrieved from [https://git-scm.com/](https://git-scm.com/)
- GitHub CLI. (n.d.). Retrieved from [https://cli.github.com/](https://cli.github.com/)
- Vite. (n.d.). Retrieved from [https://vitejs.dev/](https://vitejs.dev/)

