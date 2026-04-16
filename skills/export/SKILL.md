---
name: export
description: ipa-sec-todokede で整理した内容を .ipa-sec-todokede/ 配下に保存するスキル。report.json・draft.md・severity.md・checklist.md の存在を確認し、不足しているものを作ってから最終出力する。
---

# exportスキル

提出用のファイルを保存して、最後の状態を整える。

## コマンド

```text
/export
```

---

## 手順

### Step 1: 保存先を確認する

以下のディレクトリがなければ作る。

```text
.ipa-sec-todokede/
.ipa-sec-todokede/evidence/
.ipa-sec-todokede/evidence/screenshots/
.ipa-sec-todokede/evidence/logs/
.ipa-sec-todokede/evidence/poc/
```

### Step 2: 必須ファイルを確認する

以下のファイルの有無を確認する。

- `.ipa-sec-todokede/report.json`
- `.ipa-sec-todokede/draft.md`
- `.ipa-sec-todokede/severity.md`
- `.ipa-sec-todokede/checklist.md`

不足しているものがあれば、その場で最小限の内容で生成する。

### Step 3: report.json の最低限チェックを行う

最低限、以下が入っているか確認する。

```text
- target_type
- site_url
- confirmed_at
- summary
- vuln_type
- cwe
```

空欄があれば短く指摘する。

### Step 4: 最終出力を並べる

以下の順番で要約して表示する。

```text
- 対象URL
- 脆弱性の種類
- CWE候補
- CVSSベクトル
- 証跡の有無
- 他所への届出有無
- 未記入項目
```

### Step 5: 最後に短く案内する

以下の温度感で締める。

```text
下書きは保存しました。あとは IPA のウェブ届出フォームに転記してください。
制度やフォームは変わることがあるので、最終的には公式案内を確認してください。
```
