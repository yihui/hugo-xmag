# HUGO XMAG

**XMag** is designed based on the Hugo theme [**XMin**](https://github.com/yihui/hugo-xmin), and similarly, features minimalism but with a magazine style on the homepage inspired by [The Signpost](https://en.wikipedia.org/wiki/Wikipedia:Wikipedia_Signpost) on Wikipedia.

This theme includes a few cool features:

- Responsive article summary blocks on homepage

- Thumbnails in summary blocks

- Magazine title in Blackletter (&Bfr;&Lfr;&Afr;&Cfr;&Kfr; &Lfr;&Efr;&Tfr;&Tfr;&Efr;&Rfr;)

- Github edit links

- Author info and site info at the bottom of an article

- MathJax for LaTeX math expressions

It also supports features that are probably not even worth mentioning:

- Google Analytics

- highlight.js for syntax highlighting of code blocks

- Display categories and tags on single pages

- Table of contents for single pages

Most features can be configured through `config.toml`, and a few can be enabled by custom layouts. Please see the detailed documentation on the [About](https://xmag.yihui.org/about/) page of the theme website. The source code is available [on Github](https://github.com/yihui/hugo-xmag) (MIT license).

## Quickstart guide

If you are an R user, the easiest way to get started with this theme is to install the **blogdown** package, and [use `blogdown::new_site()` to create a new site](https://bookdown.org/yihui/blogdown/a-quick-example.html):

```r
install.packages('blogdown')
blogdown::new_site(theme = 'yihui/hugo-xmag')
```

If you do not use R, please read on.

**Watch out** The standard [Quickstart Guide](https://gohugo.io/getting-started/quick-start/) fails. In Step 3 do not proceed past `git init`. 

Then, to install this theme in your Hugo site

1.  Download this repo and unzip it
1.  Change directory to the site root
1.  Copy the downloaded theme into `themes/`: `cp -r ~/Downloads/hugo-mag-master themes/hugo-mag`
1.  Copy the example site into your site root: `cp -r themes/hugo-mag/exampleSite .` 

Now resume the Quickstart Guide at Step 5.

[![Screenshot](https://github.com/yihui/hugo-xmag/raw/master/images/screenshot.png)](https://xmag.yihui.org)
