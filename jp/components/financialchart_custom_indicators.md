﻿---
title: Financial Chart - カスタム インジケーター
_description: Ignite UI for Angular Financial Chart コンポーネントは簡易な API を使用してファイナンシャル データを表示できます。ユーザーがデータにバインド後にチャートがデータの可視化オプションを複数提供します。
_keywords: Ignite UI for Angular, Angular, ネイティブ Angular コンポーネント スィート, ネイティブ Angular コントロール, ネイティブ Angular コンポーネント, ネイティブ Angular コンポーネント ライブラリ, Angular チャート, Angular チャート コントロール, Angular チャート例, Angular チャート コンポーネント, Angular Financial Chart
_language: ja
---
## カスタム インジケーター

igxFinancialChart コンポーネントでは、インジケーター ペインに表示するカスタム財務指標を定義できます。

### カスタム インジケーター デモ

<div class="sample-container" style="height: 550px">
    <iframe id="financial-chart-custom-indicators-iframe" src='{environment:demosBaseUrl}/financial-chart-custom-indicators' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn"   data-iframe-id="financial-chart-custom-indicators-iframe" data-demos-base-url="{environment:demosBaseUrl}">StackBlitz で開く
    </button>
</div>

<div class="divider--half"></div>

igxFinancialChart でカスタム財務指標を有効にするには、`CustomIndicatorNames` プロパティに名前を追加し、`ApplyCustomIndicators` イベントで計算を実行します。

以下のコード例は、2 つのカスタム インジケーターを設定して計算する方法を紹介します。単純移動平均 (SMA) およびランダム値を表示するインジケーターを使用します。
