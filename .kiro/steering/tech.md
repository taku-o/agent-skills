# 技術スタック

## アーキテクチャ

ビルドやランタイムを持たない、Markdown と JSON による宣言的な構成。Claude Code がスキル定義（`SKILL.md`）とプラグイン manifest（`plugin.json`）を読み込んで動作する。アプリケーションコードやパッケージ依存は持たない。

## コア技術

- **スキル定義**: `SKILL.md`（YAML frontmatter + Markdown 本文）
- **プラグイン manifest**: `.claude-plugin/plugin.json`
- **marketplace 定義**: `.claude-plugin/marketplace.json`
- **記述言語**: 日本語（ドキュメント・スキル本文ともに）

## 記述標準

### SKILL.md の frontmatter
- `name`: スキル名（ディレクトリ名と一致）
- `description`: 「何をするか」だけでなく「いつ発動するか」を具体的なトリガーワードとともに明記する
- `allowed-tools`: 必要なツールを最小限に限定する（例: `Bash(jj:*)`、`Bash(rm:*), Bash(cp:*)`）

### plugin.json / marketplace.json
- `name` はプラグインディレクトリ名と一致させる
- `description` は marketplace.json 側とプラグイン側で内容を揃える
- `author` は `{ name: "taku-o", email: "mail@nanasi.jp" }`

## 主要ツール

- **GitHub CLI（`gh`）**: 利用可能
- **jj（Jujutsu）**: バージョン管理ワークフローで使用

## 主要な技術的判断

- フォールバックや将来拡張を前提にした作りはしない（`.claude/rules/development-style.md` 参照）。ドキュメントにない機能は実装しない。
- marketplace 名は予約名を避け `taku-o-skills` を使用する。

---
_標準とパターンを記述し、全依存を列挙しない_
