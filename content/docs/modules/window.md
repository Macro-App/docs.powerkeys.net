---
title: Window
type: docs
prev: docs/module/uibuilder
---

Window provides a way to get the currently focused window. It also has a way to get notified when the currently focused window changes.

## CurrentFocus

Returns the full path of the currently focused window.

Returns:

- `string` - The full path of the currently focused window.

```javascript
const windowPath = Window.CurrentFocus;

// Example output if the focused window is notepad: "C:\Windows\System32\notepad.exe"
Console.Log(windowPath);
```

## OnFocusChange

Registers a callback function to be called when the currently focused window changes.

Parameters:

- `callback` (function) - The function to be called when the currently focused window changes.
  - params:
    - `windowPath` (string) - The full path of the newly focused window.

```javascript
Window.OnFocusChange(function (windowPath) {
  Console.Log(windowPath); // Will log the full path of the newly focused window
});
```
