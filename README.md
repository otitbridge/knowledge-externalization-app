# 暗黙知の形式知化スターター

技能伝承や引継ぎで、対話・観察・既存資料に含まれる知識を整理するためのスターターです。生成AIと人が協働してMarkdownの正本を作り、Gitで根拠と変更を管理します。保全、検査、引継ぎ、問い合わせ対応などで、対象に合わせて利用できます。

この版に含むのは運用ルール、3つのSkills、入力テンプレート、導入・検証手順です。アプリの実装や自動生成・検証プログラムは含みません。SkillsはAIが資料を読み、所定の手順で編集・照合するための指示です。

## 最初に読むもの

1. [AGENTS.md](AGENTS.md)：全作業のルール
2. [導入設定](docs/project-profile.md)：用途・担当者・共有範囲
3. [運用手順](docs/workflow.md)：資料の受領から更新まで
4. [知識の書式](docs/knowledge-format.md)：ID・根拠版・正本・図の対応
5. [検証チェックリスト](docs/validation-checklist.md)：変更後の検査

## 使い始める

このフォルダ全体を新しい用途の作業フォルダへコピーします。既存プロジェクトへ導入する場合は、既存のAGENTS.md・Skills・ID体系と照合してから統合します。

`docs/project-profile.md` と [確認票](review/questions.md) の導入事項を、分かる範囲で記入します。未決定のままでも、資料の整理と草稿作成は開始できます。正式利用と外部共有は、それぞれの判断が必要な時点で確認します。

Gitを使う場合は、新しい作業フォルダ内で `git init` し、登録対象を確認してからコミットします。原本には機密情報が含まれうるため、公開先を自動的に作らないでください。根拠版の固定とコミットの順序は [運用手順](docs/workflow.md) に記載しています。

資料を受領したら原本を `source/records/` に保存し、[一次資料索引](templates/source-index.md) を基に `source/index.md` を作ります。既存原本を上書きせず、正本は資料に根拠のある内容から作成します。

## Skills

| Skill | 用途 |
|---|---|
| [structure-knowledge](.agents/skills/structure-knowledge/SKILL.md) | 発言・観察を、根拠付きの知識項目と確認事項へ構造化 |
| [review-knowledge](.agents/skills/review-knowledge/SKILL.md) | 回答・レビュー・承認を区別して正本へ反映 |
| [derive-knowledge-artifacts](.agents/skills/derive-knowledge-artifacts/SKILL.md) | 正本から図・一覧・根拠付き教材を作成・照合 |

Skillsを使う環境では、このフォルダを作業対象として開いてください。Skillだけをコピーすると共通書式への相対参照が切れます。手動で利用する場合も同じ手順を読んで実施できます。

依頼例：

```text
$structure-knowledge を使い、source/records/ に保存した対話を構造化してください。
根拠のある知識だけを canonical/ に保存し、不明点を review/questions.md へ追加してください。
```

```text
$review-knowledge を使い、追加回答を反映してください。
回答者の役割と確認対象を照合し、確認されていない範囲の状態は昇格させないでください。
```

```text
$derive-knowledge-artifacts を使い、指定した正本からレビュー用の図を作ってください。
未確定の接続を補わず、根拠・状態・参照版の対応を検査してください。
```

## テンプレート

| テンプレート | 記入後の配置 |
|---|---|
| [導入設定](templates/project-profile.md) | `docs/project-profile.md` |
| [対話・観察記録](templates/source-record.md) | `source/records/` |
| [一次資料索引](templates/source-index.md) | `source/index.md` |
| [正本](templates/canonical.md) | `canonical/` |
| [確認事項](templates/questions.md) | `review/questions.md` へ追記 |
| [レビュー・承認記録](templates/review-record.md) | `review/records/` |
| [実践記録](templates/work-session.md) | `data/work-sessions/` |
| [派生物管理票](templates/artifact-record.md) | `derived/records/` |
| [検証記録](templates/validation-report.md) | `reports/` |

`{{...}}` は記入箇所です。実データに残さず、不明な業務内容はQへ移します。テンプレートは正本・一次資料・承認記録そのものではありません。

[架空の使用例](examples/DEMO-document-handover.md)で、手順が不明なまま知識を保持する方法を確認できます。
