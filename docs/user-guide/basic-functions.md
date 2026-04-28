# SleepVivo の基本機能

SleepVivo は、眠る前から起きるまでの流れに合わせて、画面の明るさ、色温度、音量などを切り替えます。
このページでは、SleepVivo がどの場面で何をするか、ユーザー操作で何が変わるかを説明します。

## 基本の流れ

SleepVivo は、おおまかに次の流れで動きます。

1. 眠る前：普段どおりの状態です。
2. 眠る準備：寝る時刻に向けて、画面や音を眠りやすい方向へ変えます。
3. 睡眠中：睡眠中向けの明るさ、色温度、音量を保ちます。
4. 起きる準備：起きる時刻に向けて、画面や音を戻します。

この流れは、予定時刻、寝落ち検知、手動操作によって進みます。

## 眠る準備で行うこと

眠る準備では、[入眠誘導](sleep-induction.md) の設定に沿って、少しずつ眠りやすい状態へ近づけます。

1. 明るさを下げます。
2. 色温度制御を使っている場合は、色温度を変えます。
3. 音量を下げます。
4. 設定している場合は、対応する自動化・連携を実行します。

どのくらい時間をかけて変えるかは、[睡眠・起床の調整](sleep-wake-settings.md) で設定できます。

## 睡眠中に行うこと

睡眠中は、睡眠中向けの設定を保ちます。

1. 睡眠中の明るさ、色温度、音量を使います。
2. 寝落ち検知や起床サポートの対象になります。
3. 睡眠中に実行する自動化・連携がある場合は、その設定に沿って動きます。

睡眠中向けの値は、[睡眠・起床の調整](sleep-wake-settings.md) で確認できます。

## 起きる準備で行うこと

起きる準備では、[起床誘導](wake-induction.md) の設定に沿って、起きやすい状態へ戻します。

1. 明るさを戻します。
2. 色温度制御を使っている場合は、色温度を戻します。
3. 音量は、眠る前に記録した音量へ戻します。
4. 設定している場合は、起床時の自動化・連携を実行します。

起きる時刻は、固定時刻または [スケジュール](scheduler.md) で決まります。

## 手動操作でできること

SleepVivo の状態は、デスクトップGUIのホーム画面と [VR Overlay](vr-overlay.md) から手動で切り替えられます。
表示されるボタンは、その時点でできる操作だけです。

| 表示されるボタン | 表示される場面 | 押したときの動き |
| --- | --- | --- |
| `Sleep now` | 眠る前 | 眠る準備を開始します。 |
| `Not yet` | 眠る準備中 | いったん眠る準備をやめます。設定している場合は、あとでもう一度眠る準備が始まります。 |
| `Already asleep` | 眠る準備中 | すぐに睡眠中向けの状態へ切り替えます。 |
| `I am awake` | 睡眠中 | 起きたものとして扱い、起きる方向へ戻します。 |
| `Keep sleeping` | 起きる準備中 | まだ眠るものとして扱い、睡眠中向けの状態へ戻します。 |
| `I am awake` | 起きる準備中 | 起きたものとして扱い、起床サポートを完了します。 |

## デスクトップGUIで操作する

デスクトップGUIでは、ホーム画面上部の SleepVivo エリアに現在の状態と操作ボタンが表示されます。
表示されているボタンを押すと、上の表と同じ動きになります。

今日の入眠予定時刻と起床予定時刻も、ホーム画面からすばやく確認・変更できます。
日ごとの予定を細かく管理する場合は、[スケジュール](scheduler.md) を使います。

## VR Overlay で操作する

VR Overlay では、VR 内から同じ操作ができます。
HMD を外さずに、眠る準備、起床、明るさ、色温度、音量の調整を行いたい場合に使います。

詳しい開き方と操作は [VR Overlay](vr-overlay.md) を確認してください。

## 設定との関係

基本の流れは、次のページで設定します。

1. [初回設定](first-setup.md)：最初に入眠予定時刻と起床予定時刻を入れます。
2. [入眠誘導](sleep-induction.md)：眠る準備の明るさ、色温度、音量を調整します。
3. [起床誘導](wake-induction.md)：起きる準備の戻し方を調整します。
4. [睡眠・起床の調整](sleep-wake-settings.md)：眠る準備、睡眠中、起きる準備の値を細かく調整します。
5. [自動化・連携](automations.md)：各場面に合わせた外部連携を設定します。

## 困ったとき

思った場面に切り替わらない場合は、まず入眠予定時刻、起床予定時刻、入眠サポート、寝落ち検知、起床サポートが ON か確認してください。
解決しない場合は、[トラブルシューティング](troubleshooting.md) を確認してください。

## Review Checklist

- source files consulted: `U:\dev\SleepVivo\src-ui\app\views\dashboard-view\views\overview-view\overview-view.component.html`, `U:\dev\SleepVivo\src-ui\app\views\dashboard-view\views\overview-view\overview-view.component.ts`, `U:\dev\SleepVivo\src-ui\app\models\sleep-vivo-user-actions.ts`, `U:\dev\SleepVivo\src-ui\app\services\sleep-vivo-user-actions.service.ts`, `U:\dev\SleepVivo\src-ui\app\services\sleep-vivo-user-actions-runtime-core.ts`, `U:\dev\SleepVivo\src-overlay-ui\src\routes\dashboard\Overview.svelte`
- assumptions made: ユーザー向け説明では内部の状態名を使わず、画面に出る操作ラベルは現状の英語表記に合わせる
- items requiring human confirmation: デスクトップGUIの操作ボタンが日本語化された場合、このページと VR Overlay ページのボタン表記を更新する
