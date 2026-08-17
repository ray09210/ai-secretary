# ホーム

秘書が書いたものが、種類を問わず新しい順に並びます。**このページは自動です。**
何かを書き足す必要はありません。

## 最近さわったもの

```base
filters:
  and:
    - 'file.ext == "md"'
    - '!file.name.contains("CLAUDE")'
    - 'file.name != "Home"'
    - 'file.name != "README"'
views:
  - type: table
    name: 新しい順
    order:
      - file.name
      - file.folder
      - file.mtime
    sort:
      - property: file.mtime
        direction: DESC
    limit: 20
```

---

## 今日と、その前のTODO

```base
filters:
  and:
    - 'file.inFolder("secretary/todos")'
views:
  - type: table
    name: TODO
    order:
      - file.name
      - file.mtime
    sort:
      - property: file.name
        direction: DESC
    limit: 7
```

## 決めたこと・学んだこと

```base
filters:
  and:
    - 'file.inFolder("secretary/notes")'
views:
  - type: table
    name: 記録
    order:
      - file.name
      - file.mtime
    sort:
      - property: file.name
        direction: DESC
    limit: 10
```

## あとで考えること

```base
filters:
  and:
    - 'file.inFolder("secretary/inbox")'
views:
  - type: table
    name: アイデア
    order:
      - file.name
      - file.mtime
    sort:
      - property: file.name
        direction: DESC
    limit: 5
```

## 部署の記録

秘書室以外の部署ができると、ここに並びます。まだ無いうちは空のままで大丈夫です。

```base
filters:
  and:
    - 'file.ext == "md"'
    - '!file.inFolder("secretary")'
    - '!file.name.contains("CLAUDE")'
    - 'file.name != "Home"'
    - 'file.name != "README"'
views:
  - type: table
    name: 部署
    order:
      - file.name
      - file.folder
      - file.mtime
    sort:
      - property: file.mtime
        direction: DESC
    limit: 15
```

---

## 指示書

- [[CLAUDE|会社のルール]] — 全員に共通の決めごと。**部署一覧もここ**
- [[secretary/CLAUDE|秘書の指示書]] — 役割・口調・仕事の手順

書き換えれば、秘書の動きが変わります。
