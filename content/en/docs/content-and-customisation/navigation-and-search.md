---
_schema: default
title: Navigation and Search
linkTitle: Navigation and Search
weight: 3
description: |
  Customize site navigation and search for your Docsy site.
categories:
  - Navigation
  - Search
tags:
  - Nav
  - Navigation
  - Search
  - GCSE
  - Google Search
  - Algolia
---
## Top-level menu

The top level menu (the one that appears in the top navigation bar for the entire site) uses your site’s main menu. Any page made in CloudCannon through the Pages collection will appear in this menu.

The menu is ordered from left to right by page&nbsp;`weight`. So, for example, a section index or page with&nbsp;`weight: 30`&nbsp;would appear after the Documentation section in the menu, while one with&nbsp;`weight: 10`&nbsp;would appear before it.

### Adding a version drop-down

If you add some versions in the Versioning section of the Data collection, the DocsyCannon theme adds a version selector drop down to the top-level menu.

You can find out more in the guide to&nbsp;[versioning your docs](https://www.docsy.dev/docs/adding-content/versioning/).

### Adding a language drop-down

If you configure more than one language in&nbsp;`hugo.toml`, the DocsyCannon theme adds a language selector drop down to the top-level menu. Selecting a language takes the user to the translated version of the current page, or the home page for the given language.

You can find out more in&nbsp;[Multi-language support](https://www.docsy.dev/docs/language/).

## Sidebar Menu

The sidebar menu, as shown in the left side of the&nbsp;`documentation`&nbsp;section, is automatically built from the contents of the section.

Like the top-level menu, the sidebar menu is ordered by weight.

### Sidebar menu options

By default, the sidebar menu shows the current docs section fully expanded all the way down. This may make the left nav too long and difficult to scan for bigger sites. Try setting site parameter&nbsp;`sidebar_menu_foldable = true`&nbsp;in the Navbar section of the site Data collection.

The upper limit for how many pages are displayed in the sidebar menu is controlled by `sidebar_menu_truncate.`&nbsp;By default this is set to 50, so no more than 50 pages will show in the sidebar menu.

On large sites (default: &gt; 2000 pages) the sidebar menu is not generated for each page, but cached for the whole section. The HTML classes for marking the active menu item (and menu path) are then set using JS. You can adjust the limit for activating the cached section menu with the optional parameter&nbsp;`sidebar_cache_limit `in the Navbar section of the site Data collection.

## Breadcrumb navigation

Breadcrumb navigation links appear at the top of each page by default. To disable breadcrumb navigation, set&nbsp;`breadcrumb_disable`&nbsp;as true in the User Interface section of the sites Data collection.

Breadcrumb navigation links are also shown for each item on the taxonomy results page (i.e. when you click one of the taxonomy labels, e.g. Tags/Categories). These breadcrumbs can be disabled by setting&nbsp;`taxonomy_breadcrumb_disable`&nbsp;to true in the User Interface section of the sites Data collection.

## Site search options

DocsyCannon offers multiple options that let your readers search your site content, so you can pick one that suits your needs. You can choose from:

* [Google Custom Search Engine](https://programmablesearchengine.google.com/about/)&nbsp;(GCSE), the default option, which uses Google’s index of your public site to generate a search results page. This is an easy to set up option, all you need to do is add a GCSE ID and then set it up on the GCSE dashboard.

* <a target="_blank" rel="noopener" href="https://docsearch.algolia.com/">Algolia DocSearch</a>, which uses Algolia’s indexing and search mechanism, and provides an organized dropdown of search results when your readers use the search box. Algolia DocSearch is free for public documentation sites. This is slightly more complex to add to your site and requires adding to the source code. Enter scripts for Algolia in `layouts/partials/hooks/body-end.html` and style sheets in&nbsp;`layouts/partials/hooks/head-end.html`.

### Disabling the sidebar search box&nbsp;

By default, the search box appears in both the top navigation bar and at the top of the sidebar left navigation pane. If you don’t want the sidebar search box, turn off Algolia DocSearch and remove any GCSE ID in Sidebar Settings section of the sites Data collection.

## Configure search with a Google Custom Search Engine

To enable this feature, you’ll first need to make sure that you have built and deployed a production version of your site, as otherwise your site won’t be crawled and indexed.

### Setting up site search

1. Create a Google Custom Search Engine for your deployed site by clicking&nbsp;**New search engine**&nbsp;on the&nbsp;[Custom Search page](https://cse.google.com/cse/all)&nbsp;and following the instructions. Make a note of the ID for your new search engine.

2. Add any further configuration you want to your search engine using the&nbsp;**Edit search engine**&nbsp;options. In particular you may want to do the following:

   * Select&nbsp;**Look and feel**. Change from the default&nbsp;**Overlay**&nbsp;layout to&nbsp;**Results only**, as this option means your search results are embedded in your search page rather than appearing in a separate box. Click&nbsp;**Save**&nbsp;to save your changes.

   * Edit the default result link behavior so that search results from your site don’t open in a new tab. To do this, select&nbsp;**Search Features**&nbsp;-&nbsp;**Advanced**&nbsp;-&nbsp;**Websearch Settings**. In the&nbsp;**Link Target**&nbsp;field, type “\_parent”. Click&nbsp;**Save**&nbsp;to save your changes.

<div><h4> </h4>{{< alert color="info" title="Tip" >}}Your site search results should show up within a couple of days. If it takes longer than that, you can manually request that your site is indexed by submitting a sitemap through the Google Search Console.{{< /alert >}}</div>

## Configure Algolia DocSearch

As an alternative to GCSE, you can use&nbsp;[Algolia DocSearch](https://docsearch.algolia.com/)&nbsp;with this theme. Algolia DocSearch is free for public documentation sites. DocsyCannon supports Algolia DocSearch v3.

### Sign up for Algolia DocSearch

Complete the form at&nbsp;[https://docsearch.algolia.com/apply/](https://docsearch.algolia.com/apply/).

If you are accepted to the program, you will receive the code to add to your documentation site from Algolia by email.

### Adding Algolia DocSearch

1. Enable Algolia DocSearch in the Search section of the sites Data collection.&nbsp; &nbsp;&nbsp;

2. Disable the sidebar search in&nbsp;`hugo.toml`/`hugo.yaml`/`hugo.json`&nbsp;as this is not currently supported for Algolia DocSearch. See&nbsp;[Disabling the sidebar search box](https://www.docsy.dev/docs/adding-content/navigation/#disabling-the-sidebar-search-box).

3. Add the CSS and JS to use Algolia to the head and body of every page in your site.

   * In&nbsp;`head-end.html`&nbsp;add the DocSearch CSS:

     <div><p><code class="language-html"><strong>&lt;</strong><strong>link</strong> rel<strong>=</strong>"stylesheet" href<strong>=</strong>"https://cdn.jsdelivr.net/npm/@docsearch/css@3" <strong>/&gt;</strong></code></p></div>
   * In&nbsp;`body-end.html`&nbsp;add the DocSearch script, replacing the&nbsp;`docsearch`&nbsp;details with the snippet you get from Algolia (the example below is Algolia’s own site index!). You must provide&nbsp;`#docsearch`&nbsp;as your&nbsp;`container`&nbsp;value as that’s the ID of the&nbsp;`div`&nbsp;we provide in Docsy’s layout:

     <div><p><code class="language-html"><strong>&lt;</strong><strong>script</strong> src<strong>=</strong>"https://cdn.jsdelivr.net/npm/@docsearch/js@3"<strong>&gt;&lt;/</strong><strong>script</strong><strong>&gt;</strong><br /><strong>&lt;</strong><strong>script</strong> type<strong>=</strong>"text/javascript"<strong>&gt;</strong>docsearch<strong>({</strong><br />&nbsp; container<strong>:</strong> '#docsearch'<strong>,</strong><br />&nbsp; appId<strong>:</strong> 'R2IYF7ETH7'<strong>,</strong><br />&nbsp; apiKey<strong>:</strong> '599cec31baffa4868cae4e79f180729b'<strong>,</strong><br />&nbsp; indexName<strong>:</strong> 'docsearch'<strong>,</strong><br />&nbsp; <strong>});&lt;/</strong><strong>script</strong><strong>&gt;</strong></code></p></div>

You can find out more about how to configure DocSearch in the Algolia DocSearch V3&nbsp;[Getting started](https://docsearch.algolia.com/docs/DocSearch-v3)&nbsp;guide.

When you’ve completed these steps, Algolia search should be enabled on your site. Search results are displayed as a pop-up, so you don’t need any search results page.