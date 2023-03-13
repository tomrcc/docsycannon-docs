---
_schema: index
title: Multi-Language Support
linkTitle: Multi-Language Support
weight: 9
description: Support multiple languages in your site.
categories:
  - Languages
  - Translations
tags:
  - Languages
  - Translations
---
If you’d like to provide site content in multiple languages, the DocsyCannon theme and Hugo make it easy to both add your translated content and for your users to navigate between language versions. Recommended to have some experience with Hugo.

## Content and configuration

To add content in multiple languages, you first need to define the available languages in a&nbsp;`languages`&nbsp;section in your site configuration. Each language can have its own language-specific configuration. For example, the DocsyCannon Example Site config specifies that it provides content in English and Norwegian, and that the language version visitors will see by default is English:​​​​​​

Any setting not defined in a&nbsp;`[languages]`&nbsp;block will fall back to the global value for that setting: so, for example, the content directory used for the site above will be&nbsp;`content/en`&nbsp;unless the user selects the Norwegian language option.

Once you’ve updated your site config, you create a content root directory for each language version in your source repo, such as&nbsp;`content/en`&nbsp;for English text, and add your&nbsp;[content](https://www.docsy.dev/docs/adding-content/content/)&nbsp;as usual. See the&nbsp;[Hugo Docs](https://gohugo.io/content-management/multilingual)&nbsp;on multi-language support for more information.

{{< alert color="danger" title="Attention (only when using DocsyCannon as a Hugo module)" >}}If you have a multi language installation, please make sure that the section [languages] inside your configuration file is declared before the section [module] with the module imports. Otherwise you will run into trouble!{{< /alert >}}

{{< alert color="info" title="Tip" >}}If there’s any possibility your site might be translated into other languages, consider creating your site with your content in a language-specific subdirectory, as it means you don’t need to move it if you add another language.{{< /alert >}}

For adding multiple language versions of other site elements such as button text, see the internationalization bundles section below.

## Selecting a language

If you configure more than one language in your&nbsp;[configuration file](https://gohugo.io/getting-started/configuration/#configuration-file), the DocsyCannon theme adds a language selector drop down to the top-level menu. Selecting a language takes the user to the translated version of the current page, or the home page for the given language.

## Internationalization bundles

Coming soon.