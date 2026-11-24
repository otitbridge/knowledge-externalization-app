# 本人への確認をもとに、作業の順番と図を更新する

家事・育児の記録から、子どもの寝床をいつ準備するのかを確かめます。原文を正本Markdownに整理し、本人の回答で正本を直し、その変更をMermaid図に反映するところまで試せます。教材には、順番の確認に関わる箇所を収録しています。

## 1. 原文から確認したいことを見つける

[原文の抜粋](source/records/routine-excerpt.txt)を読み、作業する人と前後関係を整理します。[修正前の正本](canonical/tutorial-before.md)と[修正前の図](diagrams/tutorial-before-flowchart.md)では、食洗機、ごみ出し、寝床の準備がどうつながっているかを見てください。原文での記述順だけで、実際の順番を決められるでしょうか。

生成AIを使う場合は、[`structure-knowledge`](.agents/skills/structure-knowledge/SKILL.md)と原文の抜粋を読み込ませ、作業を整理し、確認が必要な前後関係について質問を出してもらいます。

## 2. 本人の回答で正本を更新する

[確認票](review/questions.md)のQ-006と[本人の回答](source/records/answers.md)を読み、修正前の正本をコピーして編集します。AIを使う場合は、[`review-knowledge`](.agents/skills/review-knowledge/SKILL.md)に沿って、どの関係がどの回答で変わるかを示してもらってから反映します。

[修正後の正本](canonical/tutorial-after.md)と見比べ、ミルクをあげ始めた直後に寝床を用意し、そのあとで父が家事を一つずつ順不同で行うことを確かめます。妻に小声で呼ばれたら、作業中でも手を止めて子どもを預かります。

## 3. 更新した正本から図を作る

修正した正本の関係をMermaidで図にします。AIを使う場合は[`derive-knowledge-artifacts`](.agents/skills/derive-knowledge-artifacts/SKILL.md)を読み込ませ、正本の遷移を矢印に、順不同の家事を同じ枠に置くように依頼します。[修正後の図と対応表](diagrams/tutorial-after-flowchart.md)で、旧R-018の矢印が消え、R-032とR-035が加わったことを確認できます。

Mermaidを表示できる環境では[修正前](diagrams/tutorial-before-flowchart.mmd)・[修正後](diagrams/tutorial-after-flowchart.mmd)のコードをそのまま開けます。[入力資料の一覧](source/index.md)と[図の管理票](derived/records/tutorial.md)に、各資料と図の対応を記録しています。
