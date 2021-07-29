# Dynamic-css-angular

## Select CSS file dynamically for changing UI appearance.

## Created Service file for common code of to append CSS

```typescript
import { Inject, Injectable } from "@angular/core";
import { DOCUMENT } from "@angular/common";

@Injectable({
  providedIn: "root",
})
export class DynamicStyleService {
  constructor(@Inject(DOCUMENT) private document: Document) {}

  setStyle() {
    if (true) {
      //Condition
      const head = this.document.getElementsByTagName("head")[0];
      const style = this.document.createElement("link");
      style.id = "css-styling";
      style.rel = "stylesheet";
      style.href = "update-styles.css"; //CSS file name
      head.appendChild(style);
    }
  }
}
```

## Call service to apply CSS

```typescript
import { DynamicStyleService } from './services/dynamic-style.service';

@Component({
  selector: 'app-root',
  template: '<router-outlet></router-outlet>',
})

  constructor(
    private dynamicStyleService: DynamicStyleService
  )

  export class AppComponent implements OnInit {

      this.dynamicStyleService.setStyle();
  }

```

## Created CSS file which need to use {update-styles.css}

This CSS file for to change style of Mat-Stepper, button, mat-tab's, custom buttons

```typescript
// For Buttons
.btn-primary {
    color: #fff;
    border-color: rgb(170, 53, 62) !important;
    background-image: linear-gradient(to right, #bd5861, #aa353e) !important;
}

.btn-primary:hover {
    color: #fff;
    // background-color: #eb7a23;
    background-image: linear-gradient(to right, #bd5861, #aa353e) !important;
    border-color: #aa353e;
}

// For Steppers
.mat-step-header .mat-step-icon-selected,
.mat-step-header .mat-step-icon-state-done,
.mat-step-header .mat-step-icon-state-edit {
    //   background-color: #eb7a23 !important;
    background-image: linear-gradient(to right, #bd5861, #aa353e) !important;
}

// For Tabs
.mat-tab-labels .mat-tab-label.mat-tab-label-active {
    // background-image: linear-gradient(to right, #598bff, #36f);
    background-image: linear-gradient(to right, #bd5861, #aa353e) !important;
    color: #fff;
    border-radius: 6px 6px 0 0;
}

.mat-tab-group.mat-primary .mat-tab-list .mat-ink-bar {
    background-image: linear-gradient(to right, #bd5861, #aa353e) !important;
}

.mat-tab-labels .mat-tab-label {
    opacity: 1;
    background-color: #fff;
    color: rgb(170, 53, 62);
    border-radius: 6px 6px 0 0;
    margin: 0 1px;
    border: solid 1px rgb(170, 53, 62);
}

.mat-tab-labels .mat-tab-label:hover {
    background-image: linear-gradient(to right, #bd5861, #aa353e) !important;
    border-radius: 6px 6px 0 0;
    color: #fff;
}

//Custom Buttons
.image-button {
    display: block;
    border-radius: 0px;
    color: #fff;
    box-shadow: 0px 4px 6px 2px rgba(0, 0, 0, 0.2);
    background-image: linear-gradient(to right, #bd5861, #aa353e) !important;
    font-size: 12px;
    cursor: pointer;
}

.image-button:hover {
    background-image: linear-gradient(to right, #bd5861, #aa353e) !important;
}

//Mat-Groups
.mat-button-toggle-checked {
    background-color: #aa353e !important;
    color: #ffffff !important;
}

//Instruction Button
.custom-color {
    color: #aa353e !important;
}

```

## Usage

This can also use to change theme of the UI on dropdown change.
