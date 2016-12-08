# &lt;juicy-table-repeat&gt;

> This is a workaround custom element to support `<template is="dom-repeat">` in `<table>` under IE.
Will not be required after this Polymer issue is fixed: https://github.com/Polymer/polymer/issues/1567

## Install

Install the component using [Bower](http://bower.io/):

```sh
$ bower install Juicy/juicy-table-repeat --save
```

Or [download as ZIP](https://github.com/Juicy/juicy-table-repeat/archive/gh-pages.zip).

## Usage

1. Import Web Components' polyfill, if needed:

    ```html
    <script src="bower_components/webcomponentsjs/webcomponents.min.js"></script>
    ```

2. Import Custom Element:

    ```html
    <link rel="import" href="bower_components/juicy-table-repeat/juicy-table-repeat.html">
    ```

3. Start using it!

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
        <table>
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

## Options

Attribute     | Options     | Default      | Description
---           | ---         | ---          | ---
`rows`        | *Array*     |              | The array of objects to iterate over.

## [Contributing and Development](CONTRIBUTING.md)

## History

For detailed changelog, check [Releases](https://github.com/Juicy/juicy-table-repeat/releases).

## License

MIT
