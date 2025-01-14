# Iconic Dropdown

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT) [![Version](https://img.shields.io/github/package-json/v/sidneywm/iconic-dropdown)](https://github.com/sidneywm/iconic-dropdown)

<p align="center">A dropdown component written in pure JavaScript - IE11+ compatible</p>

<p align="center">
  <img src="./assets/iconic-dropdown.png">
</p>

### :rocket: [Try live demo](https://sidneywm.github.io/iconic-dropdown/)

## Getting Started

### 1. Link the required files

Firstly, the script needs to be included in your HTML file. If you would like to personalize the Iconic Dropdown component, you can additionally include a CSS stylesheet with your custom CSS properties which target the Iconic Dropdown component classes. Also, do not forget to set `customCss` to `true`. ([see configuration](#configuration))

```html
<head>

  // Optional 
  <link rel="stylesheet" href="dropdown.css" type="text/css" />

</head>

<script src="dropdown.js" type="text/javascript"></script>
```

### 2. Create a select tag

Secondly, within your HTML file, create a `<select>` tag which you want to turn into a dropdown. Do not forget to set an `id` on your `<select>` tag.

```html
<select id="foods">
    <option value="bread">Bread</option>
    <option value="cereal">Cereal</option>
    <option value="pasta">Pasta</option>
    <option value="rice">Rice</option>
    <option value="meat">Meat</option>
    <option value="fish">Fish</option>
</select>
```

### 3. Initialize the Iconic Dropdown component

Finally, target the `id` of your `<select>` tag in the options and initialize the component with the `.init()` method. You may also specify further options. ([see configuration](#configuration))

```html
<script type="text/javascript">

    const dropdown = new IconicDropdown({
      select: "#foods",
    });

    dropdown.init();

</script>
```
## Configuration

### 1. Overview

| Option       | Default              | Type          |
| :---         |     :---:            |     :---:     |
| customCss    | `false`              | `boolean`     |
| data         | `[]`                 | `Object[]`    |
| noData       | `No data found.`     | `string`      |
| noResults    | `No results found.`  | `string`      |
| placeholder  | `Select...`          | `string`      |
| select*      | `none`               | `string`      |
| textField    | `null`               | `string`      |
| valueField   | `null`               | `string`      |

\* This option is compulsory

#### `customCss`
If set to `true`, the component will not inject its own CSS in the `<head>` tag.

#### `data*`
The component can be configured with data set in the configuration fields. It must be an `Array` of `Objects`.

#### `noData`
Text to display if there is no data found in the `<select>` tag or in the data field.

#### `noResults`
Text to display if there is no results when the option list is filtered.

#### `placeholder`
Text to display in the input placeholder.

#### `select`
The `<select>` tag from which the component is initialized.

#### `textField`
The field of the data object that provides the text content.

#### `valueField`
The field of the data object that provides the value.

\* **IMPORTANT:** When `data` is provided, `valueField` and `textField` should also be set.

### 2. Example

```html
  <script type="text/javascript">

    const dropdown = new IconicDropdown({
      customCss: true,
      data: [
        { valueName: "bread", itemName: 'Bread'}, 
        { valueName: "rice", itemName: 'Rice'}, 
        { valueName: "pasta", itemName: 'Pasta'}
      ],
      noData: "No food item found.",
      noResults: "No results found in this list.",
      placeholder: "Select a food item...",
      select: "#foods",
      textField: 'itemName',
      valueField: 'valueName',
    });

  </script>
```

## Methods

#### `.init()`
Initialize the component with all its settings.

#### `.subscribe()`
Listen for all events.

Example: 

```javascript
JavaScript:

dropdown.subscribe(function(event) {
  console.log(event);
});

```

```console 
Console:

Object : { value: "AX", text: "Åland Islands" }
```


## Contributing

Iconic Dropdown is an open-source project. Contributions of any kind are welcome and appreciated. Feel free to open an issue or request a feature. Pull requests are also welcome.

## Author

- [Sidney Wimart](https://github.com/sidneywm)

## License

This project is open source and available under the [MIT License](LICENSE).
