# Beautiful Hugo - A port of Beautiful Jekyll Theme

![Beautiful Hugo Theme Screenshot](https://github.com/halogenica/beautifulhugo/blob/master/images/screenshot.png)

## Why fork from the original repo?

The original repo is great but it doesn't suit for the Chinese language and China users because of some well known reasons.

There are some additional features beside of the original Beautiful-hugo theme:

- Support Chinese word count
- Mobile devices adaptive
- Use Baidu Analysis(百度统计)
- Use prism for syntax highlighting
- Use algolia for searching
- [livere（来必力）](https://livere.com) 评论插件
## Installation

```bash
$ mkdir themes
$ cd themes
$ git clone https://github.com/rootsongjc/beautifulhugo.git beautifulhugo
```

See [the Hugo documentation](http://gohugo.io/themes/installing/) for more information.

## Usage

Let me show you how to add and debug a new post and push it to Github pages and building a new searching index.

### 1. Add a new post

Use this command to create a new post:

```
hugo add posts/new.md
```

After the new post created, it is located at `./content/posts/new.md`.

### 2. Post head matters

Classic example:

```yaml
date: "2017-06-01T20:18:57+08:00"
draft: false
title: "微服务管理框架service mesh——istio安装笔记"
subtitle: "手把手教你安装Istio service mesh"
categories: "cloud-native"
tags: ["kubernetes","istio","service-mesh"]
description: "对文章的简要描述 SEO used for description"
bigimg: [{src: "https://res.cloudinary.com/jimmysong/image/upload/images/2017052801.jpg", desc: "Beijing China|May 28,2017"}]
nocomment: true
postmeta: false
```

**bigimg**：an array, you can specify multiple images in map lists.

**postmeta**：whether show the post meta data below a post title/subtitle

**nocomment**: whether show the comment box

### 3. Preview and debug

Execute this command the build a preview:

```
hugo server
```

Visit [http://localhost:1313](http://localhost:1313/) for the website preview.

**4. Update algolia index**

Execute this command to build a new algolia index at the project's base path:

```
hugo-alogolia
grep -v '"content":' algolia.json>rootsongjc-hugo.json
rm -f algolia.json
```

As the new post created there should be a new record added to this file `public/rootongjc-hugo.json`.

## Acknowledgements

- [AddThis](https://www.addthis.com/): social share botton
- [Algolia](https://www.algolia.com/): search platform
- [autocomplete.js](https://github.com/algolia/autocomplete.js): search frontend
- [Baidu analysis](http://tongji.baidu.com/): website analysis
- [Beautiful Hugo](https://github.com/halogenica/beautifulhugo): theme
- [Bitlinks](https://bitly.com/) Short links
- [Cloudfare](https://www.cloudflare.com/): DNS and https
- [Cloudinary](https://www.cloudinary.com/): CDN and static images hosting
- [Github Pages](https://pages.github.com/): website hosting
- [Gitment](https://github.com/imsun/gitment): comments plugin
- [Hugo](https://gohugo.io/): static website builder
- [Hugo-algolia](https://www.npmjs.com/package/hugo-algolia): index json builder
- [Namecheap](https://namecheap.com/): domain name registry
- [Prism](http://prism.com/): code highlight

---

## Extra Features

### Responsive

This theme is designed to look great on both large-screen and small-screen (mobile) devices.

### Syntax highlighting

This theme has support for both server side and client side highlighting.

#### Server side syntax highlighting

Use the `highlight` shortcode (with Pygments),
see [the Hugo documentation](http://gohugo.io/extras/highlighting/) for more information.

To use this feature install Pygments (`pip install Pygments`) and add `pygmentsuseclasses = true` to your `config.toml`.

#### Client side syntax highlighting

Use triple backticks ( ``` ) or triple tilde ( ~~~ ) around code blocks.

Client side highlighting does not require pygments to be installed.

### Disqus support

To use this feature, uncomment and fill out the `disqusShortname` parameter in `config.toml`.

### Google Analytics

To add Google Analytics, simply sign up to [Google Analytics](http://www.google.com/analytics/) to obtain your Google Tracking ID, and add this tracking ID to the `googleAnalytics` parameter in `config.toml`.

### Commit SHA on the footer

If the source of your site is in a Git repo, the SHA corresponding to the commit the site is built from can be shown on the footer. To do so, two environment variables have to be set (`GIT_COMMIT_SHA` and `GIT_COMMIT_SHA_SHORT`) and parameter `commit` has to be defined in the config file:

```yaml
[Params]
  commit = "https://github.com/<username>/<siterepo>/tree/"
```

This can be achieved by running the next command prior to calling Hugo:

```bash
  GIT_COMMIT_SHA=`git rev-parse --verify HEAD` GIT_COMMIT_SHA_SHORT=`git rev-parse --short HEAD`
```

See at [xor-gate/xor-gate.org](https://github.com/xor-gate/xor-gate.org) an example of how to add it to a continuous integration system.

## About

This is a port of the Jekyll theme [Beautiful Jekyll](http://deanattali.com/beautiful-jekyll/) by [Dean Attali](http://deanattali.com/aboutme#contact). It supports most of the features of the original theme.

## License

MIT Licensed, see [LICENSE](https://github.com/halogenica/Hugo-BeautifulHugo/blob/master/LICENSE).
