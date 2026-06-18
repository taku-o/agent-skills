# プロジェクト構成

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
    ├── prevent-auto-commit/
    │   ├── .claude-plugin/
    │   │   └── plugin.json
    │   └── skills/
    │       └── prevent-auto-commit/
    │           └── SKILL.md
    ├── rm-file/
    │   ├── .claude-plugin/
    │   │   └── plugin.json
    │   └── skills/
    │       └── rm-file/
    │           └── SKILL.md
    └── write-claude-code-fnc/
        ├── .claude-plugin/
        │   └── plugin.json
        └── skills/
            └── write-claude-code-fnc/
                └── SKILL.md
```

新しいスキルを追加するときは、`plugins/<name>/` 配下に同じ構成でプラグインを置き、`.claude-plugin/marketplace.json` の `plugins` 配列にエントリを追加します。
