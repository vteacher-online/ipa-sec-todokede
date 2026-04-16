# ipa-sec-todokede — IPA の脆弱性届出を AI に任せる

「これ、IPAに出してよいのか？」
「CWEは何を書く？」
「CVSSの根拠、どう書けばよい？」

そういう面倒ごとを、AIにやってもらうための Claude Code 用スキルです。

対象は **ウェブアプリケーション脆弱性関連情報の届出** です。
OS・ブラウザ・サーバソフト・アプリ・機器などの **ソフトウェア製品** は別区分なので、このスキルでは扱いません。

## この repo の考え方

この repo は **skill 単位で入れる** 前提で作っています。

最初はこれだけで十分です。

```bash
npx skills add vteacher-online/ipa-sec-todokede --skill start -a claude-code
```

必要になったら、あとから足していきます。

```bash
npx skills add vteacher-online/ipa-sec-todokede --skill cwe -a claude-code
npx skills add vteacher-online/ipa-sec-todokede --skill severity -a claude-code
npx skills add vteacher-online/ipa-sec-todokede --skill draft -a claude-code
npx skills add vteacher-online/ipa-sec-todokede --skill checklist -a claude-code
npx skills add vteacher-online/ipa-sec-todokede --skill export -a claude-code
```

全部まとめて入れたい場合:

```bash
npx skills add vteacher-online/ipa-sec-todokede -a claude-code
```


## どれを入れればよいか

| やりたいこと | 入れる skill |
|-------------|-------------|
| まず通報対象か整理したい | `start` |
| CWEだけ決めたい | `cwe` |
| 深刻度だけ書きたい | `severity` |
| フォーム本文を作りたい | `draft` |
| 提出前チェックだけしたい | `checklist` |
| 保存用ファイルをまとめたい | `export` |

## コマンド一覧

| コマンド | やること |
|---------|---------|
| `/ipa-sec-todokede` | いま何をやるべきかを整理するハブ |
| `/ipa-sec-todokede-start` | 通報対象の整理を始める |
| `/ipa-sec-todokede-cwe` | CWE候補を整理する |
| `/ipa-sec-todokede-severity` | CVSSと深刻度・影響範囲の下書きを作る |
| `/ipa-sec-todokede-draft` | IPAフォームに転記できる下書きを作る |
| `/ipa-sec-todokede-checklist` | 添付漏れ・記入漏れを確認する |
| `/ipa-sec-todokede-export` | 提出用の Markdown と JSON を保存する |

## おすすめの入れ方

### いちばん軽い構成

```bash
npx skills add vteacher-online/ipa-sec-todokede --skill start -a claude-code
npx skills add vteacher-online/ipa-sec-todokede --skill draft -a claude-code
```

これで、
- まず情報を整理する
- そのまま下書きにする

ところまでは進められます。

### 実務でいちばん使う構成

```bash
npx skills add vteacher-online/ipa-sec-todokede --skill start -a claude-code
npx skills add vteacher-online/ipa-sec-todokede --skill cwe -a claude-code
npx skills add vteacher-online/ipa-sec-todokede --skill severity -a claude-code
npx skills add vteacher-online/ipa-sec-todokede --skill draft -a claude-code
npx skills add vteacher-online/ipa-sec-todokede --skill checklist -a claude-code
```

## 保存先

各 skill は同じ保存先を使います。

```text
.ipa-sec-todokede/
├── report.json
├── draft.md
├── severity.md
├── checklist.md
└── evidence/
    ├── screenshots/
    ├── logs/
    └── poc/
```

## 注意事項

- このスキルは **届出文面の整理** を助けるものです。提出先の最終確認は必ず自分で行ってください。
- 脆弱性関連情報は、正当な理由がない限り第三者に開示しない前提で使ってください。
- 「届け出れば必ず保護される」といった断定はしません。
- 制度やフォームは変わることがあるため、最終的には必ず IPA の最新案内を確認してください。

## ライセンス

MIT
