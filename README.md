# simple-hugo

> ⚠️ Work in progress.

A Hugo theme using [Simple.css](https://simplecss.org).

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
  updateHeader: false # If true, header will contain front matter title and description. If false, header will contain site title and subtitle and front matter will display in <main>. default: true
menu:
  headerTop: # Menu for header. Can be changed to headerBottom.
    - name: Link 1
      url: https://example.com # will open in new tab
      weight: 1
    - name: Link 2
      url: /link/
      weight: 2
    - name: Link 3
      url: /link/
      weight: 3
  footerTop: # Menu for footer. Can be changed to footerBottom.
    - name: Link 4
      url: https://example.com # will open in new tab
      weight: 1
    - name: Link 5
      url: /link/
      weight: 2
    - name: Link 6
      url: /link/
      weight: 3
```
