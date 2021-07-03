![License](https://img.shields.io/badge/license-MIT-blue)

# Jekyll-Minima with Bootstrap5 Boilerplate Template

*Minima is a one-size-fits-all Jekyll theme for writers*. It's Jekyll's default (and first) theme. It's what you get when you run `jekyll new`.

This repository can be used as a boilerplate template for create Bootstrap 5 websites using *Jekyll Website Builder*.

[Theme preview](https://nuwanj.github.io/jekyll-minima-bootstrap-5-boilerplate/)

## Installation

Add this line to your Jekyll site's Gemfile:

```ruby
gem "minima"
```

And then execute:
```sh
bundle
```

## Contents At-A-Glance

Minima has been scaffolded by the `jekyll new-theme` command and therefore has all the necessary files and directories to have a new Jekyll site up and running with zero-configuration.

### Layouts

Refers to files within the `_layouts` directory, that define the markup for your theme.

  - `default.html` &mdash; The base layout that lays the foundation for subsequent layouts. The derived layouts inject their contents into this file at the line that says ` {{ content }} ` and are linked to this file via [FrontMatter](https://jekyllrb.com/docs/frontmatter/) declaration `layout: default`.
  - `page.html` &mdash; The layout for your documents that contain FrontMatter, but are not posts.
  - `post.html` &mdash; The layout for your posts.

#### Home Layout

`home.html` is a flexible HTML layout for the site's landing-page / home-page / index-page. <br/>

##### *Main Heading and Content-injection*

From Minima v2.2 onwards, the *home* layout will inject all content from your `index.md` / `index.html` **before** the **`Posts`** heading. This will allow you to include non-posts related content to be published on the landing page under a dedicated heading. *We recommended that you title this section with a Heading2 (`##`)*.

Usually the `site.title` itself would suffice as the implicit 'main-title' for a landing-page. But, if your landing-page would like a heading to be explicitly displayed, then simply define a `title` variable in the document's front matter and it will be rendered with an `<h1>` tag.

##### *Post Listing*

This section is optional from Minima v2.2 onwards.<br/>
It will be automatically included only when your site contains one or more valid posts or drafts (if the site is configured to `show_drafts`).

The title for this section is `Posts` by default and rendered with an `<h2>` tag. You can customize this heading by defining a `list_title` variable in the document's front matter.


### Includes

Refers to snippets of code within the `_includes` directory that can be inserted in multiple layouts (and another include-file as well) within the same theme-gem.

  - `analytics.html` &mdash; Inserts Google Analytics module (active only in production environment).
  - `footer.html` &mdash; Defines the site's footer section.
  - `head.html` &mdash; Code-block that defines the `<head></head>` in *default* layout.
  - `head.html` &mdash; Defines the site's main header section. By default, pages with a defined `title` attribute will have links displayed here.
  - `meta.html` &mdash; Defines the site's meta tags and tags related to SEO in here.
  - `navbar.html` &mdash; Navbar and its content can be defined in here.

### Plugins

Minima comes with [`jekyll-seo-tag`](https://github.com/jekyll/jekyll-seo-tag) plugin preinstalled to make sure your website gets the most useful meta tags. See [usage](https://github.com/jekyll/jekyll-seo-tag#usage) to know how to set it up.

## Usage

Have the following line in your config file:

```yaml
theme: NuwanJ/jekyll-minima-bootstrap-5-boilerplate
```

### Customizing templates

To override the default structure and style of minima, simply create the concerned directory at the root of your site, copy the file you wish to customize to that directory, and then edit the file.
e.g., to override the [`_includes/head.html `](_includes/head.html) file to specify a custom style path, create an `_includes` directory, copy `_includes/head.html` from minima gem folder to `<yoursite>/_includes` and start editing that file.

### Change default date format

You can change the default date format by specifying `site.minima.date_format`
in `_config.yml`.

```
# Minima date format
# refer to http://shopify.github.io/liquid/filters/date/ if you want to customize this
minima:
  date_format: "%b %-d, %Y"
```

### Author Metadata

From `Minima-3.0` onwards, `site.author` is expected to be a mapping of attributes instead of a simple scalar value:

```yaml
author:
  name: John Smith
  email: "john.smith@foobar.com"
```

To migrate existing metadata, update your config file and any reference to the object in your layouts and includes as summarized below:

Minima 2.x    | Minima 3.0
------------- | -------------------
`site.author` | `site.author.name`
`site.email`  | `site.author.email`


### Enabling Google Analytics

To enable Google Analytics, add the following lines to your Jekyll site:

```yaml
  ga_tracking: UA-NNNNNNNN-N
```

Google Analytics will only appear in production, i.e., `JEKYLL_ENV=production`

## Available Scripts

You can use following script files:
- */scripts/setup* : Setup the website
- */scripts/build* : Build the website
- */scripts/cibuild* : Script to test the build result in CI
- */scripts/run* : Build and run the website on *127.0.0.1:4000*

## License

The theme is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
