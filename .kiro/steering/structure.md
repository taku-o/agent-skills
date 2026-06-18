# プロジェクト構成

## 構成思想

プラグインごとに自己完結したディレクトリを持つ、marketplace 中心の構成。各プラグインは同一の入れ子パターンに従い、`marketplace.json` が一覧を束ねる。

## ディレクトリパターン

### marketplace 定義
**場所**: `.claude-plugin/marketplace.json`
**目的**: 収録プラグインの一覧と各プラグインへの相対パス（`source`）を定義する。

### プラグイン
**場所**: `plugins/<name>/`
**目的**: 1 プラグイン = 1 ディレクトリ。以下の固定構成を取る。
```
plugins/<name>/
├── .claude-plugin/
│   └── plugin.json        # プラグイン manifest
└── skills/
    └── <name>/
        └── SKILL.md       # スキル本体（必要に応じて補助ファイルを同梱）
```

### ドキュメント
**場所**: `docs/`
**目的**: プロジェクト構成などの補足ドキュメント（例: `docs/project-structure.md`）。

## 命名規約

- **プラグイン名 / スキル名**: kebab-case（例: `jj-new`、`prevent-auto-commit`、`rm-file`）
- **ディレクトリ名 = `plugin.json` の `name` = `SKILL.md` の `name`** を一致させる

## 新規プラグイン追加の手順

1. `plugins/<name>/` 配下に上記の固定構成でファイルを作成する。
2. `.claude-plugin/marketplace.json` の `plugins` 配列にエントリを追加する。
3. README.md の収録プラグイン表を更新する。

## コード構成の原則

- プラグインは互いに独立しており、相互依存を持たせない。
- 1 スキルは単機能に保ち、発動条件を description に明記する。

---
_パターンを記述しファイルツリーを列挙しない。パターンに従う新規ファイルは更新を要さない_
