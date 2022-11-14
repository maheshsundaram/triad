# 🎼 Triad

- the root - THREE.js
- the third - Typescript
- the fifth - ESModules

Simple template for using THREE.js with Typescript and ESModules and no build/bundle tooling (besides tsc).

## ➡️ Setup

`npm install` installs Typescript and THREE.js and copies the THREE.js build to `modules/`.

The `index.html` uses an import-map to allow a bare import of THREE.js in the `src/main.ts` file, i.e.

```html
    <!-- index.html -->
    <script type="importmap">
      {
        "imports": {
          "three": "./modules/three.module.js"
        }
      }
    </script>
```

```ts
// src/main.ts
import * as three from "three";
```

Then when running the TS build (with `npx tsc` or e.g. `npx tsc --watch`) the TS modules output is in `modules/`

You will need a simple server to [run locally](https://threejs.org/docs/index.html#manual/en/introduction/How-to-run-things-locally). The [Deno std/http file server](https://deno.land/manual@v1.28.0/examples/file_server#using-the-stdhttp-file-server) makes this very easy, i.e. after installing it just run `file_server .` in the directory then open the URL in the browser.

## 💾 Deployment

Use your favorite tooling to copy the assets (`index.html`, `style.css`, and `modules/` files) to the host.
