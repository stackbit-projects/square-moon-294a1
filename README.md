# Kagami

[![Build Status](https://travis-ci.org/kamikat/jekyll-theme-kagami.svg?branch=master)](https://travis-ci.org/kamikat/jekyll-theme-kagami)
[![Gem Version](https://badge.fury.io/rb/jekyll-theme-kagami.svg)](https://badge.fury.io/rb/jekyll-theme-kagami)

Simple and clean theme for Jekyll and GitHub Pages.

![Screenshot](https://s2.banana.moe/docs/kagami-preview@2x.png)

## Installation

Add this line to your Jekyll site's Gemfile:

```ruby
gem "jekyll-theme-kagami"
```

And add this line to your Jekyll site's `_config.yml`:

```yaml
theme: jekyll-theme-kagami
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install jekyll-theme-kagami

### GitHub Pages

Jekyll build is integrated with GitHub Pages with limited function. This section is intended for those who
want to use the theme with GitHub Pages hosted sites.

1. Download latest gem file from https://rubygems.org/gems/jekyll-theme-kagami
2. Run `gem unpack [path-to-downloaded-gem-file] --target=.` on jekyll site project folder
3. Delete the line `theme: ...` in `_config.yml`

Zip archive downloaded from release page may not work because GitHub does not pack necessary files from submodules.

Instruction 1 and 2 can also work when you decide to upgrade your installation.

## Usage

### Social account links

You can customize social account links by adding following lines to `_config.yml`

```yaml
github_username: my_github_username
twitter_username: my_twitter_username
instagram_username: my_instagram_username
```

You can customize footer by overriding `_includes/footer.html`.

### Syntax highlighting

Kagami support color schemes from [jekyll-pygments-themes](https://github.com/jwarby/jekyll-pygments-themes).

Add the following lines to choose a color scheme:

```yaml
color_scheme: github
```

### Comment service (Disqus or Gitalk)

Add the following lines to your Jekyll site to enable Disqus comment service:

```yaml
disqus_shortname: my_disqus_shortname
```

You can find out more about Disqus' shortnames [here](https://help.disqus.com/customer/portal/articles/466208).

For [Gitalk](https://github.com/gitalk/gitalk#options):

```yaml
gitalk:
  id: <clientID>
  secret: <clientSecret>
  repo: <repo>
  owner: <owner> # (optional) if not set, value of `github_username` will be used
  admin: <admin> # (optional) if not set, value of `github_username` will be used
  proxy: ...     # (optional)
```

By default, comment service will only be enabled in production mode, set an environment `JEKYLL_ENV=production` for local test.

If you don't want to comments for particular posts you can disable that by adding `comments: false` to the post's YAML Front Matter.

### Google Analytics

To enable Google Anaytics, add the following lines to your Jekyll site:

```yaml
google_analytics: UA-NNNNNNNN-N
```

Google Analytics will only appear in production, i.e., `JEKYLL_ENV=production`

### Navigation Bar

Pages and posts can be registered as navigation item with following frontmatter:

```yaml
navbar_title: Awesome Title # specifies the text to display as navigation item
```

Navigation items are ordered in alphabetical order by default in Jekyll. Adjust the order manually with a `position` value:

```yaml
position: 999
```

### Tags and category

Layout file `post-list` supports filtering by tag or category. Create pages with following frontmatter will generate a filtered post list.

```yaml
title: Title of Tag Page
layout: post-list
filter:
  - by_tag: tagname
```

To filter by both category and tags:

```yaml
filter:
  - by_tag: tagname
    by_category: category
```

Results from multiple filters are combined (logical 'or') into the result.

A more flexible filter strategy is supported by supplying liquid expression to `by_expression` parameter in which post object can be referenced by the name `post`.

### MathJax

You can use MathJax with Kramdown's [built-in support](https://kramdown.gettalong.org/syntax.html#math-blocks).

To enable [MathJax](https://www.mathjax.org/), add following lines to your site
or post's front matter stuff:

```yaml
mathjax: true
```

### Mermaid

To enable [mermaid](https://mermaid-js.github.io/mermaid/), add following line to
the site configuration or post's front matter stuff:

```yaml
mermaid: true
```

Code blocks with `mermaid` language tag should be transformed into diagrams.

### Use `.side-note` and `.retina2x`

Taking advantages of [Block/span IAL](https://kramdown.gettalong.org/syntax.html#block-ials),
Kagami supports extra elements in writing.

Add `{:.side-note}` notation after a paragraph (in a new line just after paragraph WITHOUT extra line breaks)
will style the paragraph as a sidenote. Sidenote will be pull to the left of
the page and only be visible in desktop mode.

Kagami is also optimized for high-res image display:

```markdown
![image@2x](path-to-image@2x.png){:.retina2x}
```

And the retina image will be scaled to half of it's original size in pixels.

## Contributing

Bug reports and pull requests are welcome on GitHub at <https://github.com/kamikat/jekyll-theme-kagami>. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## Development

To set up your environment to develop this theme, run `bundle install`.

Your theme is setup just like a normal Jekyll site! To test your theme, run `bundle exec jekyll serve -s example` and open your browser at `http://localhost:4000`. This starts a Jekyll server using your theme. Add pages, documents, data, etc. like normal to test your theme's contents. As you make modifications to your theme and to your content, your site will regenerate and you should see the changes in the browser after a refresh, just like normal.

When your theme is released, only the files in `_layouts`, `_includes`, and `_sass` tracked with Git will be released.

## License

The theme is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

