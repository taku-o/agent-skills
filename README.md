# agent-skills

taku-o の Claude Code [Agent Skills](https://docs.claude.com/en/docs/claude-code/skills) をまとめた Claude Code プラグイン marketplace です。

## インストール

Claude Code でこの marketplace を登録します。

```
/plugin marketplace add taku-o/agent-skills
```

ローカルのクローンから登録する場合:

```
/plugin marketplace add /path/to/agent-skills
```

登録後、プラグインをインストールします。

```
/plugin install jj-new@agent-skills
```

`/plugin` を開いて GUI から選択することもできます。

## 収録プラグイン

| プラグイン | 説明 |
| --- | --- |
| `jj-new` | `jj new` を実行して新しい jj チェンジを作成する。現在のチェンジの description が未設定なら Conventional Commits スタイルで設定してから実行する。 |
| `prevent-auto-commit` | AI が `git commit` / `jj new` を自己判断で実行することを防ぐガードレール。明示的な指示やスキルのワークフロー時のみ許可する。 |

## 構成

```
agent-skills/
├── .claude-plugin/
│   └── marketplace.json          # marketplace 定義（収録プラグイン一覧）
└── plugins/
    ├── jj-new/
    │   ├── .claude-plugin/
    │   │   └── plugin.json        # プラグイン manifest
    │   └── skills/
    │       └── jj-new/
    │           └── SKILL.md       # スキル本体
    └── prevent-auto-commit/
        ├── .claude-plugin/
        │   └── plugin.json
        └── skills/
            └── prevent-auto-commit/
                └── SKILL.md
```

新しいスキルを追加するときは、`plugins/<name>/` 配下に同じ構成でプラグインを置き、`.claude-plugin/marketplace.json` の `plugins` 配列にエントリを追加します。

## ライセンス

[MIT](./LICENSE)
