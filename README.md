# The source code of <https://www.appveyor.com/>

[![Build status](https://ci.appveyor.com/api/projects/status/a8s3e1pd8070x2y9/branch/master?svg=true)](https://ci.appveyor.com/project/AppVeyor-Website/website)
[![dependencies Status](https://david-dm.org/appveyor/website/status.svg)](https://david-dm.org/appveyor/website)


## Getting started

Install:

* [Node.js](https://nodejs.org/download/) >= 18
* Ruby matching version found in `.ruby-version`
* Bundler: run `gem install bundler`

Install project dependencies:

```sh
npm install
bundle install
```

Build the production static site:

```sh
npm run build
```

The generated site is written to the `_site/` directory.

The build script runs Jekyll and then performs the asset pipeline directly from
`scripts/build.js`: CSS and JavaScript bundling/minification, asset
fingerprinting, reference rewriting, and HTML minification.

To preview the generated site locally, serve `_site/` with any static file
server. For example:

```sh
npx http-server _site -p 4000
```

Then open <http://localhost:4000/>.

`npm test` currently runs the same production build:

```sh
npm test
```

## Staging

The `staging` branch is published to <https://appveyor-staging.azurewebsites.net>.

### TODO:

* Fix HTML errors due to duplicate IDs in /updates/
