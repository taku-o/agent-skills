# プロダクト概要

`agent-skills` は、taku-o の Claude Code [Agent Skills](https://docs.claude.com/en/docs/claude-code/skills) をまとめた Claude Code プラグイン marketplace（`taku-o-skills`）。日常の開発ワークフローを補助するスキルをプラグインとして配布する。

## コア機能

- **プラグイン marketplace**: `.claude-plugin/marketplace.json` で収録プラグイン一覧を定義し、`/plugin marketplace add` で登録できる。
- **ワークフロー補助スキル**: バージョン管理（`jj-new`）、安全策（`prevent-auto-commit`、`rm-file`）、Claude Code 自体の拡張作業支援（`write-claude-code-fnc`）など、独立した単機能スキルを提供する。
- **ガードレール系スキル**: AI が自己判断で破壊的・不可逆な操作（コミット、ファイル削除）を行わないよう抑止する。

## 主な利用シーン

- ユーザーが marketplace を登録し、必要なスキルを個別にインストールして使う。
- スキルの発動条件（description）に合致した操作を Claude Code が行おうとした際に、自動でスキルが呼び出される。

## 価値提案

各スキルは「いつ発動するか」を description に明記した単機能の部品として設計されており、marketplace 形式で選択的にインストールできる。安全策とワークフロー自動化を、利用者が必要な分だけ組み合わせられる点が特徴。

---
_パターンと目的に焦点を当て、機能の網羅的な列挙は避ける_
