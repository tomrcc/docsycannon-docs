---
_schema: index
title: Repository Links
linkTitle: Repository Links
weight: 7
description: Help your users interact with your source repository.
categories:
  - Repository Links
  - GitHub
tags:
  - Repository Links
  - Repository
  - GitHub
  - Issues
  - Contribute
---
The DocsyCannon docs and blog layouts include links for readers to edit the page or create issues for your docs or project via your site’s source repository. The current generated links for each docs or blog page are:

* **View page source**\: Brings the user to the page source in your docs repo.
* **Edit this page**\: Brings the user to an editable version of the page content in their fork (if available) of your docs repo. If the user doesn’t have a current fork of your docs repo, they are invited to create one before making their edit. The user can then create a pull request for your docs.
* **Create child page**\: Brings the user to a create new file form in their fork of your docs repo. The new file will be located as a child of the page they clicked the link on. The form will be pre-populated with a template the user can edit to create their page. You can change this by adding&nbsp;`assets/stubs/new-page-template.md`&nbsp;to your own project.
* **Create documentation issue**\: Brings the user to a new issue form in your docs repo with the name of the current page as the issue’s title.
* **Create project issue**&nbsp;(optional): Brings the user to a new issue form in your project repo. This can be useful if you have separate project and docs repos and your users want to file issues against the project feature being discussed rather than your docs.

This page shows you how to configure these links.

Currently, DocsyCannon supports only GitHub repository links “out of the box”. Since GitLab can handle the same link scheme, it should work as well. If you are using another repository such as Bitbucket and would like generated repository links, feel free to&nbsp;[add a feature request or update our theme](https://www.docsy.dev/docs/contribution-guidelines/).

## Link configuration

There are four variables you can configure in

<font face="Inconsolata, monospace, sans-serif"><span style="font-size: 15.3px; white-space: pre-wrap; background-color: rgb(238, 238, 238);">config.yaml</span></font>&nbsp;to set up links.

### GitHub repository

The URL for your site’s source repository. This is used to generate the&nbsp;**Edit this page**,&nbsp;**Create child page**, and&nbsp;**Create documentation issue**&nbsp;links.​​​​​

### GitHub subdirectory

Specify a value here if your content directory is not in your repo’s root directory. For example, this site if your site is in the&nbsp;`userguide`&nbsp;subdirectory (folder) of its repo. Setting this value means that your edit links will go to the right page.

### GitHub project repository

Specify a value here if you have a separate project repo and you’d like your users to be able to create issues against your project from the relevant docs. The&nbsp;**Create project issue**&nbsp;link appears only if this is set.

### GitHub branch

Specify a value here if you have would like to reference a different branch for the other GitHub settings like&nbsp;**Edit this page**&nbsp;or&nbsp;**Create project issue**.