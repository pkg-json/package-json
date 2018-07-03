# package.json

`package.json` is a module metadata format commonly used to describe packages in the JavaScript ecosystem. It is consumed by tools such as package managers, bundlers, compilers, app frameworks, testing tools, and more. This document describes the fields that can be included in a `package.json` file, including what they are for, how they should work, what tools they are useful for, and tracks conforming implementations.

* [Essentials](#essentials)
  - [`name`](#name)
  - [`version`](#version)

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
