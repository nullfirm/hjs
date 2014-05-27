hjs
=====
[Hogan.js](http://twitter.github.com/hogan.js/) NPM package for [express](http://expressjs.com/) 3.x

## Installation

    $ npm install -g express@3.0  hjs

## Quick Start

 Install Express :

    $ npm install -g express@3.0

 Create express app :

    $ express -H /tmp/testapp
    $ cd /tmp/testapp/
    & npm install

## Manual Start

 Install Express :

    $ npm install -g express@3.0

 Create express app :

    $ express /tmp/testapp
    $ cd /tmp/testapp/

 Edit package.json :

    $ vi package.json

```json
"dependencies": {
    "express": "3.0.0",
    "hjs": "*"
}
```

    $ npm install

 Edit app.js :

```js
app.set('view engine', 'hjs');
```

 Make views/index.hjs :

```html
<html>
<head>
    <title>{{ title }}</title>
</head>
<body>
    <p>{{ title }}</p>
</body>
</html>
```

 Start server :

    $ node app

## Partials
index.hjs
```html
<html>
<head>
    <title>{{ title }}</title>
</head>
<body>
    <p>{{ title }}</p>
    {{> footer }}
</body>
</html>
```
footer.hjs
```html
<div>My awesome footer</div>
```
To use a partial once:
```js
res.render('index', {
    title: 'My Test App',
    partials: {footer: 'footer'}
});
```
To include a partial on every page:
```js
app.set('partials', {footer: 'footer'});
```

## More Information
 [express](http://expressjs.com/) is Fast, unopinionated, minimalist web framework for [node](http://nodejs.org).

 [Hogan.js](http://twitter.github.com/hogan.js/) is a compiler for the
[Mustache](http://mustache.github.com/) templating language. For information
on Mustache, see the [manpage](http://mustache.github.com/mustache.5.html) and
the [spec](https://github.com/mustache/spec).
