# juicy-table-repeat
This is a workaround custom element to support `<template is="dom-repeat">` in `<table>` under IE.
Will not be required after this Polymer issue is fixed: https://github.com/Polymer/polymer/issues/1567

## Usage example

Instead of following code:
```html
  <table>
      <thead>
      <!-- your favorite thead -->
      </thead>
      <tbody>
      <template is="dom-repeat" items="{{model.Shops}}">
          <tr>
              <td>{{item.Name}}</td>
              <!-- other item stuff -->
          </tr>
      </template>
      </tbody>
  </table>
```

Use this:

```html
<juicy-table-repeat rows="{{model.Shops}}">
    <table>
      <thead>
      <!-- your favorite thead -->
      </thead>
      <tbody>
      </tbody>
    </table>
    <template is="dom-template" class="row-template">
        <table class="products-shops-box">
            <tr>
              <td>{{item.Name}}</td>
              <!-- other item stuff -->
            </tr>
        </table>
    </template>
</juicy-table-repeat>
```

## Observing changes

**Note:** `juicy-table-repeat` observes changes in the `rows` array, but re-rendering HTML table might be expensive.

- A splice on the `rows` array causes entire table re-rendering.
- A row property change causes entire table row re-rendering.

## License

MIT
