# fs

File system operations beyond opening/reading a single file. Path inspection: `fs.exists(p)` — anything (file/dir/symlink) at p `fs.is_file(p)` / `fs.is_dir(p)` `fs.size(p)` — bytes (-1 if not sta

This package is also bundled with the Quirk compiler at
`<QUIRK_HOME>/packages/fs/`, so `use fs` works out of the box on a
fresh install. This repo is the canonical home — when you want a version
newer than the one your compiler shipped with, install it explicitly:

```bash
quirk pkg install fs             # latest tag from this repo
quirk pkg install fs@1.0.0       # pinned
```

The compiler-shipped registry maps the bare name `fs` to this repo
(since v1.4.0), so no `quirk pkg registry add` is needed.

## Origin

Split from `quirk-compiler/packages/fs/` in compiler v1.5.0 as part of
the stdlib-in-independent-repos rollout. Source history before that lives
in [AlexVachon/quirk](https://github.com/AlexVachon/quirk).

## License

MIT (see [`LICENSE`](LICENSE)).
