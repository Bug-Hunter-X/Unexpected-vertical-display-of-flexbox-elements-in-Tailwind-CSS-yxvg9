# Unexpected vertical display of flexbox elements in Tailwind CSS

This repository demonstrates an unexpected behavior when using Tailwind CSS classes with flexbox.  The expected behavior is that flex items should be displayed horizontally by default. However, under certain conditions, they display vertically. This issue shows a way to reproduce the behavior and offers a solution.  This often results from a missing or incorrect parent container configuration.

## Bug Report

The following HTML code snippet uses Tailwind CSS classes to create a flexible layout with two divs.  The expected result is that the divs would display side-by-side horizontally.

```html
<div class="flex">
  <div class="bg-red-500 p-4">
    This is red
  </div>
  <div class="bg-blue-500 p-4">
    This is blue
  </div>
</div>
```

However, depending on the context and other CSS rules, this might instead result in a vertical display of the divs.

## Solution

The solution generally involves ensuring that the parent element has the necessary properties to allow for horizontal flexbox layout.  In most cases, the issue arises from a missing `flex-row` class.   The solution is adding `flex-row` to the parent `div`.

```html
<div class="flex flex-row">
  <div class="bg-red-500 p-4">
    This is red
  </div>
  <div class="bg-blue-500 p-4">
    This is blue
  </div>
</div>
```

This forces the flex items to arrange horizontally within the parent container.
