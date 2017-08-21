---
title: About Hugo XMag
author: Yihui Xie
---

**XMag** is the second Hugo theme I have designed. It is based on my first Hugo theme [**XMin**](https://github.com/yihui/hugo-xmin), and similarly, features minimalism but with a magazine style on the homepage inspired by [The Signpost](https://en.wikipedia.org/wiki/Wikipedia:Wikipedia_Signpost) on Wikipedia. You can find its source code on Github: https://github.com/yihui/hugo-xmag (licensed under MIT).

# Features

This theme includes a few cool features:

- Responsive article summary blocks on homepage

- Thumbnails in summary blocks

- Magazine title in Blackletter (&Bfr;&Lfr;&Afr;&Cfr;&Kfr; &Lfr;&Efr;&Tfr;&Tfr;&Efr;&Rfr;)

- Github edit links

- Author info and site info at the bottom of an article

- Multiple authors of a single page

- MathJax for LaTeX math expressions

It also supports features that are probably not even worth mentioning:

- Google Analytics

- highlight.js for syntax highlighting of code blocks

- Display categories and tags on single pages

- Table of contents for single pages

Most features can be configured through `config.toml`, and a few can be enabled by custom layouts.

# config.toml

By default, your site title will be displayed at the top in Blackletter fonts if your web browser and operating system support Blackletter fonts. Essentially, for every English letter `X` in your site title, it is substituted with `&Xfr;`, e.g. the Blackletter version of `A` is `&Afr;` (&Afr;). Below are the letters from A to Z:

## &Afr;&Bfr;&Cfr;&Dfr;&Efr;&Ffr;&Gfr;&Hfr;&Ifr;&Jfr;&Kfr;&Lfr;&Mfr;&Nfr;&Ofr;&Pfr;&Qfr;&Rfr;&Sfr;&Tfr;&Ufr;&Vfr;&Wfr;&Xfr;&Yfr;&Zfr;

Alternatively, you can provide a banner image:

```toml
[params.banner]
    src = "/path/to/banner.png"
    alt = "alternative text on image"
```

By default, each summary block on the homepage contains the first 200 letters extracted from all paragraphs of an article. I find Hugo's built in `.Summary` often unsatisfactory (e.g. it may contain headings and code blocks, which really should not go to the summary), so I wrote my own version. It works much better and the size of most summary blocks will be the same, unless certain articles are really short. The length 200 can be customized via `params.summary_length`.

If you are not satisfied with the automatic summary, you can specify the `description` option in the (YAML) metadata of your Markdown document, e.g.,

```yaml
title: "My Cool Post"
description: "Please use this as the summary."
```

Each summary block may contain a thumbnail, which is the first image in an article if exists. You can override it by providing the `thumbnail` option in the meta data of your Markdown document, e.g.,

```yaml
---
title: "My Cool Post"
thumbnail: "/url/of/the/image"
---
```

For each page, this theme adds an edit link to the top-right if a parameter `github_edit` is provided, so that your reader may easily help you edit a page and submit a pull request on Github.

The page footer can be defined in `.Params.footer`, and the text is treated as Markdown. Below are some sample configurations:

```toml
[params]
    summary_length = 200
    github_edit = "https://github.com/yihui/hugo-xmag/edit/master/exampleSite/content/"
    footer = "&copy; [Yihui Xie](https://yihui.name) 2017"
```

There are a few phrases that you can "translate" (I didn't use Hugo's multi-language feature just because I'm lazy):

```toml
[params.text]
    about_author = "About the Author"
    author_delimiter = ", "
    back = "Back to Home"
    edit = "Edit this page"
    tags = "Tags: "
    truncated = " &hellip;"
    uncategorized = "Uncategorized"
```

You can define a data file under `data/` to store all authors information, e.g., you can use a TOML file `data/authors.toml` (or YAML/JSON):

```
"Alice Wonder" = "I'm Alice. More about me on [my homepage](http://example.com)."
"Yihui Xie" = "Hey this is Yihui. You don't want to follow me on Twitter @xieyihui."
```

Then for an article with an author name that can be found in `data/authors.toml`, the author info will be added to the bottom of a page. For example, on this page, you can find information about me. You can change the phrase "About the Author" by changing the parameter `about_author` in `config.toml`.

To add a table of contents to an article, you can add `toc: true` to the YAML metadata of the Markdown document.

# Custom layouts

Besides the custom layout^[If this is the first time you have heard about "customizing layouts", please read the Hugo documentation first: https://gohugo.io/themes/customizing/.] files `head_custom.html` and `foot_custom.html` supported in **XMin** (see [documentation](https://xmin.yihui.name/about/)), this theme added a few more layout files such as `banner.html`, `comments.html` and `info.html` under `layouts/partials/`. The first can be used to customize the banner. The second can be used to add a comment section, e.g., if you want to use Hugo's default Disqus template, just add this to `comments.html`:

```
{{ template "_internal/disqus.html" . }}
```

You can also append arbitrary text to each article through `info.html`. For example, you may declare copyrights or briefly introduce your site.

There are other partial templates in this theme and I encourage you to read the source code to figure out what they do.

# Final words

I feel the world has become so noisy that I'm often at a loss when looking at a web page, because there are so many things to distract me. I was heavily influenced by the book [_Amusing Ourselves to Death_](https://en.wikipedia.org/wiki/Amusing_Ourselves_to_Death) after I read it in early 2017. From then on, I was hoping to design a theme for a website that gives articles the top priority. Everything else must give way to articles. That is why the navigation menu is at the bottom instead of in the conventional position (top or sidebar). There isn't much to do other than reading an article when you open a page. By the way, this is a pure plain-text theme. You can certainly add images if you want, but this theme itself contains zero binary files. Out of my [OCD](https://en.wikipedia.org/wiki/Obsessive%E2%80%93compulsive_disorder), I was just trying to push the limits of web design without using any images or JavaScript libraries (I'm a totally amateur).^[I used MathJax and highlight.js anyway in this theme because they are helpful.]

I hope you can enjoy this theme. Again, the source code is [on Github](https://github.com/yihui/hugo-xmag). Happy hacking!
