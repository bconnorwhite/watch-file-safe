<div align="center">
  <a href="https://github.com/bconnorwhite/write-file-safe">
    <img alt="write-file-safe" src="assets/header.svg" />
  </a>
  <a href="https://npmjs.com/package/watch-file-safe">
    <img alt="NPM" src="https://img.shields.io/npm/v/watch-file-safe.svg">
  </a>
  <a href="https://github.com/bconnorwhite/watch-file-safe">
    <img alt="TypeScript" src="https://img.shields.io/github/languages/top/bconnorwhite/watch-file-safe.svg">
  </a>
  <a href='https://coveralls.io/github/bconnorwhite/watch-file-safe?branch=master'>
    <img alt="Coverage Status" src="https://img.shields.io/coveralls/github/bconnorwhite/watch-file-safe.svg?branch=master">
  </a>
  <a href="https://github.com/bconnorwhite/watch-file-safe">
    <img alt="GitHub Stars" src="https://img.shields.io/github/stars/bconnorwhite/watch-file-safe?label=Stars%20Appreciated%21&style=social">
  </a>
  <a href="https://twitter.com/bconnorwhite">
    <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/bconnorwhite.svg?label=%40bconnorwhite&style=social">
  </a>
</div>

<br />

> Watch a file for changes.

Provides a simplified wrapper around [chokidar](https://www.npmjs.com/package/chokidar) for watching a file.

## Installation

```sh
yarn add watch-file-safe
```

```sh
npm install watch-file-safe
```

## API

### Usage
```ts
import watchFile from "watch-file-safe";

const watcher = watchFile("/path/to/file.txt");

watcher.onReady(() => {
  console.log(`Ready`);
}).onAdd((path: string) => {
  console.log(`Added ${path}`);
}).onChange((path: string) => {
  console.log(`Changed ${path}`);
}).onRemove((path: string) => {
  console.log(`Removed ${path}`);
});

// To stop watching:
watcher.stop();
```

### Types
```ts
import watchFile, { Watcher, EventCallback } from "watch-file-safe";

function watchFile(path: string): Watcher;

type EventCallback = (path: string) => void;

type Watcher = {
  onAdd: (cb: EventCallback) => Watcher;
  onRemove: (cb: EventCallback) => Watcher;
  onChange: (cb: EventCallback) => Watcher;
  onReady: (cb: () => void) => Watcher;
  stop: () => Promise<boolean>;
}
```

<br />

<h2>Dependencies<img align="right" alt="dependencies" src="https://img.shields.io/david/bconnorwhite/watch-file-safe.svg"></h2>

- [chokidar](https://www.npmjs.com/package/chokidar): A neat wrapper around node.js fs.watch / fs.watchFile / fsevents.

<br />

<h2>Dev Dependencies<img align="right" alt="David" src="https://img.shields.io/david/dev/bconnorwhite/watch-file-safe.svg"></h2>

- [@bconnorwhite/bob](https://www.npmjs.com/package/@bconnorwhite/bob): Bob is a toolkit for TypeScript projects

<br />

<h2>License <img align="right" alt="license" src="https://img.shields.io/npm/l/watch-file-safe.svg"></h2>

[MIT](https://opensource.org/licenses/MIT)

<br />

## Related Packages

- [fs-safe](https://www.npmjs.com/package/fs-safe): A simple fs wrapper that doesn't throw
- [watch-dir-safe](https://www.npmjs.com/package/watch-dir-safe): Watch a directory for changes
- [read-file-safe](https://www.npmjs.com/package/read-file-safe): Read files without try catch
- [write-file-safe](https://www.npmjs.com/package/write-file-safe): Write files, and parent directories if necessary
- [remove-file-safe](https://www.npmjs.com/package/remove-file-safe): Remove a file without try catch
