---
name: ipa-sec-todokede
description: IPA のウェブアプリケーション脆弱性届出で、いま何をやるべきかを整理するハブスキル。状況に応じて start / cwe / severity / draft / checklist / export のどれを使うか案内する。Claude Code専用。
---

# ipa-sec-todokede — ハブスキル

IPA のウェブアプリケーション脆弱性届出を進めるときの入口。

このスキル自身は長い本文を作り込むのではなく、
**いま足りないものを見て、次に使うべき skill を 1 つだけ案内する。**

## コマンド一覧

| コマンド | やること |
|---------|---------|
| `/ipa-sec-todokede` | いま何をやるべきかを整理する |
| `/ipa-sec-todokede-start` | 通報対象の整理を始める |
| `/ipa-sec-todokede-cwe` | CWE候補を整理する |
| `/ipa-sec-todokede-severity` | CVSSと深刻度・影響範囲の下書きを作る |
| `/ipa-sec-todokede-draft` | IPAフォームに転記できる下書きを作る |
| `/ipa-sec-todokede-checklist` | 添付漏れ・記入漏れを確認する |
| `/ipa-sec-todokede-export` | 提出用の Markdown と JSON を保存する |

---

## `/ipa-sec-todokede` の動作

### Step 1: まず今の状態を聞く

短く以下だけ確認する。

```text
- まだ何も整理していない
- CWEで止まっている
- 深刻度で止まっている
- フォーム本文で止まっている
- 提出前で不安
- 保存したい
```

### Step 2: 次に使う skill を 1 つだけ案内する

- まだ何も整理していない → `/ipa-sec-todokede-start`
- CWEで止まっている → `/ipa-sec-todokede-cwe`
- 深刻度で止まっている → `/ipa-sec-todokede-severity`
- 本文で止まっている → `/ipa-sec-todokede-draft`
- 提出前で不安 → `/ipa-sec-todokede-checklist`
- 保存したい → `/ipa-sec-todokede-export`

### Step 3: 長く説明しない

3〜5行で返す。
説明より導線を優先する。

## 各スキルの詳細

- `skills/start/SKILL.md`
- `skills/cwe/SKILL.md`
- `skills/severity/SKILL.md`
- `skills/draft/SKILL.md`
- `skills/checklist/SKILL.md`
- `skills/export/SKILL.md`
