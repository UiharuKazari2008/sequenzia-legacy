![Logo](https://github.com/UiharuKazari2008/php-sequenzia/raw/master/public/images/logo.png "Logo")
# Sequenzia LTS (MyImouto LTS - ACR Rev.)

MyImouto is a clone of [Moebooru](https://github.com/UiharuKazari2008/myimouto) for PHP and MySQL. In order for this clone to be as exact as possible, MyImouto uses a custom framework that is based on Ruby on Rails, thus the code from Moebooru was transcribed to PHP with some small modifications to fit the target language and framework.

MyImouto development stopped around 2014. By then, the port was mostly complete, with some bugs here and there. For more information about its features, changes and additions compared to Moebooru, please refer to the [About MyImouto](https://github.com/myimouto/myimouto/wiki/About-MyImouto) wiki. 

This Project has now been taken in by ACR to support the LTS project Sequenzia Project. Its completely open for remixing and branching. Some things are moddifed to fit our setup so 

Very big thanks to Parziphal for his efforts in mantaing this project before we picked it up, his efforts are one of the reason this still works today!


## Requirements

  * PHP 5.4 or higher.
  * MySQL v5.5 or higher.
  * PHP libraries:
    * GD2
    * PDO
    * cURL
    * Imagick (recommended)
    * Memcached (recommended)
  * Composer (Dependency Management for PHP).
  * If running under Apache, the Rewrite mod must be enabled. Also, to serve gzipped CSS and JS files, the Headers mod is needed.


## Installation

For an explained, step-by-step guide, please check the following guides: 

* [How to Install (Centralized)](https://github.com/UiharuKazari2008/php-sequenzia/wiki/Installation) - All-In-One Setup
* [Docker Compose](https://github.com/UiharuKazari2008/sequenzia-legacy-compose) Installer to efforetly install and run Sequenzia LTS

Otherwise, here's the quick guide for advanced users:

  * Install system dependencies: `composer install`.
  * Create a database for the booru.
  * Create `config/config.php` and `config/database.yml` by copying their respective _.example_ files.
  * Set your database configuration in `config/database.yml`.
  * Configure the booru by editing `config/config.php`. For a minimum configuration, both `server_host` and `url_base` options must be correctly set.
  * Run the installer: `php install.php`. Enter a name and password for the admin account when asked, then wait for the installation to finish.
  * Finally, point the document root of your web server to the `public` folder. That's where the index.php file is.


## Updating

Every time you update the files, don't forget to run `composer update` to update dependencies, specially for the framework, and also run `php config/boot.php db:migrate` to run database migrations (if any).
