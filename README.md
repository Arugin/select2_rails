#Select2 for Rails asset pipeline

[Select2](https://github.com/select2/select2) is a jQuery based replacement for select boxes. It supports searching, remote data sets, and infinite scrolling of results.

This repo is a continuation of the dead [select2-rails](https://github.com/argerim/select2-rails) project.

The `select2_rails` gem integrates the `Select2` jQuery plugin with the Rails asset pipeline.

[![Gem Version](https://badge.fury.io/rb/select2-rails.png)](http://badge.fury.io/rb/select2-rails)

## Usage

### Install select2_rails gem

Add `select2_rails` to your Gemfile and run `bundle install`:

	gem "select2_rails"

### Include select2_rails javascript assets

Add the following to your `app/assets/javascripts/application.js`:

	//= require select2

alternatively, for the [full build](http://select2.github.io#builds):

    //= require select2.full

### Include select2_rails stylesheet assets

Add to your `app/assets/stylesheets/application.css`:

	*= require select2

If you are using Twitter Boostrap you need to also require the bootstrap theme CSS in addition to the above require.

	*= require select2-bootstrap

To apply the theme, tell Select2 to do so by passing `bootstrap` to the [`theme`](https://select2.github.io/examples.html#themes) option when initializing Select2:

    $( "#dropdown" ).select2({
        theme: "bootstrap"
    });

## Internationalization (i18n)

The `select2_rails` now supports multiple languages.

Add the following to your `app/assets/javascripts/application.js`:

	//= require select2_locale_"any possible language"

Possible languages:

	az, bg, ca, cs, da, de, en, es, et, eu, fi, fr, gl, hi, hr, hu, id, is, it, lt, lv, mk, nb, nl, pl, pt-BR, pt, ro, ru, sk, sr, sv, th, tr, uk, vi, zh-CN, zh-TW

## Fix
### IE8 Invalid Character
IE8 doesn't support some unescaped Unicode character and need to quote keys in object literals
You need some configurations for [Uglifier](https://github.com/lautis/uglifier) to do the work.
Add to your `config/environments/production.rb`

       require 'uglifier'
       config.assets.js_compressor = Uglifier.new(output: {ascii_only: true, quote_keys: true})

## Contributions

If you want to contribute, please:

* Fork the project.
* Make your feature addition or bug fix.
* Send me a pull request on Github.

## License

selec2_rails is released under the [MIT License](http://www.opensource.org/licenses/MIT).
