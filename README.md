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
