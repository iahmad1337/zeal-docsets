- Howto: https://kapeli.com/docsets#dashDocset
- The zeal docset directory may be found via Zeal -> Preferences -> Docset
  storage

# My actions
For a baseline, you can build the docset with dashing:
```
brew install dashing
dashing create
dashing build mydocs
```
and then move the reuslt to docset directory.

On the other hand, you can try to build the index yourself. This is necessary if
you plan to use the search.
```
sqlite3
    .open nasm/nasm.docset/Contents/Resources/docSet.dsidx
    CREATE TABLE searchIndex(id INTEGER PRIMARY KEY, name TEXT, type TEXT, path TEXT);
    CREATE UNIQUE INDEX anchor ON searchIndex (name, type, path);
```
At this stage you should build the index by a custom script - but i'm not ready
for this yet.
