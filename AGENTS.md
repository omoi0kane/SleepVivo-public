# SleepVivo Documentation Rules

## Product name
Use "SleepVivo". Do not use "SleepFit" except when explicitly discussing historical provenance.

## Audience
Write primarily for Japanese users. Use clear, non-technical wording for user-facing pages.

## Accuracy
Do not invent features, UI labels, settings, data fields, or guarantees.
If a feature is planned but not implemented, label it as planned.

## Research Program
Always explain that participation is optional.
Always distinguish:
- data collected
- data not collected
- purpose of use
- withdrawal / opt-out behavior

## Privacy
Do not claim full anonymity if the correct term is pseudonymous or de-identified.
Do not overstate GDPR compliance beyond the written specification.

## Style
Use short sections.
Prefer concrete steps over abstract explanation.
Use screenshots placeholders when screenshots are needed.

## Review
Do not include review checklists or internal review notes in public Markdown pages.
Keep source files consulted, assumptions made, and items requiring human confirmation in PR comments or private review notes only.


# SleepVivo Encoding / 日本語ファイル編集ポリシー

## 目的
日本語文字列の破壊（mojibake）を防止する。
特に「UTF-8 no BOM を CP932 として誤読し再保存する事故」を防ぐ。

---

## 基本方針

- 日本語を含む文書ファイル（`.md`, `.txt`）は UTF-8 with BOM で扱う
- Windows PowerShell 5.1 は日本語ファイル編集に使用しない
- 機械編集は encoding を明示する経路に限定する
- 軽微編集はエディタ（VS Code）を優先する

---

## 禁止事項（重要）

以下は禁止：

- Windows PowerShell 5.1 における日本語ファイル編集
- encoding 未指定の以下コマンドによる日本語編集
  - `Get-Content`
  - `Set-Content`
  - `Add-Content`
  - `Out-File`
  - `>`
  - `>>`
- 誤読状態のまま保存すること

---

## 許可される操作

以下は許可：

- VS Code エディタでの直接編集
- PowerShell 7 (`pwsh`) による encoding 明示編集
- Python / Node.js による encoding 明示編集
- リポジトリ内の `tools` 配下の安全スクリプトの使用

---

## 推奨手順（機械編集）

日本語ファイルを編集する場合：

1. リポジトリ内の `tools` の既存スクリプトを確認
2. あればそれを使用
3. なければ Python スクリプトで追加（utf-8-sig）
4. 編集後に必ず確認

---

## 確認ルール（必須）

編集後は必ず：

- ファイルを再読み込みする
- 以下が壊れていないことを確認
  - 先頭行
  - 見出し
  - UI文字列

---

## 文字化け検知ルール

以下の文字が含まれていた場合は異常とみなす：

- `繧`
- `縺`
- `蜈`
- `鬘`
- `郢`
- `�`

→ 即座に変更を破棄し、正常ファイルからやり直す

---

## 補足

このポリシーは「効率」より「破壊防止」を優先する。
