# agent-skills

taku-o の Claude Code [Agent Skills](https://docs.claude.com/en/docs/claude-code/skills) をまとめた Claude Code プラグイン marketplace です。

## 収録プラグイン

| プラグイン | 説明 |
| --- | --- |
| `jj-new` | `jj new` を実行して新しい jj チェンジを作成する。現在のチェンジの description が未設定なら Conventional Commits スタイルで設定してから実行する。 |
| `prevent-auto-commit` | AI が `git commit` / `jj new` を自己判断で実行することを防ぐガードレール。明示的な指示やスキルのワークフロー時のみ許可する。 |
| `rm-file` | `rm` でファイル削除、`cp` でファイル上書きをする際に `-f` オプションを付けて実行する。 |
| `write-claude-code-fnc` | Claude Code のスキル・プラグイン・サブエージェント・フック・設定を作成・修正する。作業前に公式ドキュメントを参照して正しい配置・フォーマットを確認する。 |

## インストール

Claude Code でこの marketplace を登録します。

```
/plugin marketplace add taku-o/agent-skills
```

登録後、プラグインをインストールします。

```
/plugin install jj-new@agent-skills
```

`/plugin` を開いて GUI から選択することもできます。

## ライセンス

[MIT](./LICENSE)
