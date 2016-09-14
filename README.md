# After Dark

A retro dark theme for [Hugo](https://gohugo.io/).

![Theme screenshot](https://cloud.githubusercontent.com/assets/440298/18599964/ae2ea6de-7c20-11e6-889c-db5ca4afef67.png)

> Simplicity is the ultimate sophistication<br>
> --- Leonardo da Vinci

## Features

- Dark theme intended for low-light reading
- Entire page served in a single HTTP request (including favicon)
- Grid layouts and more using [hack.css](hackcss.com)
- Responsive typography optimized for mobile, tablet and desktop
- [Block Templates](https://gohugo.io/templates/blocks/) for foolproof layouts
- Google Analytics tracking using the [internal async template](https://gohugo.io/extras/analytics#configuring-google-analytics)
- Rich post byline including word count and reading time
- Extensible [taxonomy terms template](https://gohugo.io/templates/terms)
- Related posts feature guides users to similar content
- Configurable [menu system](https://gohugo.io/extras/menus/) for global site navigation
- Simple list pagination with page indicators
- Custom archetypes, meta descriptions and rel meta for SEO control
- Default 404 page with engaging MP4 background video
- Full site keyboard accessibility
- No JavaScript for predictable use on terminal-based browsers

## Getting started

From your Hugo site directory, run:

```shell
(cd themes; git clone git@github.com:comfusion/after-dark.git)
hugo serve --theme=after-dark
```

Copy the custom archetypes to your site:

```shell
cp themes/after-dark/archetypes/* archetypes
```

Include the following in your site's `config.toml`:

```toml
baseurl = "https://c74ce35e.ngrok.io" # Controls base URL
languageCode = "en-US" # Controls html lang attribute
title = "After Dark" # Homepage title and page title suffix
paginate = 5 # Number of posts to show before paginating

enableRobotsTXT = true # Suggested, enable robots.txt file
googleAnalytics = "" # Optional, add tracking Id for analytics
SectionPagesMenu = "main" # Enable menu system for lazy bloggers

[params]
  description = "" # Suggested, controls homepage description meta
  author = "" # Optional, controls author name display on posts
  show_menu = false # Optional, set false to disable menu entirely
  powered_by = true # Optional, set false to disable theme credits
```

Configure menu in `config.toml` if desired:

```toml
[menu]
  [[menu.main]]
    name = "Home"
    weight = 0
    identifier = "home"
    url = "/"
  [[menu.main]]
    name = "Posts"
    weight = 1
    identifier = "post"
    url = "/post/"
```

Add pages to the menu from page frontmatter:

```toml
menu = "main"
weight = 3
```

## Upgrading hack.css

The specific version of [`hack.css`](hackcss.com) used is _pinned_ in the `package.json` dependency manifest. To check for updates do an `npm i` and run `npm run ncu`.

If an update is available consider taking the automatic update, but keep the version pinned in the manifest. Once the new `hack` dependency version is pulled down to the `node_modules` directory, copy the contents of `hack.css` and `dark.css` into the `critical-vendor.css.html` file.

Once the vendor file is updated pop open your favorite dev tools and test the changes by previewing your site on mobile, tablet and desktop at different display resolutions and orientations. Make any tweaks necessary to the `hack.css` style overrides indicated in `critical-custom.css.html`.

## Contributing

Issues have been disabled for this repo. If you feel passionate something needs to be changed please feel free to submit a pull with your suggested changes.
