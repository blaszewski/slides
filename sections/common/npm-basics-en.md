# npm

## npm registry

The npm registry is an online registry consisting primarily of open source JavaScript packages

With [over 1 million packages](http://www.modulecounts.com/) it is by far the largest software registry in existence

examples: [most depended upon packages](https://www.npmjs.com/browse/depended)

## Package managers

two major package managers for the npm registry:

- _npm_: Node package manager, comes with node.js
- _yarn_: may be installed separately

## Package configuration

Both public packages and our private projects will be managed via a configuration file named _package.json_.

## Package configuration

In order to add dependencies to our project we can start out with an empty _package.json_ configuration:

```json
{}
```

We could also create such a file with some content via `npm init` (or `npm init -y` for default options)

## Adding dependencies

We can add some dependencies via:

```bash
npm install lodash bootstrap
```

## Adding dependencies

If we are developing a reusable library that we want to publish to the npm package registry:

Install dependencies that are only needed for development as _dev-dependencies_:

```bash
npm install eslint --save-dev
```

## Adding dependencies

Effects of the previous `npm install` commands:

- `package.json` - lists minimum versions of the packages we just installed
- `node_modules` - folder that contains all installed packages
- `package-lock.json` - lists exact versions of all packages in `node_modules`

## Dependencies in package.json

The file `package.json` now lists dependencies together with a version specifier

The version specifier uses _semantic versioning_: `major.minor.patch`

possible configurations:

- `"bootstrap": "4.3.1"` - exactly this version
- `"bootstrap": "~4.3.1"` - patch version updates allowed - for example to `4.3.2`
- `"bootstrap": "^4.3.1"` - minor version updates allowed - for example to `4.4.0`

## Dependencies in package-lock.json

The file `package-lock.json` lists _exact_ versions for all dependencies and their recursive dependencies

## node_modules folder

contains the actual packages

this should not be put under version control - instead, this folder can be recreated from `package.json` by running `npm install` (without any arguments)

## npm scripts

Npm can be used to execute scripts / commands that are needed for development, for example:

- `npm run test` - would run unit tests
- `npm run build` - would create a build
- `npm run start`
- `npm run deploy`

Some npm scripts have shorthands, notably `npm test` and `npm start`

## npm scripts

Npm scripts are configured in `package.json`:

```json
{
  "scripts": { "start": "node run-server.js" }
}
```

## Global installs and npx

Node packages may be installed globally on a computer or may be executed directly from the npm registry

direct execution (without installation):

```bash
npx cowsay hello
```

global installation of `cowsay`:

```bash
npm install -g cowsay

cowsay hello
```