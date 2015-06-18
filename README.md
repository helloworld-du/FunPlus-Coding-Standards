[![Build Status](https://travis-ci.org/funplus/FunPlus-Coding-Standards.svg?branch=master)](https://travis-ci.org/funplus/FunPlus-Coding-Standards)

# FunPlus Coding Standards for PHP_CodeSniffer

This project is a collection of [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) rules (sniffs) to validate code developed for FunPlus.

## Installation

### Composer

Standards can be installed with [Composer](https://getcomposer.org/) dependency manager:

    composer create-project fp-coding-standards/fpcs:dev-master --no-dev

Running this command will:

1. Install FunPlus standards into `fpcs` directory.  
2. Install PHP_CodeSniffer.
3. Register FunPlus standards in PHP_CodeSniffer configuration.
4. Make `phpcs` command available from `fpcs/vendor/bin`.

For convenience of using `phpcs` as global command you might want to add path to `fpcs/vendor/bin` directory to a `PATH` environment of your operating system.

### Standalone

1. Install PHP_CodeSniffer by following its [installation instructions](https://github.com/squizlabs/PHP_CodeSniffer#installation) (via Composer, PEAR, or Git checkout).

  Do ensure, if for example you're using [VVV](https://github.com/Varying-Vagrant-Vagrants/VVV), that PHP_CodeSniffer's version matches our requirements (you can check the required version in [composer.json](composer.json#L18)).

2. Clone FunPlus standards repository:

        git clone -b master https://github.com/funplus/FunPlus-Coding-Standards.git fpcs

3. Add its path to PHP_CodeSniffer configuration: 

        phpcs --config-set installed_paths /path/to/fpcs


To summarize:

```bash
cd ~/projects
git clone https://github.com/squizlabs/PHP_CodeSniffer.git phpcs
git clone -b master https://github.com/funplus/FunPlus-Coding-Standards.git fpcs
cd phpcs
./scripts/phpcs --config-set installed_paths ../fpcs
```

And then add the `~/projects/phpcs/scripts` directory to your `PATH` environment variable via your `.bashrc`.

You should then see `FunPlus` et al listed when you run `phpcs -i`.

## How to use

### Command line

Run the `phpcs` command line tool on a given file or directory, for example:

    phpcs --standard=FunPlus somephpfile.php

## Standards subsets

The project encompasses a super–set of the sniffs that the FunPlus community may need. If you use the `FunPlus` standard you will get all the checks. 

You can use the following as standard names when invoking `phpcs` to select sniffs, fitting your needs:

 - `FunPlus` — all of the sniffs in the project.


### Using custom ruleset

If you need to further customize selection of sniffs for your project — you can create custom `ruleset.xml` standard. See [fully annotated example](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Annotated-ruleset.xml) in PHP_CodeSniffer documentation.

## License

See [LICENSE](LICENSE) (MIT).
