---
sidebar_label: 'ion-router-outlet'
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# ion-router-outlet

Router outlet is a component used in routing within an Angular or Vue app. It behaves in a similar way to Angular's built-in router outlet component and Vue's router view component, but contains the logic for providing a stacked navigation, and animating views in and out.

> Note: this component should only be used with Angular and Vue projects. For vanilla or Stencil JavaScript projects, use [`ion-router`](router.md) and [`ion-route`](route.md).

Although router outlet has methods for navigating around, it's recommended to use the navigation methods in your framework's router.

## Life Cycle Hooks

Routes rendered in a Router Outlet have access to specific Ionic events that are wired up to animations

| Event Name         | Trigger                                                            |
| ------------------ | ------------------------------------------------------------------ |
| `ionViewWillEnter` | Fired when the component routing to is about to animate into view. |
| `ionViewDidEnter`  | Fired when the component routing to has finished animating.        |
| `ionViewWillLeave` | Fired when the component routing from is about to animate.         |
| `ionViewDidLeave`  | Fired when the component routing to has finished animating.        |

These event tie into Ionic's animation system and can be used to coordinate parts of your app when a Components is done with its animation. These events are not a replacement for your framework's own event system, but an addition.

For handling Router Guards, the older `ionViewCanEnter` and `ionViewCanLeave` have been replaced with their framework specific equivalent. For Angular, there are [Router Guards](https://angular.io/guide/router#milestone-5-route-guards).

## Properties

### animated

|                 |                                                                           |
| --------------- | ------------------------------------------------------------------------- |
| **Description** | If `true`, the router-outlet should animate the transition of components. |
| **Attribute**   | `animated`                                                                |
| **Type**        | `boolean`                                                                 |
| **Default**     | `true`                                                                    |

### animation

|                 |                                                                                                                                                                                                     |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Description** | By default `ion-nav` animates transition between pages based in the mode (ios or material design).<br />However, this property allows to create custom transition using `AnimateBuilder` functions. |
| **Attribute**   | `undefined`                                                                                                                                                                                         |
| **Type**        | `((baseEl: any, opts?: any) => Animation) \| undefined`                                                                                                                                             |
| **Default**     | `undefined`                                                                                                                                                                                         |

### mode

|                 |                                                   |
| --------------- | ------------------------------------------------- |
| **Description** | The mode determines which platform styles to use. |
| **Attribute**   | `mode`                                            |
| **Type**        | `"ios" \| "md"`                                   |
| **Default**     | `getIonMode(this)`                                |
