# Adding interaction

We respond to an event by surrounding the event name with parentheses ().

Example of an event: `(click)="functionName(param1,param2,...)"`

Define the function in the component.ts file: `functionName(param1: HTMLInputElement, link: HTMLInputElement): boolean { console.log(`text: ${param1.value} and text: ${param2.value}`); return false;}`

Add `#param1` and `param2` to the input tag then pass it as variables to the `functionName()`

This `<input name="label_name" #param1>` tells Angular to bind the tag to the variable _param1_, the # syntax is called _resolve_

`param1 and param2` are two objects of type `HTMLInputElement`

`@HostBinding('attr.class') cssClass = 'row';` the CSS class we intend to apply to the "host" of the given component

The Component _host_ is the _element this component is attached to_

`@HostBinding()` decorator to set properties on the host element which make sure taht the value of the host elements is in sync with the property **_cssClass_**. Import it from `@angular/core`

When you create a new component, you have to import then new component and add it in a declarations in NgModules in the _app.module.ts_

Add the `return false` to fucntion which executes after a click to stop event propagation

A Good practice when writing Angular code is to isolate the data structures we are using from the component code by creating a new file called **classname.model.ts**.

---

export class Article {
title: string;
link: string;
votes: number;

constructor(title: string, link: string, votes?: number) {
this.title = title;
this.link = link;
this.votes = votes || 0;
}
}

---

Optional parameter is define as follow **votes?: number**

---

import the model class as follows in the component `import { ModelName } from './modelFileName.model'`;

Storing reference to prop-name to be our new ModelName class as follows `prop-name: ModelName`

---
