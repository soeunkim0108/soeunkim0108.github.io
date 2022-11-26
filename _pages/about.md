---
title: About
author: Tao He
date: 2022-02-04
category: Jekyll
layout: post
---

## Why Jekyll with GitBook

GitBook is an amazing frontend style to present and organize contents (such as book chapters
and blogs) on Web. The typical to deploy GitBook at [Github Pages][1]
is building HTML files locally and then push to Github repository, usually to the `gh-pages`
branch. It's quite annoying to repeat such workload and make it hard for people do version
control via git for when there are generated HTML files to be staged in and out.

This theme takes style definition out of generated GitBook site and provided the template
for Jekyll to rendering markdown documents to HTML, thus the whole site can be deployed
to [Github Pages][1] without generating and uploading HTML bundle every time when there are
changes to the original repo.

## How to Get Started

This theme can be used just as other [Jekyll themes][1] and support [remote theme][2],
see [the official guide][3] as well.

You can introduce this jekyll theme into your own site by either

- [Fork][4] this repository and add your markdown posts to the `_posts` folder.
- Use as a remote theme in your [`_config.yml`][5](just like what we do for this
  site itself),

```yaml
remote_theme: sighingnow/jekyll-gitbook
```

## License

This work is open sourced under the Apache License, Version 2.0.

Copyright 2019 Tao He.

[1]: https://pages.github.com
[2]: https://rubygems.org/gems/jekyll-remote-theme
[3]: https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll
[4]: https://github.com/sighingnow/jekyll-gitbook/fork
[5]: https://github.com/sighingnow/jekyll-gitbook/blob/master/_config.yml
