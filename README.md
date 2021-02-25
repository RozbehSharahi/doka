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

Note: You can also create a `.doka.local.env` which you add to gitignore in order to have local settings. This is useful to configure your XDEBUG client host for instance.

## Now you can

Run any `docker-compose` commands like this: `doka/compose up -d` or run `doka/enter-app` to enter the cli as `www-data` user.

## Good to know

Set on your `.doka.env` `APACHE_DOCUMENT_ROOT=/your/path/` and rebuild `doka/build` in order to configure your document root.

See on `doka/.doka.env` what variables you might set. Your project level `.doka.env` will override these env variables as soon as they are declared.
