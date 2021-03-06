---
title: Financial Chart Component - Native Angular | Ignite UI for Angular
_description: The Ignite UI for Angular Financial Chart component is easily configured to display financial data using a simple and intuitive API, as once the user binds the data, the chart offers multiple ways in which the data can then be visualized and interpreted.
_keywords: Ignite UI for Angular, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components, Native Angular Components Library, Angular Chart, Angular Chart Control, Angular Chart Example, Angular Grid Component, Angular Chart Component, Angular Financial Chart
---
## Financial Chart

The Financial Chart is a charting component that makes it easy to visualize financial data by using a simple and intuitive API. Once the user binds the data, the chart offers multiple ways in which the data can then be visualized and interpreted. There are several display modes for price and volume and a host of financial indicators. The chart also makes use of label formatting to give context to the data.

The financial chart component analyzes and selects data columns - Date/Time column to use for x-axis and Open, High, Low, Close, Volume columns or the first 5 numeric columns for y-axis. Beyond this, the user can specify the chart type to either Bar, Candle, Column, and Line. With its five main visual elements, a toolbar, a prices view, a volume view, an indicators view, and a navigation view, data has become more perceptible.

### Financial Chart Demo

<div class="sample-container" style="height: 550px">
    <iframe id="financial-chart-overview-sample-iframe" src='{environment:demosBaseUrl}/financial-chart-overview-sample' width="100%" height="100%" seamless frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn"   data-iframe-id="financial-chart-overview-sample-iframe" data-demos-base-url="{environment:demosBaseUrl}">View on StackBlitz
    </button>
</div>

<div class="divider--half"></div>

You can explicitly specify the chart type by setting the `chartType` property to one of the following options:

Property|Description
---|---
`bar`|Specifies the bar series with markers at each data point
`candle`|Specifies the candle series
`column`|Specifies the column series
`line`|Specifies the line series
`auto`|Specifies automatic selection of chart type based on Data Adapter which suggest one of above values based names and number of numeric columns in your data. For example, it will suggest `bar` for data items with Open, High, Low, Close columns.

Refer to the [Financial Chart Panes](financialchart_panes.html) topics for  information on other chart panes.

```html
 <igx-financial-chart
    chartType="candle">
 </igx-financial-chart>
```

### Toolbar
A toolbar is displayed at the top of the financial chart. This allows your end users to change various details about the data being displayed, and also displays different panes. The toolbar consists of the following selectors:
- Indicator Type Selector - Allows users to select multiple types of financial indicators. These indicators are displayed below the price pane in their own panes because they do not share the same Y-Axis scale with the prices or other indicators.
- Overlay Type Selector - Allows users to select different types of financial overlays. These overlays are displayed together with the financial prices series because they share the same y-axis scale. There are two types of overlays the `BollingerBands` and `PriceChannel`.
- Trendline Type Selector - Allows users to select different types of trendlines. The trendline is displayed in a trendline layer over the price pane and the volume pane.
- Date Range Selector - Allows users to select different range presets to view the data. Note that some buttons will not be functional if your data range is less 1 year.
- Chart Type Selector - Allows users to select chart types for the financial chart. These are displayed in the price pane.
- Volume Type Selector -  Allows users to view the stock volume data in the Volume Pane. Users can choose between None, Column, Line, and Area chart types.

Also, you can hide the toolbar if you wish to maximize vertical space for the chart panes. The following code show how to hide the toolbar:

```html
 <igx-financial-chart
    isToolbarVisible="false">
 </igx-financial-chart>
```

### Dependencies
The financial chart is exported as an `NgModule`, you need to import the _IgxFinancialChartModule_ inside your `AppModule`:

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

### Usage
Now that the financial chart module is imported, next step is to bind it to data.

In order to create an `igx-financial-chart` control, you must first have data to bind it to. The following code snippet demonstrates how to create a simple data source.

```typescript
let data = [
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

The following code demonstrates how to bind the financial chart to the above data.

```html
 <igx-financial-chart
    [dataSource]="data"
    width="850px"
    height="600px">
 </igx-financial-chart>
```


