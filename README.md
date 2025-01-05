# Open All Details
Custom button element to open/close grouped `<details>` elements intuitively. [Demo (TBA)]

`OpenAll.astro` is an [Astro component](https://docs.astro.build/en/basics/astro-components/) that inserts a custom element containing an unstyled button that will open (or close) all `<details>` elements specified by the `selector` prop. The script takes into account whether the `<details>` elements started out opened or closed since the button was last pressed and will know to open/close them all if they're all in the opposite state. The button has the class `.open-all` and a label specified by the `title` prop (`open/close` by default, which can be changed in the component file). Additional classes can be passed using the `classes` prop.

## Example Usage ([Astro page](https://docs.astro.build/en/basics/astro-pages/#astro-pages))
```JSX
---
import OpenAll from '../components/OpenAll.astro'
---
<section class="fruit">
  <h2>
    Fruit
    <OpenAll selector=".fruit details" title="expand/collapse all" classes="fruit-button" />
  </h2>

  <details>
    <summary>Berries</summary>
    Blueberry, Raspberry, Strawberry
  </details>

  <details>
    <summary>Citruses</summary>
    Lemon, Grape, Orange
  </details>
</section>
```

Resulting button:
```HTML
<open-all data-selector=".fruit details">
  <button class="open-all fruit-button" type="button">expand/collapse all</button>
</open-all>
```
