# VR Overlay

VR Overlay は、VR 内から SleepVivo の主な操作を行うためのメニューです。
HMD を外さずに、眠る準備、起きる操作、明るさや音量の調整、Research Program のアンケート回答ができます。

SleepVivo の基本的な流れは、デスクトップGUIと VR Overlay で共通です。
全体像は [SleepVivo の基本機能](basic-functions.md) を確認してください。

## 開く前に確認すること

1. SteamVR を起動します。
2. SleepVivo を起動します。
3. 「設定」>「一般設定」>「オーバーレイ」で「オーバーレイメニューを有効にする」が ON か確認します。
4. 「コントローラーバインディング」で、Overlay を開く操作が割り当てられているか確認します。
5. 必要に応じて「VRChatが実行中の場合のみメニューを開く」を ON にします。

!!! note "スクリーンショット"
    VR Overlay 画面のスクリーンショットは追加予定です。

## 画面の見方

Overlay の中央には SleepVivo の状態と、今できる操作が表示されます。
表示される操作は、今の睡眠サポートの進み具合に合わせて変わります。

1. 眠る前は `Sleep now` が表示されます。
2. 眠る準備中は `Not yet` と `Already asleep` が表示されます。
3. 睡眠中は `I am awake` が表示されます。
4. 起きる準備中は `Keep sleeping` と `I am awake` が表示されます。

## 眠る前に操作する

`Sleep now` を押すと、SleepVivo は眠る準備へ切り替わります。
明るさ、色温度、音量は「睡眠サポート」や「睡眠・起床の調整」で設定した内容に沿って変わります。

眠る準備中にまだ起きていたい場合は、`Not yet` を押します。
画面と音は戻り、設定している場合はあとでもう一度眠る準備が始まります。

すでに眠る状態にしたい場合は、`Already asleep` を押します。
SleepVivo は睡眠中の設定へ切り替わります。

## 起きるときに操作する

起きる準備中に、まだ眠りたい場合は `Keep sleeping` を押します。
SleepVivo は睡眠中の設定へ戻ります。

起きた場合は `I am awake` を押します。
起床サポートが完了し、画面と音は起きる方向へ戻ります。

睡眠中に手動で起きる場合も、`I am awake` を押します。

## 明るさ・色温度・音量を調整する

Overlay の下部では、表示されているスライダーをドラッグして調整できます。

1. 「簡易明度」は、全体の明るさを調整します。
2. 高度な明度モードの場合は、「ソフトウェア明度」と「ハードウェア明度」が分かれて表示されます。
3. 色温度制御が使える場合は、温度計のボタンで色温度スライダーへ切り替えられます。
4. 「音量 (基準値%)」は、その睡眠セッション開始時の音量を 100% として調整します。

表示されない項目は、その環境または設定では使えません。

## その他のボタン

Overlay には、環境によって次のボタンが表示されます。

1. 歯車のようなボタン：Overlay から切り替えられる自動化を表示します。
2. コントローラーのボタン：コントローラーやトラッカーの電源操作を表示します。
3. 電源ボタン：シャットダウン手順を開始します。設定がない場合は押せません。
4. クイズのボタン：Research Program のアンケートを開きます。参加中で、回答対象がある場合だけ使えます。

## Research Program のアンケート

Research Program への参加は任意です。
参加していない場合、Overlay のアンケートは開けません。

参加中で回答対象の睡眠セッションがある場合、Overlay にクイズのボタンが表示されます。
アンケートでは、次のような睡眠後の質問に 1 から 5 の数字で回答します。

1. 寝つきやすさ
2. 睡眠への満足度
3. 起きたときのすっきり感

送信されるのは、選んだ数字、質問の種類、回答対象の睡眠セッションを結びつけるための情報です。
氏名、VRChat アカウント、音声、映像、スクリーンショットは送信されません。

詳しくは [Research Program 概要](../research-program/overview.md) と [収集される情報](../research-program/collected-data.md) を確認してください。

## 困ったとき

Overlay が開かない場合は、次を確認してください。

1. SteamVR が起動しているか。
2. 「オーバーレイメニューを有効にする」が ON か。
3. コントローラーバインディングが設定されているか。
4. 「VRChatが実行中の場合のみメニューを開く」を ON にしている場合、VRChat が起動しているか。
5. SteamVR ダッシュボードを開いたままにしていないか。

## Review Checklist

- source files consulted: `U:\dev\SleepVivo\src-overlay-ui\src\routes\dashboard\Overview.svelte`, `U:\dev\SleepVivo\src-overlay-ui\src\routes\dashboard\Survey.svelte`, `U:\dev\SleepVivo\src-overlay-ui\src\routes\dashboard\DeviceControl.svelte`, `U:\dev\SleepVivo\src-overlay-ui\src\lib\components\BrightnessSliders.svelte`, `U:\dev\SleepVivo\src-ui\app\services\sleep-vivo-user-actions.service.ts`, `U:\dev\SleepVivo\src-ui\app\services\sleep-vivo-user-actions-runtime-core.ts`, `U:\dev\SleepVivo\src-ui\app\services\overlay\overlay.service.ts`, `U:\dev\SleepVivo\src-ui\app\views\dashboard-view\views\settings-general-view\settings-general-view.component.html`, `U:\dev\SleepVivo\src-ui\assets\i18n\ja.json`
- assumptions made: Overlay のスクリーンショットは未配置のため、テキストのプレースホルダーとして記載。操作ボタンは現状UIに合わせて英語表記で記載
- items requiring human confirmation: VR Overlay 画面のスクリーンショットを追加する。操作ボタンが日本語化された場合は文言を更新する
