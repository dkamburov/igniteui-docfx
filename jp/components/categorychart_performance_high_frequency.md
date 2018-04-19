﻿---
title: Category Chart パフォーマンス
_description: Ignite UI for Angular Category Chart コンポーネントは、カテゴリ データを表示するタッチ対応、高いパフォーマンス、軽量なチャート コントロールです。
_keywords: Ignite UI for Angular, データ ビジュアライゼーション, UI コントロール, Angular ウィジェット, web ウィジェット, UI ウィジェット, Angular, ネイティブ Angular コンポーネント スィート, ネイティブ Angular コントロール, ネイティブ Angular コンポーネント ライブラリ, Angular Chart コンポーネント, Angular Category Chart コンポーネント, Angular Chart コントロール, Angular Category Chart コントロール
_language: ja
---
## 高頻度パフォーマンス

igxCategoryChart は、数百万のデータ ポイントに及ぶ大量のデータを処理し、それらを数ミリ秒ごとに更新する機能を備えます。以下のデモはカテゴリ チャート コンポーネントのパフォーマンスを紹介します。

<div class="divider"></div>

### 高頻度でデータを更新するデモ

<div class="sample-container" style="height: 650px">
    <iframe id="category-chart-performance-iframe" src='{environment:demosBaseUrl}/category-chart-high-frequency-sample' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn"   data-iframe-id="category-chart-high-frequency-sample-iframe" data-demos-base-url="{environment:demosBaseUrl}">StackBlitz で開く
    </button>
</div>

<div class="divider--half"></div>

### パフォーマンス最適化

チャートのパフォーマンスに影響を及ぼすチャート機能および Angular 固有の機能があり、アプリケーションでのパフォーマンスを最適化する際に検討する必要があります。

* コンポーネントにバインドするプロパティで大量のデータを保存する場合、`@Component` デコレーターで `changeDetection: ChangeDetectionStrategy.OnPush` を設定します。
     * Angular の各変更検出のサイクルでデータ配列内の変更を確認しないようにする設定です。
* チャートに Angular が自動でデータ変更を通知する代わりに、バインドされたデータが変更された方法をコンポーネントに通知できます。
    * デルタ通知の処理は、Angular が変更検出を実行する際に 100 万のレコードを含む配列のすべての変更を比較するより効果的に実行できます。
    * バインドしたデータの変更をチャートに通知する方法の詳細については、チャートの `notify*` メソッドを参照してください。
* Angular が Debug モードで実行されている場合、特定のブラウザーでパフォーマンスを低下させるオーバーヘッドがあります。実環境パフォーマンスを評価する場合、`--prod` を使用して serve または build してください。
