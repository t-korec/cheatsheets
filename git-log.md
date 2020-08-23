---
title: git log
category: Git
layout: 2017/sheet
keywords:
  - "git log --pretty=format:%H"
  - "%H - Commit hash"
  - "%an - Author"
  - "%aD - Author date"
---

### Revision ranges

```bash
git log master             # branch
git log origin/master      # branch, remote
git log v1.0.0             # tag

git log master develop

git log v2.0..master       # reachable from *master* but not *v2.0*
git log v2.0...master      # reachable from *master* and *v2.0*, but not both
```

See [gitrevisions](./git-revisions).

### Log options

    --oneline
      e11e9f9 Commit message here

    --decorate
      shows "(origin/master)"

    --graph
      shows graph lines

    --date=relative
      "2 hours ago"

### Basic filters

```bash
-n, --max-count=2
    --skip=2
```

```bash
    --since="1 week ago"
    --until="yesterday"
```

```bash
    --author="Rico"
    --committer="Rico"
```

### Search

```bash
    --grep="Merge pull request"   # in commit messages
    -S"console.log"               # in code
    -G"foo.*"                     # in code (regex)
```

```bash
    --invert-grep
    --all-match                   # AND in multi --grep
```

### Limiting

```bash
    --merges
    --no-merges
```

```bash
    --first-parent          # no stuff from merged branches
```

```bash
    --branches="feature/*"
    --tags="v*"
    --remotes="origin"
```

### Simplification

```bash
git log -- app/file.rb          # only file
    --simplify-by-decoration    # tags and branches
```

### Ordering

```bash
    --date-order
    --author-date-order
    --topo-order              # "smart" ordering
    --reverse
```

### Formatting

```bash
    --abbrev-commit
    --oneline
    --graph
```

### Custom formats

```bash
    --pretty="format:%H"
```


## Log format
{: .-three-column}

### Pretty format
{: .-prime}

```bash
git log --pretty="format:%H"
```

See the next tables on format variables.

### Hash

#### Commit

| Variable | Description |
| --- | --- |
| `%H` | commit hash |
| `%h` | (abbrev) commit hash |

#### Tree

| Variable | Description |
| --- | --- |
| `%T` | tree hash |
| `%t` | (abbrev) tree hash |

#### Parent

| Variable | Description |
| --- | --- |
| `%P` | parent hash |
| `%p` | (abbrev) parent hash |

### Commit

| Variable | Description |
| --- | --- |
| `%s` | commit subject |
| `%f` | commit subject, filename style |
| `%b` | commit body |
| --- | --- |
| `%d` | ref names |
| `%e` | encoding |

## Author and committer

### Author

#### Name

| Variable | Description |
| --- | --- |
| `%an` | author |
| `%aN` | author, respecting mailmap |

#### Email

| Variable | Description |
| --- | --- |
| `%ae` | author email |
| `%aE` | author email, respecting mailmap |

#### Date

| Variable | Description |
| --- | --- |
| `%aD` | author date (rfc2882) |
| `%ar` | author date (relative) |
| `%at` | author date (unix timestamp) |
| `%ai` | author date (iso8601) |

### Committer

#### Name

| Variable | Description |
| --- | --- |
| `%cn` | committer name |
| `%cN` | committer name, respecting mailmap |

#### Email

| Variable | Description |
| --- | --- |
| `%ce` | committer email |
| `%cE` | committer email, respecting mailmap |

#### Date

| Variable | Description |
| --- | --- |
| `%cD` | committer date (rfc2882) |
| `%cr` | committer date (relative) |
| `%ct` | committer date (unix timestamp) |
| `%ci` | committer date (iso8601) |
