![geniem-github-banner](https://cloud.githubusercontent.com/assets/5691777/14319886/9ae46166-fc1b-11e5-9630-d60aa3dc4f9e.png)
# WordPress Dropin & Plugin Collection: Safe, Fast & Clean WordPress
[![Latest Stable Version](https://poser.pugx.org/devgeniem/wp-sanitize-accented-uploads/v/stable)](https://packagist.org/packages/devgeniem/wp-safe-fast-and-clean-collection) [![Total Downloads](https://poser.pugx.org/devgeniem/wp-safe-fast-and-clean-collection/downloads)](https://packagist.org/packages/devgeniem/wp-safe-fast-and-clean-collection) [![Latest Unstable Version](https://poser.pugx.org/devgeniem/wp-safe-fast-and-clean-collection/v/unstable)](https://packagist.org/packages/devgeniem/wp-safe-fast-and-clean-collection) [![License](https://poser.pugx.org/devgeniem/wp-safe-fast-and-clean-collection/license)](https://packagist.org/packages/devgeniem/wp-safe-fast-and-clean-collection)

This is WordPress plugin and dropin collection which enhances WordPress in multiple ways.

## Reasons
This package was created to handle multiple projects with `composer update`. We just include this collection into our `composer.json` and stick to the guidelines about which plugins should be included here. WordPress evolves with time and some plugins will propably be pointless at some point, if that happens we will remove those unneccessary plugins.

## Installation
```
$ composer require devgeniem/wp-safe-fast-and-clean-collection
```

## Guidelines
We only want to add minimal plugins which enhance small part of WordPress.

### WordPress should expose as little as possible about itself and plugins
* All unneccessary html comments and headers should be stripped away.

### WordPress shouldn't make any additional requests to wordpress.org or 3rd party services
* WordPress should disable anything related to updates of core/themes/plugins.
* WordPress shouldn't create unneccessary requests which either slow the page down or use cpu cycles without any additional value

### Cache as much as possible
* Caching reduces load and allows us to create faster sites

### Avoid situations where users can accidentally create errors
WordPress core development moves a bit slower with some enhancements. We will add plugins that provide fixes for problems like accented file uploads into this collection. Once those features or fixes are not needed anymore we will disable them from this package.

### Allow developers to define as much settings as possible in wp-config.php
Too many plugins have only wp-admin settings pages. We believe that most of the settings belong into code rather than the database.

### WordPress shouldn't install or contain unneccessary example data
* Core installation should create minimal amount of content
* Plugins shouldn't have example content when possible

## Requirements
* >= PHP 7.0
* WordPress
* Redis server for object caching
* Use composer to update your site rather than using WordPress auto updates

### Composer.json settings
For correct installation your project should define following installation paths in `extra` section:
```
extra: {
    "installer-paths": {
      "web/app/mu-plugins/{$name}/": ["type:wordpress-muplugin"],
      "web/app/plugins/{$name}/": ["type:wordpress-plugin"]
    },
    "dropin-paths": {
      "web/app/": ["type:wordpress-dropin"]
    }
}
```

We use bedrock styled names for `wp-content`. Replace `web/app` according for your project.

## Maintainers
[Onni Hakala](https://github.com/onnimonni)

## Changelog
[See the included CHANGELOG.md](CHANGELOG.md)

## License
Respect the licenses of used libraries. This readme and composer are licensed under MIT
