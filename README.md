# juicy-table-repeat
This is a workaround custom element to support `<template is="dom-repeat">` in `<table>` under IE.
Will not be required after this Polymer issue is fixed: https://github.com/Polymer/polymer/issues/1567

## Observing changes

**Note:** `juicy-table-repeat` observes changes in the `rows` array, but re-rendering HTML table might be expensive.

- A splice on the `rows` array causes entire table re-rendering.
- A row property change causes entire table row re-rendering.

## License

MIT
