---
layout: page
title: Configure Markdown
step: 4
sidebar_title: Markdown
prev:
    url: 3-syntax-highlighting.html
    title: Syntax Highlighting
next:
    url: 5-wdm-gem.html
    title: Watch
---

Jekyll v3.x uses <a href="http://kramdown.gettalong.org/">kramdown</a> as its default Markdown engine and <a href="http://kramdown.gettalong.org/">Github</a> only supports kramdown. 

> You should normally not have to do anything unless you specifically want to use a different engine than _kramdown_. 

The kramdown engine supersedes both the `Rdiscount` or `Redcarpet` engines and if you're updating an existing site updating should be as simple as changing the Markdown setting to _kramdown_ in your site's configuration (or removing it entirely).

If you encounter issues with any of the Markdown engines try issuing the following gem command

```
gem install markdown
```

# Installing redcarpet
If you want to use the <a href="https://github.com/vmg/redcarpet">redcarpet</a> Markdown engine instead then first install it.

```
gem install redcarpet
```

Then update your `_config.yml` file to have the following lines 

```
markdown: redcarpet
```

To get Github-esque features (such as tables etc) enable the following extension in your `_config.yml` file

```
redcarpet:
  extensions: ["no_intra_emphasis", "fenced_code_blocks", "autolink", "tables", "strikethrough", "superscript", "with_toc_data"]
```

## Error dependency for redcarpet not found
In case you get dependency errors for redcarpet after installing it. Try removing all the data from your projects `Gemfile` and replacing it with 

```
source 'https://rubygems.org'
group :jekyll_plugins do
  gem "redcarpet"
end
```

