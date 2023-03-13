---
_schema: index
title: Getting Started
linkTitle: Getting Started
weight: 2
description: How to get your own documentation site
categories:
  - Getting Started
tags:
  - Install
  - Start
  - Getting Started
  - Template
  - Build
---
The simplest way to get started is to use this project as a template, which gives you a site project that is set up and ready to use. To do this:

1\. Click **Use this template** on <a target="_blank" rel="noopener" href="https://github.com/tomrcc/docsycannon-template">GitHub</a>

2\. Select a name for your new project and click **Create repository from template**.

3\. [Sign up](https://app.cloudcannon.com/register?trial=cc_standard)&nbsp;for CloudCannon using their free trial period.

4\. <a target="_blank" rel="noopener" href="https://cloudcannon.com/community/learn/hugo-cms---get-started-with-cloudcannon">Build your site</a>.

Once you have a copy of the template live on CloudCannon, navigate to <a target="_blank" rel="noopener" href="https://app.cloudcannon.com/editor">CloudCannon's CMS</a>&nbsp;and edit the contents to suit your needs.

## Forking vs. Use as template

If you prefer, you can fork the DocsyCannon repository on <a target="_blank" rel="noopener" href="https://github.com/tomrcc/docsycannon-template">GitHub</a>, instead of using the repository as a template. [Here](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template) is more information on the difference between the two methods. The main advantage of using a repository created from a template is that it starts with a single commit, giving you a fresh commit history, while a fork includes the entire commit history of the parent repository.

Forking a repo will keep you up to date with the latest changes to DocsyCannon automatically, which can be useful or annoying depending on your use case. Either method, you will may have to resolve some merge conflicts to get the changes into your repo. We recommend using the template, then if you end up needing any changes made to DocsyCannon you can set it as an upstream remote. You would then pull through the changes and then merging `upstream/main` with your main branch.

Open your CLI and navigate to the root folder of your project and the branch you want the changes to be made on. Add an upstream remote.<br>`git remote add upstream git@github.com:cloudcannon/docsycannon-template.git`

Fetch the changes to your upstream remote.<br>`git fetch upstream`

Your changes will live on a new branch called&nbsp;`upstream/main`. Merge&nbsp;`upstream/main`&nbsp;into `main`​​, or whatever branch you want the changes on. We recommend using a tool like <a target="_blank" rel="noopener" href="https://www.sublimemerge.com/">Sublime Merge</a> to make this easier.