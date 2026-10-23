# Life Coach Arla

A Jekyll website starter for Life Coach Arla.

## Local development

```sh
bundle install
bundle exec jekyll serve --livereload
```

Then open <http://localhost:4000>.

## Cloudflare Workers deployment

This is a **Ruby/Jekyll** static website, not a Node.js project. The
`wrangler.jsonc` file declares `_site` as the static-asset directory.

In the Cloudflare Workers project settings under Builds, configure:

- **Build command:** `bundle exec jekyll build`
- **Deploy command:** `npx wrangler deploy`
- **Output directory:** `_site` (where requested)
- **Root directory:** repository root

**Do not use** `npx bundle exec jekyll build`: Bundler is a Ruby executable
and cannot be launched via `npx`. The previous deployment failed with
`npm error could not determine executable to run` for that reason.

Cloudflare must build the Jekyll site *before* Wrangler deploys its
generated files from `_site`. From a local checkout, the equivalent is:

```sh
bundle install
bundle exec jekyll build
npx wrangler deploy
```

The Cloudflare build environment needs Ruby and Bundler, which were already
successfully installed in the failing deployment log.
