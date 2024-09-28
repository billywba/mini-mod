# Hugo Theme Mini

A fast, minimalist and responsive hugo theme.

![./images/screenshot.png](https://raw.githubusercontent.com/nodejh/hugo-theme-mini/master/images/screenshot.png)

- [Online demo](https://nodejh.github.io/hugo-theme-mini)
- [Example Site Source](https://github.com/billywba/mini-mod/tree/master/exampleSite)

Features:

- Fast
- Minimalist
- Responsive
- Archive
- Tags
- Obsidian/GitHub Callouts

## 1. Installation

Hugo needs to be installed in order to build and compile the site. Install Hugo here: [Hugo - Installation](https://gohugo.io/installation/).

The quick start guide can be found here: [Hugo - Quick Start](https://gohugo.io/getting-started/quick-start/).

### 1.1 As a Hugo Module (Recommended)

> [!WARNING]
> If you installed a [Hugo binary](https://gohugo.io/getting-started/installing/#binary-cross-platform), you may not have Go installed on your machine. To check if Go is installed:
>
> ```
> $ go version
> ```
>
> Go modules were considered production ready in v1.14. [Download Go](https://golang.org/dl/).

1. From your project's root directory, initiate the hugo module system if you haven't already:

   ```bash
   $ hugo mod init github.com/<your_user>/<your_project>
   ```

2. Add the theme's repo to your `hugo.toml`:

   ```toml
   theme = "github.com/billywba/mini-mod"
   ```

### 1.2 As a Git Submodule

1. Inside the folder of your Hugo site run:

   ```bash
   $ git submodule add https://github.com/billywba/mini-mod.git themes/mini
   ```

2. Add the theme's directory to your `hugo.toml`:

   ```toml
   theme = "mini-mod"
   ```

## 2. Getting Started

After installing the theme successfully it requires a few more steps to get your site running.

### 2.1 The Config File

Take a look inside the [`exampleSite`](https://github.com/billywba/mini-mod/tree/master/exampleSite) folder of this theme. You'll find a file called [`hugo.toml`](https://github.com/billywba/mini-mod/blob/master/exampleSite/hugo.toml). To use it, copy the [`hugo.toml`](https://github.com/billywba/mini-mod/blob/master/exampleSite/hugo.toml) in the root folder of your Hugo site. Feel free to change the strings in this theme.

### 2.2 Default Content Language

You can set default content language by `languageCode`:

```toml
defaultContentLanguage = "en-us"
```

Default is `en-us`. Now support:

- `en`: English
- `zh`: Chinese
- `nl`: Dutch
- `fr`: French
- `es`: Spanish
- `da`: Danish

More about multiple languages: [Multilingual Mode](https://gohugo.io/content-management/multilingual/).

### 2.3 Enabling Comments

To enable comments, add following to your config file:

- Disqus shortname: `disqusShortname: your-disqus-shortname`
- Enable Comment:

  ```toml
  [params]
  enableComments = true
  disqusShortname =  "your-disqus-shortname"
  ```

### 2.4 Enabling Google Analytics

To enable google analytics, add following to your config file:

- Google Analytics ID: `googleAnalytics: your-google-analytics-id`
- Enable Google Analytics:

  ```toml
  [params]
  enableGoogleAnalytics = true
  googleAnalytics = "your-google-analytics-id"
  ```

### 2.5 Logo and Favicon

You can replace the log in the top of each page and favicon with your own images. To do that put your own logo and favicon into the `images` directory of your website static directory, then named them `avatar.png` and `favicon.ico`. For example:

```
- content
- static
└── images
    ├── avatar.png
    └── favicon.ico
```

### 2.6 Nearly Finished

In order to see your site in action, run Hugo's built-in local server.

```bash
$ hugo server
```

Now enter http://localhost:1313 in the address bar of your browser.

### 2.7 Production

To run in production (e.g. to have Google Analytics show up), run `HUGO_ENV=production` before your build command. For example:

```bash
HUGO_ENV=production
```

Note: The above command will not work on Windows. If you are running Windows, use the below command:

```bash
set HUGO_ENV=production
hugo
```

## 3. Optional Configuration

### 3.1 Table of Contents

To enable table of contents, you could set `showToc` to `true`.

For example:

```toml
[params]
showToc = true
```

### 3.2 Disable Comments on a Single Post

You can set `enableComments` to `false` in front matter to disable disqus comments on a single post.

For example:

```yaml
---
title: Some title
enableComments: false
---
```

### 3.3 Custom CSS and JS

You can put your custom css and js files to `static` directory, or use remote css and js files which start with `http://` or `https://`.

For example:

```toml
[params]
customCSS = [
  "https://example.com/styles/remote.css",  # Remote CSS
  "css/local-style.css"                     # Local CSS
]

customJS = [
  "https://example.com/scripts/remote.js",  # Remote JS
  "js/local-script.js"                      # Local JS
]
```

### 3.4 Math Typesetting

Mathematical notation is enabled by [KaTeX](https://katex.org/).

- To enable KaTex globally set the parameter `math` to `true` in project’s configuration
- To enable KaTex on a per page basis include the parameter `math` to `true` in content files

### 3.5 Hidden Post Summary in Home Page

To hidden post summary in home page, you could set `hiddenPostSummaryInHomePage` to `true`, default is `false`.

For example:

```toml
[params]
hiddenPostSummaryInHomePage = true
```

## License

[MIT](https://github.com/billywba/mini-mod/blob/master/LICENSE.md)
