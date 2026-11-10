# fs

File system operations: path inspection and manipulation, directories,
recursive `walk`, `glob` patterns (`src/**/*_test.qk`), temporary files
and directories, `copy` / `copy_tree`, and whole-file `read_text` /
`write_text`.

```quirk
use fs

for path in fs.glob("src/**/*.qk") {
    print(path)
}
work := fs.temp_dir(prefix="build-")
fs.copy_tree("assets", fs.join(work, "assets"))
fs.write_text(fs.join(work, "VERSION"), "1.2.0\n")
```

v1.2.0 needs the Quirk compiler 7.19.0+ (its runtime has the new
`Fs_*` functions).

This package is also bundled with the Quirk compiler at
`<QUIRK_HOME>/packages/fs/`, so `use fs` works out of the box on a
fresh install. This repo is the canonical home — when you want a version
newer than the one your compiler shipped with, install it explicitly:

```bash
quirk pkg install fs             # latest tag from this repo
quirk pkg install fs@1.2.0       # pinned
```

The compiler-shipped registry maps the bare name `fs` to this repo
(since v1.4.0), so no `quirk pkg registry add` is needed.

## Origin

Split from `quirk-compiler/packages/fs/` in compiler v1.5.0 as part of
the stdlib-in-independent-repos rollout. Source history before that lives
in [AlexVachon/quirk](https://github.com/AlexVachon/quirk).

## License

MIT (see [`LICENSE`](LICENSE)).
