# Doka

## Setup

Go to your projects root directory, create a `.doka.env` file and clone the repository

### 1 - Add doka to your `.gitignore`

`/doka`

### 2 - Clone the repository

`git clone https://github.com/RozbehSharahi/doka`

### 3 - Create an empty .doka.env

Create a file `.doka.env` on your project directory, where doka is placed.

Checkout `doka/.doka.env` to see what options you can override.

Note: You can also create a `.doka.local.env` which you add to gitignore in order to have local settings. This is useful
to configure your XDEBUG client host for instance.

## Now you can

Run any `docker-compose` commands like this: `doka/compose up -d` or run `doka/enter-app` to enter the cli as `www-data`
user.

## Configuration

This README will not cover all possible configurations. In order to see what can be configured, or what can be improved
you can check out .doka.env and documentations of the underlying docker images.


> Please consider that for some settings running `doka/build` is needed.

However, here are some possible configurations.

### App configuration (example: PHP and XDEBUG configuration)

```
DOKA_APP_PHP_VERSION=8
DOKA_APP_HOST_PORT=8080
DOKA_APP_XDEBUG_MODE=off
DOKA_APP_XDEBUG_CLIENT_HOST=0.0.0.0
DOKA_APP_XDEBUG_CLIENT_PORT=9003
```

## Good to know

Set on your `.doka.env` `APACHE_DOCUMENT_ROOT=/your/path/` and rebuild `doka/build` in order to configure your document
root.

See on `doka/.doka.env` what variables you might set. Your project level `.doka.env` will override these env variables
as soon as they are declared.
