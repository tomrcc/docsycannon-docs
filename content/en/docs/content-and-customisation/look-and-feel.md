---
_schema: default
title: Look and Feel
linkTitle: Look and Feel
description: Customise colors, fonts and more for your site.
weight: 2
categories:
  - Customisation
tags:
  - Customisation
  - Editing
  - Colors
  - Navbar
  - Code Highlighting
---
## Colors

Colors for the site can be easily changed in the colors section of the Data collection.<br><br>If you have developer experience, more color options can be added by updating `_variables.scss` and&nbsp;`fetch-color.js` in the source code. Follow the format already there for the existing color options, and rebuild in CloudCannon, or run&nbsp;`npm start`&nbsp;locally.

## Navbar

For pages beginning with a Cover bookshop component, like most homepages, the navbar is translucent as long as the hero image hasn’t scrolled up past the navbar. This initial translucent setting ensures that the hero image is maximally visible.

After the hero image has scrolled past the navbar, the navbar’s (opaque) background color is set – to the site’s primary color.

The text of navbar entries can be difficult to read with some hero images. In these cases, you can disable navbar translucency by setting the&nbsp;`translucent_over_cover_disable`&nbsp;option to&nbsp;`true`&nbsp;in your site’s Data collection.

By default the navbar does not display your logo in the top left. To enable a logo navigate to the Navbar section of your sites Data file, turn on `Navbar Logo` and ensure the correct path to your logo image is entered.

## Code Highlighting

You can change the default style for code highlighting by going to your config.yaml and changing the style from `tango` like shown below:

```yaml
markup:
  goldmark:
    renderer:
      unsafe: true
  highlight:
    # See a complete list of available styles at https://xyproto.github.io/splash/docs/all.html
    style: tango
    # Uncomment if you want your chosen highlight style used for code blocks without a specified language
    # guessSyntax: "true"
```