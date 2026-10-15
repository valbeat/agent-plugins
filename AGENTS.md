# agent-plugins

## 位置づけ

- 役割: 公開できる汎用スキルのマーケットプレイス（writing / design / git-workflow / dev-workflow / skill-tools）。個人環境に依存するスキルは valbeat/agent-plugins-private に置き、汎用化できたものだけをここへ昇格させる
- 読ませない相手: public なので、個人の文脈（dashboard の goals・memo・業務の固有情報）を持ち込まない
- 自動で書くもの: なし。リポ群の地図は `~/src/github.com/valbeat/dashboard/docs/knowledge/repo-map.md`

## 規約

- 置き場の判定と棚卸しの手順は agent-plugins-private の `skill-management:skill-inventory` スキルが正。ここには写さない
- 1 プラグイン = `plugins/<name>/`。`.claude-plugin/plugin.json`（Claude Code）と、Codex でも動くものだけ `.codex-plugin/plugin.json` を置き、`skills/` を共有する。version は 2 つのマニフェストで揃える
- Codex 用カタログ `.agents/plugins/marketplace.json` には、サブエージェント・モデル指定・AskUserQuestion 前提の対話・`~/.claude` の構成に依存しないプラグインだけを載せる（現状: writing / design / git-workflow）
- スキル本文は日本語。frontmatter の `name` と `description` は必須
- フィーチャーブランチ + `gh pr create --assignee @me --draft`。Conventional Commit 形式
