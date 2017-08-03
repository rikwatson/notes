# Hugo

A static site generator written in Go.

Upload to Amazon S3 & use [hugomac](https://github.com/nickoneill/hugomac) from the OS-X Menu Bar.

Read the `Hugo` [Quickstart](https://gohugo.io/overview/quickstart/)

## [Front Matter](https://gohugo.io/content/front-matter/)

TOML configuration looks like this

```toml
+++
date = "2016-02-14T16:11:58+05:30"
draft = true
title = "Good to Great Book Review"
lastmod = 2015-12-23
tags = [ ".vimrc", "plugins", "spf13-vim", "vim" ]
date = "2012-04-06"
categories = [
  "Development",
  "VIM"
]
+++
```

Also supports

 * TOML, identified by `+++`.
 * YAML, identified by `---`.
 * JSON, a single JSON object which is surrounded by `{` and `}`, each on their own line.

