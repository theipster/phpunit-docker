# PHPUnit via Docker

Run [PHPUnit](https://phpunit.de/) without needing a PHP runtime installed on your docker host.

## Installation

For example, to build PHPUnit 8.0.5:

```
$ docker build -t phpunit-docker:8.0.5 8.0.5/
```

## Usage

For example, to run PHPUnit 8.0.5 on your application `/path/to/app` with config file `phpunit.xml`:

```
$ docker run -itv /path/to/app:/app phpunit-docker:8.0.5 -c phpunit.xml
```

This can be simplified by setting up an alias in your `~/.bashrc`:

```
alias phpunit='docker run -itv "$PWD":/app phpunit-docker:8.0.5'
```

Then, running the image simply becomes:

```
$ cd /path/to/app
$ phpunit -c phpunit.xml
```

## Roadmap

- Autogenerate different PHPUnit versions using something like m4 (see [here](http://bobbynorton.com/posts/includes-in-dockerfiles-with-m4-and-make/)).
