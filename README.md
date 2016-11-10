
This project makes it simple to have a [Ghost](http://ghost.org/) blog hosted on Github pages.

## Instructions

### Installation

You need to have [Buster](https://github.com/axitkhurana/buster/) installed (basically a `pip install buster`).

Fork this repository and clone it on your computer.

This command will clone and install Ghost:

```
$ npm install
```

### Use

Load your site's data and start Ghost on `http://localhost:2368/ghost`

```
$ npm start
```

To stop Ghost and save your site data:

```
$ npm run stop
```

Publish your changes to github pages with
```
$ git add -A
$ git commit -am "your commit message"
$ git push origin gh-pages
```

____

in case of 'lxml.etree.XMLSyntaxError: Char 0x0 out of allowed range, line 1, column 1031'

sqlite3 Ghost/content/data/ghost-dev.db

.mode csv
.once dataout.csv
SELECT * FROM posts;

vi dataout.csv
:s/\\u0000//g

delete from posts;
.import dataout.csv posts
