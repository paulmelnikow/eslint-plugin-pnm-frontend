eslint-plugin-pnm-frontend
==========================

Paul's JavaScript and SASS style for front-end projects.

Originally developed at [Body Labs][].

See also [eslint-plugin-pnm][], for full-stack and back-end projects.

This is provided as an eslint module, because it lets us bundle together
multiple configs, and also allows us to provide code for our own rules,
should we add any in the future.

[Body Labs]: https://github.com/bodylabs/eslint-plugin-bodylabs
[eslint-plugin-pnm]: https://github.com/paulmelnikow/eslint-plugin-pnm


Usage
-----

```sh
npm install --save-dev eslint eslint-plugin-pnm eslint-plugin-pnm-frontend eslint-plugin-react babel-eslint
```

In your project, create `.eslintrc.yml`:

```yml
extends:
  "plugin:pnm-frontend/react"
```

And then set up scripts:

```json
"scripts": {
  "lint": "eslint '**/*.js'",
  "unittest": "mocha src",
  "test": "npm run lint && npm run unittest"
}
```


Versioning
----------

This repository adopts the versioning strategy of JSCS:

We recommend installing JSCS and eslint via NPM using `^`, or `~` if you want more stable releases.

Semver (http://semver.org/) dictates that breaking changes be major version bumps. In the context of a linting tool, a bug fix that causes more errors to be reported can be interpreted as a breaking change. However, that would require major version bumps to occur more often than can be desirable. Therefore, as a compromise, we will only release bug fixes that cause more errors to be reported in minor versions.

Below you fill find our versioning strategy, and what you can expect to come out of a new JSCS release.

 * Patch release:
   * A bug fix in a rule that causes JSCS to report less errors.
   * Docs, refactoring and other "invisible" changes for user;
 * Minor release:
   * Any preset changes.
   * A bug fix in a rule that causes JSCS to report more errors.
   * New rules or new options for existing rules that don't change existing behavior.
   * Modifying rules so they report less errors, and don't cause build failures.
 * Major release:
   * Purposefully modifying existing rules so that they report more errors or change the meaning of a rule.
   * Any architectural changes that could cause builds to fail.
