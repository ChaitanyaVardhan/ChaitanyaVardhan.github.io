---
tags: [static-websites]
---
Take the gasbyjs [gatsbyjs](https://github.com/gatsbyjs/gatsby) boilerplate page and host it using github pages with custom domain. Website will be live on prefix.domain. In my case [https://web.chaitanyavardhan.com](https://web.chaitanyavardhan.com).  
Dev Environment:  
NPM, Mac Terminal, Git
Install NPM from here [https://nodejs.org/en/download](https://nodejs.org/en/download)  

Gatsby quickstart instructions can be found here [https://www.gatsbyjs.com/docs/quick-start/](https://www.gatsbyjs.com/docs/quick-start/)  
```$ npm init gatsby ```  
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/npm_init_gatsby.png)  
The above command asks a few questions and sets up a directory.   
cd into the directory:    
```$ cd gatsby-github-pages-demo/```  
Start the local development server:  
```$ npm run develop```  
The above command ends in error as the google-tag option was chosen but no google tag is provided.  
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/npm_run_develop.png)  
To fix the above error, remove the google tag plugin from `gatsby-config.ts` .  
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/gatsby_config.png)
  
start the local dev server now after editing the config file.  
```$ npm run develop```
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/dev_server.png)  

The website can be accessed locally on http://localhost:8000  
## Hosting on Github pages  
Create a public repo on github with the same name as the local repo and link the local repo to the remote repo.  
```
% cd gatsby-github-pages-demo
% git init
% git remote add origin https://github.com/ChaitanyaVardhan/gatsby-github-pages-demo.git   
```  
### Setting up Github Actions for build and deploy  
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/github_actions.png)  
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/gatsby_yml.png)  
Clicking on `Commit changes` will created the `.github` directory with `yml` file in it.  
Git Commit local changes.  
```
% git add .
% git commit -m "rm google tag plugin"
```  
Bring the yml file to local by rebasing.  
```
% git pull --rebase origin main
```  
Edit the `package.json` file to add the deploy script:
```
"deploy": "gatsby build && gh-pages -d public -b main --repo https://github.com/ChaitanyaVardhan/gatsby-github-pages-demo.git",
```  
![](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/deploy_script.png)

Git commit.  
Create an CNAME file.  
```
% touch CNAME
% echo web.chaitanyavardhan.com > CNAME
```  
Git commit.  
Git push every thing to remote.
```
% git push -u origin main
```  
My default branch was `master` when I created the `yml` earlier. Changing to `main` as github pages works with `main` branch.  
### Trigger the deploy after making a dummy commit to main
### Possible Build errors:
```
Error: Dependencies lock file is not found in /home/runner/work/gatsby-github-pages-demo/gatsby-github-pages-demo. Supported file patterns: package-lock.json,npm-shrinkwrap.json,yarn.lock
```  
Solution: add the `package-lock.json` file  

```
Branch "main" is not allowed to deploy to github-pages due to environment protection rules.
```  

Solution: [https://github.com/orgs/community/discussions/39054](https://github.com/orgs/community/discussions/39054)
### if needed remove and re-created `package-lock.json` and push to remote for build to run successfully  

### The website will be live on `http://blog.chaitanyavardhan.com/gatsby-github-pages-demo/` as I already have a domain name associated with my github pages hosted blog.  
  
## DNS Settings:  
In the dns provider, add a CNAME record.  
![https://chaitanyavardhan-blog-assets.s3.amazonaws.com/cname.png](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/cname.png)    
  

In Github, plugin in the custom domain.  
![https://chaitanyavardhan-blog-assets.s3.amazonaws.com/github_custom_domain.png](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/github_custom_domain.png)  

The website is now live at [https://web.chaitanyavardhan.com](https://web.chaitanyavardhan.com). Github will enable `https` automatically.  


Thank you. Gatsbyjs seems a pretty good framework!!!