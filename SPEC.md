# package.json

`package.json` is a module metadata format commonly used to describe packages in the JavaScript ecosystem. It is consumed by tools such as package managers, bundlers, compilers, app frameworks, testing tools, and more. This document describes the fields that can be included in a `package.json` file, including what they are for, how they should work, what tools they are useful for, and tracks conforming implementations.

* [Essentials](#essentials)
  - [`name`](#name)
  - [`version`](#version)
  - [`main`](#main)

## Essentials

### `name`

**(Required)** The name of the package.

```json
{
  "name": "my-package"
}
```

#### Rules

* Must be less than or equal to 214 characters (including the `@scope/` for scoped packages).
* Must not start with a dot (`.`) or an underscore (`_`).
* Must not have an uppercase letter in the name.
* Must use only URL-safe characters.

#### Tips

* Don't use the same name as a core Node.js module
* Don't put js or node in the name.
* Keep names short and descriptive. You want people to understand what it is from the name, but it will also be used in require() calls.
* Make sure that there isn't something in the [registry](https://npmjs.com) with the same name.

### `version`

**(Required)** The current version of the package.

```json
{
  "version": "1.0.0"
}
```

The version number must be valid [semver](https://semver.org). See the [npm docs](https://docs.npmjs.com/misc/semver) for more info.

### `main`

Module ID that is the primary entry point to a package - that is when consumer requests the package i.e. with `require('my-package')` the resolution algorithm should check this field and redirect the request to the specified value. **(Default)** `index.js`

#### Rules

* Value should be a path relative to the root of a package
* Value gets resolved with node's resolution algorithm, described [here](http://nodejs.cn/doc/nodejs/modules.html#modules_all_together)

#### Tips

* Resolved value should point to a file authored in CommonJS format which still being predominant in the ecosystem acts as a baseline of what should be supported by all the tooling

