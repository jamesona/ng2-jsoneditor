# ng2-jsoneditor
___
Simple angular 2 wrapper for [jsoneditor](https://github.com/josdejong/jsoneditor)


# Usage
___
Install with npm
```sh
npm install --save ng2-jsoneditor
```

Import the component
```typescript
import { JsonEditorComponent } from 'ng2-jsoneditor/ng2-jsoneditor'
```

Include it in your module

```typescript
@NgModule({
  declarations: [
    JsonEditorComponent
  ]
})
export default class AppModule {}
```

Add the component to the template 

```html
<div>
  <json-editor [options]="editorOptions" [data]="data"></json-editor >
</div>
```

Create a component to set options and call methods on the jsoneditor
```typescript
import { Component, ViewChild } from '@angular/core';
import { JsonEditorComponent, JsonEditorOptions } from 'ng2-jsoneditor/ng2-jsoneditor';

@Component({
  ...
})
export class DetailComponent {
  public editorOptions: JsonEditorOptions;

  public data: any = {
    ...
  }
  
  @ViewChild(JsonEditorComponent) editor: JsonEditorComponent;
  
  constructor(...) {
    this.editorOptions = new JsonEditorOptions();
  }
  
  public setTreeMode() {
    this.editor.setMode('tree');
  }
}
```

See  jsonmodel's [api](https://github.com/josdejong/jsoneditor/blob/master/docs/api.md) docs for more detailed usage.