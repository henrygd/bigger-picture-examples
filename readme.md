The `sveltekit-basic` and `sveltekit-basic-typescript` examples were removed because they were using the older pre-1.0 version of SvelteKit. For now please check the [sveltekit-dynamic-import](sveltekit-dynamic-import) example.

The dynamic import example is not only for SvelteKit. You should be able to use the [load-bp module](sveltekit-dynamic-import/src/lib/load-bp.ts) in any project that supports dynamic imports.

Basic usage outline (see [masonry-gallery.svelte](sveltekit-dynamic-import/src/lib/masonry-gallery.svelte)):

```js
let bp

(async () => {
  bp = await loadBp()
})()

function onClick() {
  bp.open({...})
}
```
