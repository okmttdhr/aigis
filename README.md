# aigis

Aigis is a Node.js package that parses comments in your CSS and auto-generate a style guide.

## Installation

```shell
$ npm install --save-dev node-aigis
```

You can verify node-aigis was installed correctly by running:

```shell
$ ./node_modules/.bin/aigis -v
$ 1.x.x
```

## Config file & HTML Templates

aigis require "Config file" & "HTML Templates".

```
aigis init
```

This will create an `aigis_config.yml` file (more on this below)

```shell
$ ./node_modules/.bin/aigis init
Created the following files and directories:
  aigis_config.yml
  aigis_assets
  template_ejs
```

## Choose Template Engine

You can choose The following Template engines for generating style guide.

* EJS（`ejs`）
* Jade（`jade`）
* Handlebars（`hbs`）

When you run `aigis init`, add `--engine` option.

e.g) choose jade

```shell
$ ./node_modules/.bin/aigis init --engine jade
```

## Config file

After `aigis init`, edit `aigis_config.yml`. You have to write relative path to your source files on `source`.

```yaml
source:
  - ./lib/css
  - ./style.css
```

> Initially, the configuration file contains `source: aigis_assets`, You can run `aigis run` then generate sample style guide.

## Adding comments

Write following code on CSS comment block (<code>&#047;&#042; ~ &#042;&#047;</code>)


It's easy to add Comments. For example.

````yaml
---
name: base button
category: module/button
---

## This is base button

* Base button style.
* Use `a` or `button` tag.

```html
<a class="btn">Button</a>
```
````

## Running aigis

You're finally ready to generate a style guide!

```shell
$ ./node_modules/.bin/aigis run -c ./aigis_config.yml
```

Then you get following output.

<a href="http://pxgrid.github.io/aigis/sample/category/mod/btn/" target="_blank">sample</a>


## More

See the [documents](https://pxgrid.github.io/aigis/docs/en/)
