---
title: Tabs Component - Native Angular | Ignite UI for Angular 
_description: The Ignite UI for Angular Tabs component places tabs at the top and allows for scrolling when there are multiple tab items on the screen. 
_keywords: Ignite UI for Angular, UI controls, Angular widgets, web widgets, UI widgets, Angular, Native Angular Components Suite, Native Angular Components, Native Angular Controls, Native Angular Components Library, Angular Tabs component, Angular Tabs controls, Angular Tabs
---

## Tabs

The tabs component in Ignite UI for Angular is used to organize or switch between similar data sets. It functions as a wrapper for `igx-tab-item` and `igx-tabs-group`, as these respectively represent the container for the data and the tab header. The tabs component also places tabs at the top and allows for scrolling when there are multiple tab items on the screen.

### Tabs Demo
<div class="sample-container loading" style="height: 250px; width: 600px;">
    <iframe id="tabs-sample-0" frameborder="0" seamless width="100%" height="100%" src="{environment:demosBaseUrl}/tabs-sample-3" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn" data-iframe-id="tabs-sample-0" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>
<div class="divider--half"></div>

> [!NOTE]
> To start using Ignite UI for Angular components in your own projects, make sure you have configured all necessary dependencies and have performed the proper setup of your project. You can learn how to do this in the [**installation**](https://www.infragistics.com/products/ignite-ui-angular/getting-started#installation) topic.

### Usage

To get started with the Ignite UI for Angular Tabs component, let's first import the **IgxTabsModule** in the **app.module.ts** file.

```typescript
// app.module.ts

...
import { IgxTabsModule } from 'igniteui-angular/main';

@NgModule({
    ...
    imports: [..., IgxTabsModule],
    ...
})
export class AppModule {}
```

Then, specify three tabs groups with `label` and content.

```html
<igx-tabs>
  <igx-tabs-group label="Tab 1">This is Tab 1 content.</igx-tabs-group>
  <igx-tabs-group label="Tab 2">This is Tab 2 content.</igx-tabs-group>
  <igx-tabs-group label="Tab 3">This is Tab 3 content.</igx-tabs-group>
  <igx-tabs-group label="Tab 4">This is Tab 4 content.</igx-tabs-group>
  <igx-tabs-group label="Tab 5">This is Tab 5 content.</igx-tabs-group>
</igx-tabs>
```

If the sample is configured properly, the final result should look like that:

<div class="sample-container loading" style="height: 200px; width: 600px; border: 1px solid gray;">
    <iframe id="tabs-sample-1-iframe" src='{environment:demosBaseUrl}/tabs-sample-1' width="100%" height="100%" seamless
        frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
<button data-localize="stackblitz" class="stackblitz-btn" data-iframe-id="tabs-sample-1-iframe"
    data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

<div class="divider"></div>

### Tabs Types
There are two types of tabs. Set the `tabsType` input to choose between fixed and content-fit tabs.
- **Content-fit tabs** (default): the width of the tab header depends on the content (label, icon, both) and all tabs have equal padding.
Nevertheless what type of tabs you have choose, the tab header width is limited by the specified min and max width. 
- **Fixed tabs**: all tab headers are with equal width and fit in the tabs component. If the provided space is not enough for all items, scroll buttons are displayed.

```html
<div class="items-wrapper__item items-wrapper__item-small items-wrapper__item--blue">
  <h4 class="sample-title">CONTENT-FIT TABS</h4>
  <igx-navbar title="Contacts" actionButtonIcon="menu">
    <igx-icon name="search"></igx-icon>
    <igx-icon name="more_vert"></igx-icon>
  </igx-navbar>
  <igx-tabs>
    <igx-tabs-group label="HOME">Home content.</igx-tabs-group>
    <igx-tabs-group label="RECENT CONTACTS">Recent contacts list.</igx-tabs-group>
    <igx-tabs-group label="MORE INFORMATION ABOUT SELECTED CONTACT">More detailed contact information.</igx-tabs-group>
  </igx-tabs>
</div>

<div class="items-wrapper__item items-wrapper__item-small items-wrapper__item--blue">
  <h4 class="sample-title">FIXED TABS</h4>
  <igx-navbar title="Contacts" actionButtonIcon="menu">
    <igx-icon name="search"></igx-icon>
    <igx-icon name="more_vert"></igx-icon>
  </igx-navbar>
  <igx-tabs tabsType="fixed">
    <igx-tabs-group label="HOME">Home content.</igx-tabs-group>
    <igx-tabs-group label="RECENT CONTACTS">Recent contacts list.</igx-tabs-group>
    <igx-tabs-group label="MORE INFORMATION ABOUT SELECTED CONTACT">More detailed contact information.</igx-tabs-group>
  </igx-tabs>
</div>
```

<div class="sample-container loading" style="height: 450px; width: 800px;">
    <iframe id="tabs-sample-2-iframe" src='{environment:demosBaseUrl}/tabs-sample-2' width="100%" height="100%" seamless
        frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
<button data-localize="stackblitz" class="stackblitz-btn" data-iframe-id="tabs-sample-2-iframe"
    data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

<div class="divider"></div>

### Customizing Tabs

Let's modify the tabs and make them more appealing by including icons. The Tabs component is compatible with the Material Design
[**Icons**](https://material.io/icons/) so it will be very easy to adopt them in your application.

First add the Material+Icons import in your 'styles.css' file in the main application folder.

```css
// styles.css

...
@import url('https://fonts.googleapis.com/icon?family=Material+Icons');
...
```

```html
<igx-tabs>
  <igx-tabs-group label="MY ALBUMS" icon="library_music">
    <div style="margin: 15px">
      <igx-card>
        <igx-card-header class="compact">
          <igx-avatar src="assets/images/card/avatars/alicia_keys.jpg" roundShape="true"></igx-avatar>
          <div class="igx-card-header__tgroup">
            <h3 class="igx-card-header__title--small">HERE</h3>
            <h5 class="igx-card-header__subtitle">by Alicia Keys</h5>
          </div>
        </igx-card-header>
        <igx-card-actions>
          <div class="igx-card-actions__bgroup">
            <button igxButton igxRipple>PLAY</button>
          </div>
        </igx-card-actions>
      </igx-card>
    </div>
  </igx-tabs-group>
  <igx-tabs-group label="FAVOURITES" icon="favorite">
    <div style="margin: 15px">
      <h5 class="igx-card-header__subtitle">Add your favourite songs here.</h5>
    </div>
  </igx-tabs-group>
  <igx-tabs-group label="INFO" icon="info">
    <div style="margin: 15px">
      <h5 class="igx-card-header__subtitle">"Here" is the sixth studio album by American singer and songwriter Alicia Keys.</h5>
    </div>
  </igx-tabs-group>
</igx-tabs>
```

If the sample is configured properly, the tabs should look like the following example:

<div class="sample-container loading" style="height: 250px; width: 600px;">
    <iframe id="tabs-sample-3-iframe" src='{environment:demosBaseUrl}/tabs-sample-3' width="100%" height="100%" seamless
        frameBorder="0" onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
<button data-localize="stackblitz" class="stackblitz-btn" data-iframe-id="tabs-sample-3-iframe"
    data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

<div class="divider--half"></div>

If changing the tabs' labels and icons is not enough, you can also create your own template for each tab header.

```html
<igx-tabs>
    <igx-tabs-group>
        <ng-template igxTab>
            <div>
                <!-- your custom tab content goes here -->
            </div>
        </ng-template>
        <h1>Tab content</h1>
    </igx-tabs-group>
</igx-tabs>
```

<div class="divider"></div>

### API Summary

The following tables summarize some of the useful Tabs component inputs and outputs.

#### Inputs

The following input is available in the **igx-tabs** component:

| Name | Type | Description |
| :--- | :--- | :--- |
| `tabsType` | TabsType | Defines the tab header sizing mode - `contentfit` (default) or `fixed`. |


The following inputs are available in the **igx-tabs-group** component:

| Name | Type | Description |
| :--- | :--- | :--- |
| `label` | String | Defines the label of the associated tab header. |
| `icon` | String | Defines the icon of the associated tab header. |

<div class="divider"></div>

#### Outputs

The following outputs are available on the **igx-tabs** component:
| Name | Type | Description |
| :--- | :--- | :--- |
| `onTabItemSelected` | EventEmitter | Emits an event when a tab item is selected. |
| `onTabItemDeselected` | EventEmitter | Emits an event when a tab item is deselected. |

<div class="divider"></div>

#### Getters

The following getters are available in the **igx-tabs** component:
| Name | Type | Description |
| :--- | :--- | :--- |
| `tabs` | QueryList | Provides an observable collection of all IgxTabItemComponent-s. |
| `groups` | QueryList | Provides an observable collection of all IgxTabsGroupComponent-s. |
| `selectedIndex` | number | Gets the index of selected tab item. |
| `selectedTabItem` | IgxTabItemComponent | Gets the selected IgxTabItemComponent based on `selectedIndex`. |

<div class="divider--half"></div>

The following getters are available on the **igx-tabs-group** component:
| Name | Type | Description |
| :--- | :--- | :--- |
| `isDisabled` | boolean | Gets whether the group is disabled. |
| `index` | number | Gets the group index in the groups collection. |
| `relatedTab` | IgxTabItemComponent | Gets the tab associated with the group. |

<div class="divider--half"></div>

The following getters are available on the **igx-tab-item** component:
| Name | Type | Description |
| :--- | :--- | :--- |
| `isDisabled` | boolean | Gets whether the tab is disabled. |
| `isSelected` | boolean | Gets whether the tab is selected. |
| `index` | number | Gets the index of the tab in the tab collection. |
| `relatedGroup` | IgxTabsGroupComponent | Gets the group associated with the tab. |

<div class="divider"></div>

### Additional Resources

<div class="divider--half"></div>
Our community is active and always welcoming to new ideas.

* [Ignite UI for Angular **Forums**](https://www.infragistics.com/community/forums/f/ignite-ui-for-angular)
* [Ignite UI for Angular **GitHub**](https://github.com/IgniteUI/igniteui-angular)
