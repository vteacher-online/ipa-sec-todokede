---
name: ipa-sec-cwe
description: IPA届出フォームの「脆弱性の種類」と「CWEとの関連付け」を整理するスキル。候補を出しすぎず、もっとも近いものを 1〜3 個に絞って理由付きでまとめる。
---

# cweスキル

フォームの「脆弱性の種類」と「CWEとの関連付け」を埋めるための整理を行う。

## コマンド

```text
/cwe
```

---

## 手順

### Step 1: ユーザーの説明から種類を当てる

以下を整理する。

- フォーム上の分類（XSS / SQLインジェクション / CSRF / その他 など）
- CWE-XXX の候補

### Step 2: 候補は 1〜3 個までに絞る

候補を出しすぎない。
もっとも近いものを先頭にする。
迷う場合は「第一候補」「第二候補」として示す。

出力例:

```text
脆弱性の種類: その他（認可・アクセス制御の不備）

CWE候補:
1. CWE-284 Improper Access Control
2. CWE-200 Exposure of Sensitive Information to an Unauthorized Actor
```

### Step 3: 理由を1行ずつ添える

例:

```text
- CWE-284: 他ユーザーのデータへ認可なしでアクセスできるため
- CWE-200: 本来見えない情報が取得できているため
```

### Step 4: report.json に保存する

```json
{
  "vuln_type": "その他",
  "cwe": ["CWE-284", "CWE-200"]
}
```

### Step 5: 表記ミスに注意する

- `CWE-XXX` と書く
- `CWS-XXX` とは書かない
- 古い包括的なCWEより、なるべく具体的なCWEを優先する
