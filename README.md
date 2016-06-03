# Octopress Minify Html

[![Gem Version](https://badge.fury.io/rb/octopress-minify-html.svg)](http://badge.fury.io/rb/octopress-minify-html)
[![Build Status](https://travis-ci.org/octopress/minify-html.svg)](https://travis-ci.org/octopress/minify-html)


Minify Jekyll's HTML output with [HtmlPress](https://github.com/stereobooster/html_press)

## Installation

### Using Bundler

Add this gem to your site's Gemfile in the `:jekyll_plugins` group:

    group :jekyll_plugins do
      gem 'octopress-minify-html'
    end

Then install the gem with Bundler

    $ bundle

### Manual Installation

    $ gem install octopress-minify-html

Then add the gem to your Jekyll configuration.

    gems:
      - octopress-minify-html

## Usage

After installing, Jekyll's HTML output will be minified by default. If you configure `env` in your Jekyll configuration, HTML will be minified only when
`env` is set to production.

```yml
env: production
```

You can override the default behavior by setting the `minify_html` config.
For example, this will disable minification, regardless of your `env` setting.

```yml
minify_html: false
```

### Example Configuration

1. In `_config.yml`, insert:

   ```yaml
   minify_html: false
   ```

2. In a new config file, `_config_production.yml`, insert:

   ```yaml
   minify_html: true
   ```
3. In development, build Jekyll normally:

   ```shell
   jekyll build   # or jekyll serve
   ```
   For a production build, run:

   ```shell
   jekyll build --config _config.yml,_config_production.yml
   ```


## HtmlPress Configuration:

You can set configuration options for [HtmlPress](https://github.com/stereobooster/html_press) in your Jekyll configuration like this:

```
html_press:
  unquoted_attributes: false
  drop_empty_values: false
  strip_crlf: false
  js_minifier_options: false
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
