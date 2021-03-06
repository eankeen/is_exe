# is_exe

![github ci](https://github.com/eankeen/is_exe/workflows/Test%20CI/badge.svg?branch=master) ![github badge](https://img.shields.io/github/license/eankeen/is_exe) ![gitHub issues](https://img.shields.io/github/issues/eankeen/is_exe)

A port of the [https://github.com/isaacs/isexe](https://github.com/isaacs/isexe) package for Deno

NOTE: currently not working for windows

## Usage

```sh
deno run --allow-read --allow-env main.ts
```

```js
// main.ts
import { isExecutable } from 'https://raw.githubusercontent.com/eankeen/is_exe/master/mod.ts'

try {
  const isExe = await isExecutable('./file')
  isExe && console.log('file is executable')
} catch {
  console.log('error reading file')
}
```

### Versions

You can pin per version. the following are supported version

```sh
# deno 1.0.3 and std v0.53.0
https://raw.githubusercontent.com/eankeen/is_exe/v1.0.3/mod.ts
```

## API

### `isExecutable(filePath, [options])`

### Options

- `ignoreErrors` treat all errors as "no, this is not executable", but don't raise them.
- `uid` number to use as the user id
- `gid` number to use as the group id
- `pathExt` list of path extensions to use instead of PATHEXT environment variable on Windows *(not implemented)*
