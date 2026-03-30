# ADR-001: フォルダ構成ルール

*決定日: 2026-03-30*

## 背景

Claude Code のベストプラクティスを写経しながら学ぶプロジェクト。
Anthropic公式の一次情報をインプットし、自分の仕事に使える形で資産化するのが目的。

compound-effect/ のフレームワーク（ログ → 共通項 → 資産化）を学習にも適用する。
スキマ時間に少しずつ進める前提なので、「どこまでやったか」「次どこから」がすぐわかることが重要。

## 全体構成

```
claude-code-catchup/
├── PROGRESS.md                # エントリーポイント（進捗・次どこから）
├── meta/                      # 運用ルール・テンプレート・プロンプト
│   ├── 001-folder-structure.md
│   ├── templates/
│   │   └── study-note.md      # 写経ノートのテンプレート
│   └── prompts/
│       └── session-start.md   # セッション開始プロンプト
├── notes/                     # 写経ノート（セクション別）
│   ├── 01-xxx.md
│   ├── 02-xxx.md
│   └── ...
└── extractions/               # 抽出パターン（自分の仕事に使える形）
    └── topic-name.md
```

## ルール

### PROGRESS.md（ルート直下）

- **役割: 再開のエントリーポイント**
- 「どのセクションまで終わったか」「次どこから始めるか」がわかることが最優先
- 含めるもの: 現在の進捗、次にやるセクション、抽出済みパターンの一覧

### notes/（写経ノート）

- **役割: 記事の写経 + 自分の気づきの記録**
- ファイル名: `NN-セクション名.md`（記事の構成に合わせた連番）
- 写経と自分の気づき・疑問を混ぜて書いてOK
- 完璧に書く必要はない。理解を深めることが目的
- テンプレート: `meta/templates/study-note.md` を使う

### extractions/（抽出パターン）

- **役割: 自分の仕事に使える形で抜き出したもの**
- ファイル名: 内容がわかる名前（日付不要）
- 十分に成熟したら `compound-effect/assets/` に昇格させる
- 例: 壁打ちプロンプトの改善 → `compound-effect/assets/procedures/implementation-task-flow.md` に統合

### meta/ フォルダ

- compound-effect/ と同じパターン
- 運用ルール・テンプレート・プロンプトを管理する

## compound-effect/ との関係

- **claude-code-catchup/** は学習のインプット側（写経・理解）
- **compound-effect/** は実践のアウトプット側（資産化・運用）
- 学んだことが実務に使えると判断したら、extractions/ → compound-effect/assets/ に昇格
- 日々の学習記録は compound-effect/meta/reviews/ の夜の振り返りにも書く
