# Hyper-Svelte-Component

A [Svelte](https://svelte.dev) <[Component](https://github.com/sveltejs/component-template) /> for managing [Hyperdrives](https://github.com/hypercore-protocol/hyperdrive) using the [dat-sdk](https://github.com/datproject/sdk).

## Why

When using the dat SDK you've got to close it, and keeping track of the close is a pain. So I bundled the creation of the hyperdrive and the close function into a svelte component. Whenever the component is `destroyed` or the `window.unloads` the `await close()` function for the SDK's Hyperdrive will be closed. So you don't have to worry about it.

## Usage 

All you do is pass in an instance of the `SDK` and what you want `Hyperdrive` to be called (if you wan to rename it, or have multiple SDK instances, to simulate many peers on one device).

```js
import HyperComponent from "hyper-svelte-component");

<HyperComponent {SDK} bind:Hyperdrive={makeDrives} />
<HyperComponent {SDK} bind:Hyperdrive={makeDriveCopies} />

const original = makeDrives("original-drive-name")
const copy = makeDriveCopies(original.key)

```


---

