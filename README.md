# simple-hugo

A Hugo theme using [Simple.css](https://simplecss.org).

This is a fairly simple theme I made for my [personal site](https://www.djpeacher.com) and probably doesn't include all the bells and whistles Hugo has to offer. If you need to customize anything, you can override your sites `layouts` folder. If you think something should be added that would benefit **everyone**, feel free to make a pull request!

### Quick Start

```
brew install hugo
```

```
hugo new site quickstart
cd quickstart
git init -b main
git submodule add https://github.com/djpeacher/simple-hugo.git themes/simple-hugo
echo theme = \"simple-hugo\" >> config.toml
hugo new posts/my-first-post.md
hugo server -D
```

### Settings

```yaml
baseURL: 'http://example.org/'
languageCode: en-us
title: My New Hugo Site # Used in title.
theme: simple-hugo
copyright: 'Made with ❤️ by Barry Bluejeans'
params:
  title: My New Hugo Site # Used in header > nav > h1.
  subtitle: Very Cool # Used in header > nav > p.
  replyEmail: me@example.com # If set, a reply button will appear at the end of posts in the /post directory.
  replyButton: Reply via email # You can override the text the reply button displays.
  light:
    ... # You can override any of the simple.css light theme colors here.
  dark:
    ... # You can override any of the simple.css light dark colors here.
  # Color names here: https://github.com/djpeacher/simple-hugo/blob/main/config.yaml
menu:
  # Use `url` for external links (which will open in a new tab).
  # Use `pageref` for internal links (which will highlight current nav link).
  main:
    - name: Link 1
      url: https://example.com # will open in new tab
      weight: 1
    - name: Link 2
      pageref: /link/
      weight: 2
    - name: Link 3
      pageref: /link/
      weight: 3
```

### GitHub Hosting
As a bonus, here is a GitHub Action you can use to quickly host your site on GitHub!
```yml
name: Build
on:
  push:
    branches: [main]
  workflow_dispatch:
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
        with:
          submodules: true
          fetch-depth: 0
      - uses: peaceiris/actions-hugo@v2
      - run: hugo --minify
      - uses: JamesIves/github-pages-deploy-action@v4.2.3
        with:
          branch: gh-pages
          folder: public
```
