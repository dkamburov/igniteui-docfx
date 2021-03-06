---
title: Card Component
_description: Present users with dashboards and engaging text, images, icons or buttons as an entry point for detailed information with Ignite UI for Angular Card component.
_keywords: Ignite UI for Angular, UI controls, Angular widgets, web widgets, UI widgets, Angular, Native Angular Components Suite, Native Angular Controls, Native Angular Components Library, Angular Card component, Angular Card controls
---

##Card
<p class="highlight">The Ignite UI for Angular Card component displays text, images, icons, and buttons in a visually rich presentation that can serve as an entry point to more detailed information. Cards can be used to create a multimedia dashboard. The Card component supports pagination using the same component as the Ignite UI for Angular Grid, with some custom coding required.</p>
<div class="divider"></div>

###Card Demo
<div class="sample-container loading" style="height: 1200px">
    <iframe id="card-sample-iframe" seamless width="100%" height="100%" frameborder="0" src="{environment:demosBaseUrl}/card"
        onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn" data-iframe-id="card-sample-iframe"
        data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>
<div class="divider--half"></div>

###Usage
Cards allow you to easily display content composed of different types of objects or similar objects whose size and supported actions can vary.

####Getting Started
To get started with the Ignite UI for Angular Card, let's first import the **IgxCardModule** inside our **app.module.ts** file:

```typescript
// app.module.ts
...
import { IgxCardModule } from 'igniteui-angular/main';

@NgModule({
    ...
    imports: [..., IgxCardModule],
    ...
})
export class AppModule {}
```

Then in the template of our info card component we can add the following code to display a basic card with a header area and brief text content.

```html
<!--infocard.component.html>-->

<igx-card>
  <igx-card-header>
    <h3 class="igx-card-header__title">Rupert Stadler</h3>
    <h5 class="igx-card-header__subtitle">Audi AG</h5>
  </igx-card-header>
  <igx-card-content>
    <p class="igx-card-content__text">Rupert Stadler (born 17 March 1963 in Titting, Germany) is a German business executive and chairman of the Vorstand (CEO) of Audi AG.</p>
  </igx-card-content>
</igx-card>
```

If all went well, you should see the following card in your browser:
<div class="sample-container" style="height: 300px">
    <iframe id="card-sample-1-iframe" src='{environment:demosBaseUrl}/card-sample-1'
        width="100%" height="100%" seamless frameBorder="0"  onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn" data-iframe-id="card-sample-1-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

####Adding Avatar and Images

Yes, Rupert Stadler is popular, but maybe we want to make his card a bit more interesting. We can add a nice picture avatar to the left of his name and a larger Audi TT image. To do that let's grab the [**IgxAvatar**](https://www.infragistics.com/products/ignite-ui-angular/angular/components/avatar.html) module and import it in our **app.module.ts** file.
```typescript
// app.module.ts

...
import {
    IgxCardModule,
    IgxAvatarModule
} from 'igniteui-angular/main';

@NgModule({
    ...
    imports: [..., IgxAvatarModule],
})
export class AppModule {}
```

Next, we need to update the template for our card to show a round-shaped avatar and the actual car:

```html
<!--infocard.component.html>-->

<igx-card>
    <igx-card-header class="compact">
        <igx-avatar src="assets/images/card/avatars/rupert_stadler.jpg" roundShape="true"></igx-avatar>
        <div class="igx-card-header__tgroup">
            <h3 class="igx-card-header__title--small">Rupert Stadler</h3>
            <h5 class="igx-card-header__subtitle">Audi AG</h5>
        </div>
    </igx-card-header>
    <div style="overflow: hidden">
        <img width="100%" height="100%" src="assets/images/card/media/audi_tt.jpg">
    </div>
    <igx-card-content>
      <p class="igx-card-content__text">Rupert Stadler (born 17 March 1963 in Titting, Germany) is a German business executive and chairman of the Vorstand (CEO) of Audi AG.</p>
    </igx-card-content>
</igx-card>
```

At this point the card should look similar to the following:
<div class="sample-container" style="height: 480px">
    <iframe id="card-sample-2-iframe" src='{environment:demosBaseUrl}/card-sample-2' width="100%" height="100%" seamless frameBorder="0"  onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn" data-iframe-id="card-sample-2-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

####Adding Actions

