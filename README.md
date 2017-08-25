# nuxt-asyncdatas-example

> For reproduction of error, need:
- npm run build
- npm start

On user info page `asyncData.city` - undefined, and an error occurs `Cannot read property 'name' of undefined`

AsyncData for component not applicable, because in production build no `name` components, if you don't set them manually

#### Solution
To resolve this problem, necessary changes from [commit](https://github.com/nuxt/nuxt.js/pull/1478/commits/16608fad25610961e5a679389c688f7627d9df95)

## Build Setup

``` bash
# install dependencies
$ npm install # Or yarn install*[see note below]

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm start

# generate static project
$ npm run generate
```

*Note: Due to a bug in yarn's engine version detection code if you are
using a prerelease version of Node (i.e. v7.6.0-rc.1) you will need to either:
  1. Use `npm install`
  2. Run `yarn` with a standard release of Node and then switch back

For detailed explanation on how things work, checkout the [Nuxt.js docs](https://github.com/nuxt/nuxt.js).
