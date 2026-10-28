# Ricettario CSB

Ricettario degli studenti del Collegio Superiore di Bologna.

## Development

Use Hugo **0.165.0 Extended** (the version pinned in CI) with Blowfish **v3.6.0**.

```sh
git submodule update --init --recursive
hugo server
```

The refreshed Nix lock (`nix develop`) provides Hugo 0.166.0 Extended, which
also builds successfully but emits a warning because Blowfish declares support
through 0.165.0.

Build for production with `hugo --minify`. When updating Blowfish, check its
supported Hugo versions and update both Firebase workflows together.

## Credits
- Using [Blowfish](https://blowfish.page)

## Recipe tables

Recipes include a Cooking for Engineers–style summary. To add one
to a new recipe, place `recipe-grid.json` beside its `index.md` and insert
`{{< recipe-grid >}}` in the Markdown. The risotto's JSON is the example:
`preparationColumns` counts the process columns (there is no visible header row); each row
has an `ingredient`, `quantity`, and
`steps` with a `title` and optional `note`, `rowspan`, or `colspan`. Spanning
cells occupy positions in later rows, so omit those covered cells.
For one ingredient feeding adjacent preparation paths, set `ingredientRowspan`
on its first row and omit `ingredient` and `quantity` on the covered rows.
The apple in the apple risotto demonstrates this; its quantity is the total
shared by both preparations.

Keep the diagram consistent with the written recipe when editing either.
The table scrolls on narrow screens, supports dark mode, and has print styles.