Now, we have a rich and very informative card, but it does seem like it is missing something, right? The good news is we can use some of our other components to enrich the experience and add some functionality.
Let's put a few options to directly access social media from within the card. To do that we will grab two other modules - the [**IgxIcon**](https://www.infragistics.com/products/ignite-ui-angular/angular/components/icon.html) and the [**IgxButton**](https://www.infragistics.com/products/ignite-ui-angular/angular/components/button.html), and import them in our **app.module.ts** file.

```typescript
// app.module.ts

...
import {
    IgxCardModule,
    IgxAvatarModule,
    IgxIconModule,
    IgxButtonModule
} from 'igniteui-angular/main';

@NgModule({
    ...
    imports: [..., IgxIconModule, IgxButtonModule],
})
export class AppModule {}
```

Next, we need to update the template for our card to show these action buttons:

```html
<!--infocard.component.html>-->

<igx-card>
    <igx-card-header class="compact">
        <igx-avatar src="assets/images/card/avatars/rupert_stadler.jpg" roundShape="true"></igx-avatar>
        <div class="igx-card-header__tgroup">
            <h3 class="igx-card-header__title--small">Rupert Stadler</h3>
            <h5 class="igx-card-header__subtitle">Audi AG</h5>
        </div>
    </igx-card-header>
    <div style="overflow: hidden">
        <img width="100%" height="100%" src="assets/images/card/media/audi_tt.jpg">
    </div>
    <igx-card-actions >
        <div class="igx-card-actions__igroup--start">
            <span igxButton="icon" igxRipple igxRippleCentered="true" *ngFor="let icon of icons">
                <igx-icon fontSet="material" [name]="icon"></igx-icon>
            </span>
        </div>
        <button igxButton igxRipple >Follow</button>
    </igx-card-actions>
</igx-card>
```

We added two icons from the official [**material icons set**](https://material.io/icons/) by setting **igx-icon** component's fontSet property to "material". The list of these two icons is defined in our **infocard.component.ts** file as follows:

```typescript
// infocard.comoponent.ts

public icons = ['add', 'star'];
```

Easy, right? Let's see how it turned out in the browser:

<div class="sample-container loading" style="height: 400px">
    <iframe id="card-sample-3-iframe" seamless width="100%" height="100%" frameborder="0" src="{environment:demosBaseUrl}/card-sample-3"
        onload="onSampleIframeContentLoaded(this);"></iframe>
</div>
<div>
    <button data-localize="stackblitz" class="stackblitz-btn"
        data-iframe-id="card-sample-3-iframe" data-demos-base-url="{environment:demosBaseUrl}">view on stackblitz</button>
</div>

<div class="divider--half"></div>

<!--### API Summary-->
#### Styles
The following built-in CSS classes helped us achieve this card layout:
| Name | Description |
| :--- | :--- |
| `igx-card-header` | Makes the header a flexible container which stacks its child items in a row from left to right and wraps them if necessary. Each item is centered and occupies the whole width of the container which results into displaying the title and subtitle one above the other. |
| `igx-card-header__title` | Extends the header element class with margin, color and font-size values specific to title elements. |
| `igx-card-header__subtitle` | Extends the header element class with margin, color and font-size values specific to subtitle elements. |
| `igx-card-content` | Makes the content area a flexible container which stacks its child items in a row from left to right and wraps them if necessary. |
| `igx-card-content__text` | Extends the content element class with margin, color and font-size values specific to text elements. |
| `igx-card-actions__igroup` | Makes the group a flexible container with a specific max-height, which stacks its child items in a row but does not wrap them. All items are of equal size and color, and do not shrink during resizing. |
| `igx-card-actions__igroup--start` | Aligns the items to the left. |


####Summary
In this article we covered a lot of ground with the card component. First, we created a very simple card with text content only. Then added some images to make the card a bit more appealing. Finally, we used some additional Ignite UI for Angular components inside our card, like avatars, buttons and icons, to enrich the experience and add some functionality. The card component is capable of displaying more different layouts worth exploring in the Card Demo in the beginning of this article.

<div class="divider"></div>
###Additional Resources

<div class="divider--half"></div>
Our community is active and always welcoming to new ideas.

* [Ignite UI for Angular **Forums**](https://www.infragistics.com/community/forums/f/ignite-ui-for-angular)
* [Ignite UI for Angular **GitHub**](https://github.com/IgniteUI/igniteui-angular)
