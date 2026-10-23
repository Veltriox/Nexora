# Nexora docs site

Documentation for **Nexora** — A flexible technology brand that could expand beyond hosting into developer tools and AI infrastructure. Built with [VitePress](https://vitepress.dev).

## Local

```bash
cd website
bun install
bun run dev
```

## Build

```bash
bun run build
```

`predev` / `prebuild` run `scripts/sync-changelog.mjs`, which copies the repo-root
`CHANGELOG.md` into `website/changelog.md` (gitignored — do not edit by hand).
The homepage `<ChangelogPreview />` also loads that same root file via a VitePress
data loader.

Output: `.vitepress/dist`.

