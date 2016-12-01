# Skip bundled
Skip parsing of scripts bundled in your WordPress theme. This is useful when you bundle scripts that are also used and added to the queue through [`wp_enqueue_script`](https://developer.wordpress.org/reference/functions/wp_register_script/) by plugins (like jQuery) in a bundle file.

[![Build Status](https://travis-ci.org/trendwerk/skip-bundled.svg?branch=master)](https://travis-ci.org/trendwerk/skip-bundled)

## Install
```sh
composer require trendwerk/skip-bundled
```

## Usage
```
$scripts = new \Trendwerk\SkipBundled\Scripts();
$scripts->init();

$scripts->add($handle);
```

Where `$handle` is the handle on which the script is registered in WordPress, by using [`wp_register_script`](https://developer.wordpress.org/reference/functions/wp_register_script/).


## Example
An example for jQuery:

```php
$scripts = new \Trendwerk\SkipBundled\Scripts();
$scripts->init();

$scripts->add('jquery-core');
```

_Note: jQuery is registered as `jquery-core`._
