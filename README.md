[![Published on NPM](https://img.shields.io/npm/v/@polymer/paper-drawer-panel.svg)](https://www.npmjs.com/package/@polymer/paper-drawer-panel)
[![Build status](https://travis-ci.org/PolymerElements/paper-drawer-panel.svg?branch=master)](https://travis-ci.org/PolymerElements/paper-drawer-panel)
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://webcomponents.org/element/@polymer/paper-drawer-panel)

## &lt;paper-drawer-panel&gt;

**This element has been deprecated in favor of [app-layout](https://github.com/PolymerElements/app-layout).**

`paper-drawer-panel` contains a drawer panel and a main panel. The drawer
and the main panel are side-by-side with drawer on the left. When the browser
window size is smaller than the `responsiveWidth`, `paper-drawer-panel`
changes to narrow layout. In narrow layout, the drawer will be stacked on top
of the main panel. The drawer will slide in/out to hide/reveal the main
panel.

Use the attribute `drawer` to indicate that the element is the drawer panel and
`main` to indicate that the element is the main panel.

Example:

    <paper-drawer-panel>
      <div slot="drawer"> Drawer panel... </div>
      <div slot="main"> Main panel... </div>
    </paper-drawer-panel>

The drawer and the main panels are not scrollable. You can set CSS overflow
property on the elements to make them scrollable or use `paper-header-panel`.

Example:

    <paper-drawer-panel>
      <paper-header-panel slot="drawer">
        <paper-toolbar></paper-toolbar>
        <div> Drawer content... </div>
      </paper-header-panel>
      <paper-header-panel slot="main">
        <paper-toolbar></paper-toolbar>
        <div> Main content... </div>
      </paper-header-panel>
    </paper-drawer-panel>

To position the drawer to the right, add `right-drawer` attribute.

    <paper-drawer-panel right-drawer>
      <div slot="drawer"> Drawer panel... </div>
      <div slot="main"> Main panel... </div>
    </paper-drawer-panel>

### Styling

To change the main container:

    paper-drawer-panel {
      --paper-drawer-panel-main-container: {
        background-color: gray;
      };
    }

To change the drawer container when it's in the left side:

    paper-drawer-panel {
      --paper-drawer-panel-left-drawer-container: {
        background-color: white;
      };
    }

To change the drawer container when it's in the right side:

    paper-drawer-panel {
      --paper-drawer-panel-right-drawer-container: {
        background-color: white;
      };
    }

To customize the scrim:

    paper-drawer-panel {
      --paper-drawer-panel-scrim: {
        background-color: red;
      };
    }

The following custom properties and mixins are available for styling:

Custom property | Description | Default
----------------|-------------|----------
`--paper-drawer-panel-scrim-opacity` | Scrim opacity | 1
`--paper-drawer-panel-drawer-container` | Mixin applied to drawer container | {}
`--paper-drawer-panel-left-drawer-container` | Mixin applied to container when it's in the left side | {}
`--paper-drawer-panel-main-container` | Mixin applied to main container | {}
`--paper-drawer-panel-right-drawer-container` | Mixin applied to container when it's in the right side | {}
`--paper-drawer-panel-scrim` | Mixin applied to scrim | {}

See: [Documentation](https://www.webcomponents.org/element/@polymer/paper-drawer-panel),
  [Demo](https://www.webcomponents.org/element/@polymer/paper-drawer-panel/demo/demo/index.html).

## Usage

### Installation
```
npm install --save @polymer/paper-drawer-panel
```

### In an html file
```html
<html>
  <head>
    <script type="module">
      import '@polymer/paper-drawer-panel/paper-drawer-panel.js';
    </script>
  </head>
  <body>
    <paper-drawer-panel>
      <div slot="drawer"> Drawer panel... </div>
      <div slot="main"> Main panel... </div>
    </paper-drawer-panel>
  </body>
</html>
```
### In a Polymer 3 element
```js
import {PolymerElement, html} from '@polymer/polymer';
import '@polymer/paper-drawer-panel/paper-drawer-panel.js';

class SampleElement extends PolymerElement {
  static get template() {
    return html`
      <paper-drawer-panel>
        <div slot="drawer"> Drawer panel... </div>
        <div slot="main"> Main panel... </div>
      </paper-drawer-panel>
    `;
  }
}
customElements.define('sample-element', SampleElement);
```

## Contributing
If you want to send a PR to this element, here are
the instructions for running the tests and demo locally:

### Installation
```sh
git clone https://github.com/PolymerElements/paper-drawer-panel
cd paper-drawer-panel
npm install
npm install -g polymer-cli
```

### Running the demo locally
```sh
polymer serve --npm
open http://127.0.0.1:<port>/demo/
```

### Running the tests
```sh
polymer test --npm
```
