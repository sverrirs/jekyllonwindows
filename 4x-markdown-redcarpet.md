---
layout: page
title: Installing Redcarpet Highlighter
prev:
  url: 4-markdown.html
  title: Markdown
next:
  url: 4-markdown.html
  title: Markdown
---

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