# Composer template for Drupal projects

This project template should provide a kickstart for managing your site
dependencies with [Composer](https://getcomposer.org/) and using [Vagga](http://vagga.readthedocs.org)
to manage your development environments.

If you want to know how to use Composer as to manage tour site, have a
look at [drupal-composer/drupal-project](https://github.com/drupal-composer/drupal-project) 
on github. 

## Usage

Simply run the project with `vagga run`. It will setup the containers,
install the site (only the first time) and serve Drupal.

Drush and Drupal Console are available as Vagga commands.

### Managing depedencies
Its is unclear how to Vagga intend Composer to be used to manage
dependencies (see https://github.com/tailhook/vagga/issues/218).

Currently, `composer install` is run when building containers. Once
containers are build, Composer is not available anymore. There is no way
to run `composer require` or `composer update`. As a work around, manage
your dependencies in `composer.json`, delete the `composer.lock` and run
`vagga _build drupal --force`  when you want to run `composer install`.


## TODO
- MariaDB (with persistent data)
- nginx + php-fpm
- Vagga `test` command (+ rewrite TravisCI script)
- Vagga `doc` command
