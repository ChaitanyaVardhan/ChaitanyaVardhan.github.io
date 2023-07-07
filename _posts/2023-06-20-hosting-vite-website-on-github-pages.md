---
tags: [static-websites]
---
Prerequisites: npm  
Dev Environment: Terminal on Mac M1  
```
npm create vite@latest
```  
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/npm_init_vite.png)    
    
```
 % npm install  
 % npm run dev
``` 
The website can be accessed locally on `http://localhost:5173/`  

### Pushing to Github  
Create a public github repo.  
Set this repo as remote for the local project repo.  
```
% git init  
% git remote add origin https://github.com/ChaitanyaVardhan/mywebsite.git   
```  
  
  
Edit `vite.config.js` to set `repo` as `./mywebsite/`. This is needed because we are using this repo to host the website rather than base :`https://<USERNAME>.github.io/`  
```
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()], 
  base: './mywebsite/'
})
```  
Git commit  :
```
% git add .
% git commit -m "scaffolding"
```  
In the repo on github, go to `Settings` -> `Pages` and select `Source` as `Github Actions` and the click on `create-your-own`  
Dump the below code in file `main.yml`. Source [https://vitejs.dev/guide/static-deploy.html](https://vitejs.dev/guide/static-deploy.html):   
```
# Simple workflow for deploying static content to GitHub Pages
name: Deploy static content to Pages

on:
  # Runs on pushes targeting the default branch
  push:
    branches: ['main']

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Sets the GITHUB_TOKEN permissions to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow one concurrent deployment
concurrency:
  group: 'pages'
  cancel-in-progress: true

jobs:
  # Single deploy job since we're just deploying
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      - name: Set up Node
        uses: actions/setup-node@v3
        with:
          node-version: 18
          cache: 'npm'
      - name: Install dependencies
        run: npm install
      - name: Build
        run: npm run build
      - name: Setup Pages
        uses: actions/configure-pages@v3
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v1
        with:
          # Upload dist repository
          path: './dist'
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v1
```  
Do a git pull with rebase to bring the yml file to local.Change the remote branch name to `main` instead of `master`. Not needed actually but let's work on `main`  .
Go to `Settings` and `Environments / Configure github-pages` and change the deployment branch to `master`  
```
% git pull origin main --rebase
% git push -u origin main
```  
In case there is a build error:  
```
Error: Dependencies lock file is not found in /home/runner/work/mywebsite/mywebsite. Supported file patterns: package-lock.json,npm-shrinkwrap.json,yarn.lock
```  
Run `% npm install` to create `package-lock.json` file.  
Git add, Git commit, Git push.




