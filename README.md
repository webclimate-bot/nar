# nar

> Bundle, package and ship self-contained node applications

> **work in progress!**

## About

**nar** (node.js aplication archive) is a helper utility for creating self-contained node applications that was easy to 
ship and deploy

It creates a gzipped archive with all your applications sources, packages dependencies and
optionally node binary

## Installation

```
$ npm install -g nar
```

## Command-line interface

```
$ nar --help


```

### create

Create a nar archive from an existent application 

### exec

Run an application

### extract

Extend sources from a nar archive

## Configuration

nar specific build configuration should be defined as meta-data
in the `package.json` manifest file of your application

```
{
  "name": "my-package",
  "version": "1.0.0",
  "nar": {
    "binary": true,
    "deployPath": "${HOME}/apps/my-cool-package",
    "dependencies": true,
    "devDependencies": false,
    "peerDependencies": true,
    "commands": {
      "pre-run": "npm install",
      "run": "node ./app"
    }
  }
}
```

### Ignore files

You can explicit omit files defining them in the `.buildignore` file

### Options

The following options can be declared in your application package.json as
properties members of the `nar` or `package` first-level property

#### dependencies
Type: `boolean`
Default: `true`

#### devDependencies
Type: `boolean`
Default: `false`

#### peerDependencies
Type: `boolean`
Default: `false`

#### binary
Type: `boolean`
Default: `false`

#### globalPackages
Type: `string|array`
Default: `undefined`

Bundle globally installed packages in the generated archive.
Useful for npm, grunt-cli, bower...

Include the node.js binary in the generated archive.
This is usually useful when you want to deploy a obsessively fully self-contained application
in a sandboxed deployment or runtime environment

**Note**: the binary is OS-specific. Be aware about using this option if you want to deploy in multiple platforms

#### deployPath
Type: `string`
Default: `undefined`

## Programmatic API

`to do`

## License

Copyright (c) 2014 Tomas Aparicio

Released under the MIT license