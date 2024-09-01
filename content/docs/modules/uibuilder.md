---
title: UIBuilder
type: docs
prev: docs/module/time
next: docs/module/othermodule
---

The `UIBuilder` module allows you to dynamically create and configure UI that users can use to interact with your script.

Every script can have a `build_ui` function that is called when the script is loaded. This function can be used to create the UI elements that will be displayed to the user.

```javascript
function build_ui(builder) {
  // Do things with the builder
}
```

## Methods

### AddButton

`AddButton` adds a button to the UI and binds a callback function to its click event.

Parameters:

- `content` (string): The text content of the button.
- `callback` (function): The function to call when the button is clicked.

Example:
```javascript
function build_ui(builder) {
  // Adds a button with the text "Click Me"
  builder.AddButton("Click Me", () => {
    Console.Log("Button clicked!");
  });
}
```

### AddSlider

`AddSlider` adds a slider to the UI, allowing users to select a value within a specified range.

Parameters:

- `id` (string): A unique identifier for the slider.
- `minimum` (number): The minimum value of the slider.
- `maximum` (number): The maximum value of the slider.
- `name` (string): The name of the slider (for internal use).
- `width` (number, optional): The width of the slider in pixels. Default is 200.

Returns:

- `SliderWrapper`: An object that allows you to retrieve the current value of the slider.

Example:
```javascript
let slider = null;
function build_ui(builder) {
  // Adds a slider with a range from 0 to 100
  let slider = builder.AddSlider("volume_slider", 0, 100, "Volume");
}

// Later in the script
const sliderValue = slider.GetValue();
```

### AddComboBox

`AddComboBox` adds a combo box (drop-down list) to the UI, allowing users to select from a predefined set of options.

Parameters:

- `id` (string): A unique identifier for the combo box.
- `items` (array): An array of items to display in the combo box.
- `name` (string): The name of the combo box (for internal use).
- `width` (number, optional): The width of the combo box in pixels. Default is 200.

Returns:

- `ComboBoxWrapper`: An object that allows you to retrieve the selected value from the combo box.

Example:
```javascript
let comboBox = null;
function build_ui(builder) {
  // Adds a combo box with three options
  comboBox = builder.AddComboBox("color_combo", ["Red", "Green", "Blue"], "Color");
}

// Later in the script
const selectedColor = comboBox.GetSelectedValue();
```

### AddCheckBox

`AddCheckBox` adds a checkbox to the UI, allowing users to toggle a setting on or off.

Parameters:

- `id` (string): A unique identifier for the checkbox.
- `content` (string): The text content displayed next to the checkbox.
- `name` (string): The name of the checkbox (for internal use).

Returns:

- `CheckBoxWrapper`: An object that allows you to check whether the checkbox is selected.

Example:
```javascript
let checkBox = null;
function build_ui(builder) {
  // Adds a checkbox with the text "Enable Feature"
  checkBox = builder.AddCheckBox("feature_checkbox", "Enable Feature", "Feature");
}

// Later in the script
const isEnabled = checkBox.IsChecked();
```

### AddRow

`AddRow` creates a horizontal stack panel to organize UI elements in a row.

Returns:

- `RowColumnWrapper`: An object that allows you to add elements to the row.

Example:
```javascript
function build_ui(builder) {
  // Creates a row and adds a button and a slider to it
  let row = builder.AddRow();
  row.AddButton("Click Me", () => {
    Console.Log("Button clicked!");
  });
  row.AddSlider("volume_slider", 0, 100, "Volume");
}
```

### AddColumn

`AddColumn` creates a vertical stack panel to organize UI elements in a column.

Returns:

- `RowColumnWrapper`: An object that allows you to add elements to the column.

Example:
```javascript
function build_ui(builder) {
  // Creates a column and adds a button and a slider to it
  let column = builder.AddColumn();
  column.AddButton("Click Me", () => {
    Console.Log("Button clicked!");
  });
  column.AddSlider("volume_slider", 0, 100, "Volume");
}
```

## Wrapper Classes

### SliderWrapper

`SliderWrapper` allows you to interact with a slider added through the `UIBuilder`.

#### GetValue

`GetValue()` retrieves the current value of the slider.

Returns:

- `number`: The current value of the slider.

### ComboBoxWrapper

`ComboBoxWrapper` allows you to interact with a combo box added through the `UIBuilder`.

#### GetSelectedValue

`GetSelectedValue()` retrieves the currently selected value from the combo box.

Returns:

- `string`: The currently selected value.

### CheckBoxWrapper

`CheckBoxWrapper` allows you to interact with a checkbox added through the `UIBuilder`.

#### IsChecked

`IsChecked()` checks whether the checkbox is currently selected.

Returns:

- `boolean`: `true` if the checkbox is checked, `false` otherwise.
