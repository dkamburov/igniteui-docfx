﻿---
title: Financial Chart コンポーネント - ネイティブ Angular | Ignite UI for Angular 
_description: Ignite UI for Angular Financial Chart コンポーネントは簡易な API を使用してファイナンシャル データを表示できます。ユーザーがデータにバインド後にチャートがデータの可視化オプションを複数提供します。
_keywords: Ignite UI for Angular, Angular, ネイティブ Angular コンポーネント スィート, ネイティブ Angular コントロール, ネイティブ Angular コンポーネント, ネイティブ Angular コンポーネント ライブラリ, Angular チャート, Angular チャート コントロール, Angular チャート例, Angular チャート コンポーネント, Angular Financial Chart
_language: ja
---
## ファイナンシャル チャート

Financial Chart は簡易な API を持つファイナンシャル データを可視化するチャート コンポーネントです。ユーザーがデータをバインド後、チャートはデータの可視化オプションを複数提供します。価格および出来高のための複数の表示モードがあり、財務指標がおおあります。チャートにデータ コンテキストを表示するためにラベルの書式設定を使用します。

ファイナンシャル チャート コンポーネントはデータ列を解析して選択します。日/時列を X 軸で使用し、Open、High、Low、Close、Volume 列、または最初の 5 つの数値列を Y 軸で使用します。ユーザーがチャート タイプを棒、ローソク足、柱状、または折れ線に設定できます。主要なビジュアル要素にツールバー、価格ペイン、ボリューム ペイン、インジケーター ペイン、およびナビゲーション ペインがあります。

### Financial Chart デモ

<div class="sample-container" style="height: 550px">
    <iframe id="financial-chart-overview-sample-iframe" src='{environment:demosBaseUrl}/financial-chart-overview-sample' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn"   data-iframe-id="financial-chart-overview-sample-iframe" data-demos-base-url="{environment:demosBaseUrl}">StackBlitz で開く
    </button>
</div>

<div class="divider--half"></div>

`chartType` プロパティを以下のオプションの 1 つに設定してチャート タイプを明示的に指定することもできます。
    
プロパティ|説明
---|---
`bar`|各データ ポイントにマーカーがある棒シリーズを指定します。
`candle`|ローソク足シリーズを指定します。
`column`|柱状シリーズを指定します。
`line`|折れ線シリーズを指定します。
`auto`|データ アダプターからの提案に基づいてチャート タイプの自動選択を指定します。

### ツールバー

ファイナンシャル チャートの上側にツールバーが表示されます。チャートで表示されるデータの詳細を変更でき、複数のペインの表示もできます。ツールバーには次のセレクターが含まれます:

- インジケーター タイプ セレクター - 財務指標のタイプを選択できます。これらのインジケーターは同じ Y 軸を共有しないため、価格ペインの下のインジケーター ペインに表示されます。
- オーバーレイ タイプ - 財務オーバーレイのタイプを選択できます。これらのオーバーレイは、同じ Y 軸スケールを共有する財務物価シリーズの前に表示されます。オーバーレイには、BollingerBands および PriceChannel の 2 種類があります。
- トレンドライン タイプ セレクター - トレンドラインのタイプを選択できます。トレンドラインは価格ペインおよびボリューム ペインのトレンドライン レイヤーで表示されます。
- 日付範囲セレクター - データを表示するために定義済みの範囲を選択できます。
- チャート タイプ セレクター - ファイナンシャル チャートのチャート タイプを選択できます。これは価格ペインで表示されます。
- ボリューム タイプ セレクター - ボリューム ペインで出来高を表示します。None、Column、Line、および Area チャート タイプから選択できます。

### 依存関係

ファイナンシャル チャートが `NgModule` としてエクスポートされるため、アプリケーションで `AppModule` に `IgxFinancialChartModule` をインポートする必要があります。

```typescript
// app.module.ts
import {IgxFinancialChartModule} from '@infragistics/igniteui-angular-charts/ES5/ig-financialchart-module'

@NgModule({
    imports: [
        ...
        IgxFinancialChartModule,
        ...
    ]
})
export class AppModule {}
```

<div class="divider--half"></div>

### 使用方法

ファイナンシャル チャート モジュールをインポートした後、チャートをデータにバインドします。

ファイナンシャル チャート コントロールを作成するには、はじめにデータをバインドする必要があります。以下のコード スニペットは、シンプルなデータソースを作成する方法を示します。

```typescript

var data = [
	{ time: new Date(2013, 1, 1), open: 268.93, high: 268.93, low: 262.80, close: 265.00, volume: 6118146 },
	{ time: new Date(2013, 1, 4), open: 262.78, high: 264.68, low: 259.07, close: 259.98, volume: 3723793 },
	{ time: new Date(2013, 1, 5), open: 262.00, high: 268.03, low: 261.46, close: 266.89, volume: 4013780 },
	{ time: new Date(2013, 1, 6), open: 265.16, high: 266.89, low: 261.11, close: 262.22, volume: 2772204 },
	{ time: new Date(2013, 1, 7), open: 264.10, high: 264.10, low: 255.11, close: 260.23, volume: 3977065 },
	{ time: new Date(2013, 1, 8), open: 261.40, high: 265.25, low: 260.56, close: 261.95, volume: 3879628 },
	{ time: new Date(2013, 1, 11), open: 263.20, high: 263.25, low: 256.60, close: 257.21, volume: 3407457 },
	{ time: new Date(2013, 1, 12), open: 259.19, high: 260.16, low: 257.00, close: 258.70, volume: 2944730 },
	{ time: new Date(2013, 1, 13), open: 261.53, high: 269.96, low: 260.30, close: 269.47, volume: 5295786 },
	{ time: new Date(2013, 1, 14), open: 267.37, high: 270.65, low: 265.40, close: 269.24, volume: 3464080 },
	{ time: new Date(2013, 1, 15), open: 267.63, high: 268.92, low: 263.11, close: 265.09, volume: 3981233 }
];

```

以下のコードはファイナンシャル チャートを上記のデータにバインドします。

```html 
 <igx-financial-chart [dataSource]="data" 
    width="850px"
    height="600px">
 </igx-financial-chart>
```


