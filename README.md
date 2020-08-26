# Purgecss with Wordpress


Based on the [gist](https://gist.github.com/frnwtr/5647673bb15ca8893642469d3b400cba) made by @frnwtr, `purgecss-with-wordpress` is a set of templates for
Wordpress CMS.

## Getting Started

#### Installation

You need to install [purgecss](https://github.com/FullHuman/purgecss) first.

Install `wenprise-purgecss-whitelist`:
```sh
npm i --save-dev wenprise-purgecss-whitelist
```

## Usage

```js

import Purgecss from 'purgecss'
import purgecssWhiteList from 'wenprise-purgecss-whitelist'

const purgeCss = new Purgecss({
  content: ['**/*.html'],
  css: ['**/*.css'],
  whitelist: purgecssWhiteList.whitelist.concat([
      'ln-letters',
      'letterCountShow',
  ]),
  whitelistPatterns: purgecssWhiteList.whitelistPatterns.concat([
      /ln-*/,
      /listNav*/,
  ])
})
const result = purgecss.purge()
```

If you have additional classes you want to include in either of the `whitelist` or `whitelistPatterns`, you can include them using the spread operator:

```js
whitelist: [
  ...purgecssWhiteList.whitelist,
  'red',
  'blue',
],
whitelistPatterns: [
  ...purgecssWhiteList.whitelistPatterns,
  /^red/,
  /blue$/,
]
```

## Versioning

Purgecss-with-wordpress use [SemVer](http://semver.org/) for versioning.

## Acknowledgment

Purgecss-with-wordpress is based on the [gist](https://gist.github.com/frnwtr/5647673bb15ca8893642469d3b400cba) made by @frnwtr

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file
for details.
