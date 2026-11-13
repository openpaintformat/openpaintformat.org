# openpaintformat.org

The website for the [Open Paint Format](https://github.com/openpaintformat/standard), served by
GitHub Pages.

Its main job is to serve each JSON Schema at the URL its `$id` names, for example
`https://openpaintformat.org/schemas/recipe/v1/recipe.schema.json`.

**The schemas are not stored here.** Each build checks out `openpaintformat/standard` at
`STANDARD_REF` (see [`.github/workflows/pages.yml`](.github/workflows/pages.yml)) and publishes its
`schemas/` directory unchanged. The build fails if any schema's `$id` does not match the path it
is served at. `/build.json` records the standard commit that was published.

- Before the v1 freeze, `STANDARD_REF` is `main`. To pick up a change to the schemas, run the
  workflow again (Actions → Publish openpaintformat.org → Run workflow).
- At the freeze, set `STANDARD_REF` to the release tag, so the served v1 schemas stop moving.

The page itself is `site/index.html`. Everything in `site/` is published at the site root.
