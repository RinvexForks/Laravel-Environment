# Laravel Enviroment


Based on the article [How to keep a secret](http://blog.fortrabbit.com/how-to-keep-a-secret).
## Installation

Require this package, with [Composer](https://getcomposer.org/), in the root directory of your project.

``` bash
$ composer require faustbrian/laravel-environment
```

Add the service provider to `config/app.php` in the `providers` array.

``` php
BrianFaust\Environment\EnvironmentServiceProvider::class
```

## Configuration

Laravel Env supports optional configuration.

To get started, you'll need to publish all vendor assets:

```bash
$ php artisan vendor:publish --provider="BrianFaust\Environment\EnvironmentServiceProvider"
```

This will create a `config/env.php` file in your app that you can modify to set your configuration. Also, make sure you check for changes to the original config file in this package between releases.

## Usage

To get started, you'll need to generate a new encryption key for the `env.php` config file.

```bash
$ php artisan env:key
// 5W183ikLhZqoJ1Ye
```

Copy this key and place it within the `env.php` config file.

##### Register `sec_env` method

Add the following code at the very top of `bootstrap/app.php`, above any other code:

``` php
require_once(__DIR__.'/../vendor/faustbrian/laravel-environment/src/functions.php');
```

## Security

If you discover a security vulnerability within this package, please send an e-mail to Brian Faust at hello@brianfaust.de. All security vulnerabilities will be promptly addressed.

## License

[MIT](LICENSE) © [Brian Faust](https://brianfaust.de)
