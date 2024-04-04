- sveltekit
    bun create svelte@latest front
    cd front
    bun install

```
    plugins: [sveltekit()],
    server: {
        host: true,
      },
```
    bun --bun run dev
    bun run build

もう嫌だ。。。bunのエラーが止まらん。
```
┌   shadcn-svelte  v0.10.0 
│
└  TypeError: "paths[0]" property must be of type string, got undefined
    at join (native)
    at zs (/tmp/bunx-1000-shadcn-svelte@latest/node_modules/shadcn-svelte/dist/index.js:868:20)
    at Ws (/tmp/bunx-1000-shadcn-svelte@latest/node_modules/shadcn-svelte/dist/index.js:851:19)
    at <anonymous> (/tmp/bunx-1000-shadcn-svelte@latest/node_modules/shadcn-svelte/dist/index.js:879:45)
    at processTicksAndRejections (:12:39)
```

- tailwind
   bunx svelte-add@latest tailwindcss

- biome
    bun add --dev --exact @biomejs/biome
    bunx @biomejs/biome init
    or bun x @biomejs/biome init

# pnpm で構築する
- sveltekit
    pnpm create svelte@latest /home/node/front
    ```
    server: {
        host: true,
      },
    ```
    pnpm i
    pnpm dev

- tailwind
  pnpx svelte-add@latest tailwindcss
  pnpm i

- shadcn
    pnpx shadcn-svelte@latest init
```
  shadcn-svelte  v0.10.0 
│
◇  Would you like to use TypeScript (recommended)?
│  Yes
│
◇  Which style would you like to use?
│  Default
│
◇  Which base color would you like to use?
│  Slate
│
◇  Where is your global CSS file?
│  src/app.pcss
│
◇  Where is your Tailwind config located?
│  tailwind.config.cjs
│
◇  Configure the import alias for components:
│  $lib/components
│
◇  Configure the import alias for utils:
│  $lib/utils
│
●  Your tailwind config has been renamed to tailwind.config.js.
│
◇  Config file components.json created
│
◇  Project initialized
│
◇  Dependencies installed
│
└  Success! Project initialization completed.
```

pnpx shadcn-svelte@latest add button

# テスト準備
https://qiita.com/oekazuma/items/925ddbf48870fb999c19
 pnpm install -D @testing-library/svelte jsdom
 bun install -D @testing-library/svelte jsdom

```vite.config.js
 test: {
        include: ['src/**/*.{test,spec}.{js,ts}'],
        globals: true,
        environment: 'jsdom'
    }
```