---
title: Input Groups Component - Native Angular | Ignite UI for Angular
_description: The Input Groups component in Ignite UI for Angular allows for easy-to-use and aesthetic forms, simplicity with inputting data, and provides mitigation for handling validation and errors.
_keywords: Ignite UI for Angular, UI controls, Angular widgets, web widgets, UI widgets, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components Library, Native Angular Components, Angular Label components, Angular Label controls, Angular Input components, Angular Input controls, Input component, Input control, Label component, Label control, Angular Input Group components, Angular Input Group controls, Angular Input directive, Angular Label directive, Angular Forms, Angular Reactive Forms, Angular Form Validation
---

## Input Group

Input groups in the Ignite UI for Angular controls allow developers to create easy-to-use and aesthetic forms. The user experiences simplicity with inputting data, and the inputs also provide mitigation for handling validation and errors.

### Input Group Demo
<div class="sample-container" style="height:600px">
<iframe id="input-group-sample-6-frame" src='{environment:demosBaseUrl}/input-group-sample-6' width="100%" height="100%" seamless frameBorder="0"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn" data-iframe-id="input-group-sample-6-frame" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>
<div class="divider--half"></div>

### Usage
The default styling of the Input Group component as well as its complimentary directives follow the text fields specification in the Material Design
[**guidelines**](https://material.io/guidelines/components/text-fields.html).

To get started with the Ignite UI for Angular Input Group, Input, Label, Prefix, Suffix and Hint let's first import the **IgxInputGroup** in our **app.module.ts** file:

```typescript
// app.module.ts

...
import { IgxInputGroup } from 'igniteui-angular/main';

@NgModule({
    ...
    imports: [..., IgxInputGroup],
    ...
})
export class AppModule {}
```

> [!NOTE]
> To use any of the directives `igxInput`, `igxLabel`, `igxPrefix`, `igxSuffix` or `igxHint`, you have to wrap them in an `<igx-input-group>` container.

### Label & Input
You can read about the `igxLabel` and `igxInput` directives as well as their validation, data binding and API in a separate topic [here](label_input.md).

### Prefix & Suffix
If you want to have an input prefix or suffix, you can use Ignite UI for Angular Prefix or Suffix. Both directives can contain html elements, strings, icons or even other components. Let's add a new input field with string **prefix** (`+359`) and igxIcon **suffix** (`<igx-icon name="phone"></igx-icon>`):

```html
<igx-input-group>
    <igx-prefix>+359</igx-prefix>
    <label igxLabel for="phone">Phone</label>
    <input igxInput name="phone" type="text" [(ngModel)]="user.phone" />
    <igx-suffix>
        <igx-icon name="phone"></igx-icon>
    </igx-suffix>
</igx-input-group>
```

Here is how the sample looks:
<div class="sample-container" style="height:100px">
<iframe id="input-group-sample-3-frame" src='{environment:demosBaseUrl}/input-group-sample-3' width="100%" height="100%" seamless frameBorder="0"></iframe>
</div>
<div class="divider--half"></div>

### Hints
Ignite UI for Angular Hint provides a helper text placed below the input. The hint can be placed at the start or at the end of the input. The position of the `igxHint` can be set using the `position` property. Let's add a hint to our phone input:

```html
<igx-input-group>
    <igx-prefix>+359</igx-prefix>
    <label igxLabel for="phone">Phone</label>
    <input igxInput name="phone" type="text" [(ngModel)]="user.phone" />
    <igx-suffix>
        <igx-icon name="phone"></igx-icon>
    </igx-suffix>
    <igx-hint position="start">Ex.: +359 888 123 456</igx-hint>
</igx-input-group>
```

This is how the phone field with hint looks:
<div class="sample-container" style="height:110px">
<iframe id="input-group-sample-4-frame" src='{environment:demosBaseUrl}/input-group-sample-4' width="100%" height="100%" seamless frameBorder="0"></iframe>
</div>
<div class="divider--half"></div>

### Styling
Our inputs could be styled differently by using the `type` property of the `igxInputGroup` component. Currently we support four different ways of styling: line (the default one), box, border and search. This is how they look:

<div class="sample-container" style="height:520px">
<iframe id="input-group-sample-5-frame" src='{environment:demosBaseUrl}/input-group-sample-5' width="100%" height="100%" seamless frameBorder="0"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn" data-iframe-id="input-group-sample-5-frame" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>
<div class="divider--half"></div>

## Input Group API

### Inputs

|Name|Type|Description|
|--- |--- |--- |
|`type`|string|How the input will be styled. The allowed values are `line`, `box`, `border` and `search`. The default is `line`.|
<div class="divider--half"></div>

### Methods

|Signature|Description|
|--- |--- |
|`isTypeLine()`|Whether the `igxInputGroup` type is line.|
|`isTypeBox()`|Whether the `igxInputGroup` type is box.|
|`isTypeBorder()`|Whether the `igxInputGroup` type is border.|
|`isTypeSearch()`|Whether the `igxInputGroup` type is search.|
<div class="divider--half"></div>

## Hint API

### Inputs

|Name|Type|Description|
|--- |--- |--- |
|`position`|string|Where the hint will be placed. The allowed values are `start` and `end`. The default value is `start`.|
<div class="divider--half"></div>

## Additional Resources
Related topics:

* [Label & Input](label_input.md)
<div class="divider--half"></div>

Our community is active and always welcoming to new ideas.

* [Ignite UI for Angular **Forums**](https://www.infragistics.com/community/forums/f/ignite-ui-for-angular)
* [Ignite UI for Angular **GitHub**](https://github.com/IgniteUI/igniteui-angular)
