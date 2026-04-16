---
name: ipa-sec-todokede-start
description: IPA のウェブアプリケーション脆弱性届出を始めるためのスキル。対象区分を確認し、URL・確認日・現象・証跡などの基本情報を聞き取り、.ipa-sec-todokede/report.json を初期化する。
---

# startスキル

ウェブアプリケーションの脆弱性を IPA に届け出るための最初の整理を行う。

## コマンド

```text
/ipa-sec-todokede-start
```

---

## 手順

### Step 1: 対象区分を確認する

最初に、対象が **ウェブアプリケーション** かどうかを確認する。

- ウェブサイトや Web サービスの脆弱性 → このスキルで続行
- ソフトウェア製品の脆弱性 → 別区分を案内して終了
- 自社製品の公表相談 → 自社製品向け区分を案内する

### Step 2: 最初に聞くこと

以下を順番に確認する。
不足しているものがあれば、その場で質問する。
わからないものは空欄のまま進めてよい。

```text
- 脆弱性を確認したウェブサイトのURL
- 脆弱性の確認日
- どの画面・機能で見つけたか
- 何をしたら、何が起きたか
- 再現するか
- 影響を受けるのは誰か
- 証跡はあるか（スクリーンショット・ログ・コード）
- すでにどこかへ連絡したか
- ウェブサイト運営者の連絡先がわかるか
```

### Step 3: report.json を初期化する

以下の形式で `.ipa-sec-todokede/report.json` を作る。

```json
{
  "target_type": "web_application",
  "site_url": null,
  "confirmed_at": null,
  "screen_or_feature": null,
  "summary": null,
  "steps_to_reproduce": [],
  "observed_behavior": null,
  "affected_users": null,
  "vuln_type": null,
  "cwe": [],
  "why_vulnerable": null,
  "threats": {
    "confidentiality": null,
    "integrity": null,
    "availability": null
  },
  "evidence": {
    "screenshots": [],
    "logs": [],
    "poc": []
  },
  "site_contact": null,
  "other_disclosures": [],
  "cvss": {
    "vector": null,
    "base_score": null,
    "rationale": {}
  }
}
```

### Step 4: いまわかっている要点を短くまとめる

ユーザーに 3〜5 行で返す。
この段階では断定しすぎない。

例:

```text
- 対象: https://example.com/
- 発見日: 2026-04-16
- 現象: 他人の請求書PDFにアクセスできた
- 想定カテゴリ: アクセス制御不備 / 情報漏えい
- 次にやること: CWE候補の整理、再現手順の明文化、証跡の確認
```
