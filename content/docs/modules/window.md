---
title: Window
type: docs
prev: docs/module/uibuilder
---

The `Window` module provides a way to get the currently focused window and allows you to be notified when the focus changes.

You can access the `Window` functionality via the `@powerkeys/v1` module.

## CurrentFocus

`CurrentFocus` returns the full path of the currently focused window.

Returns:

- `string` - The full path of the currently focused window.

Example:
```javascript
import { Window } from '@powerkeys/v1';

const windowPath = Window.CurrentFocus;

// Example output if the focused window is notepad: "C:\Windows\System32\notepad.exe"
Console.Log(windowPath);
```

## OnFocusChange

`OnFocusChange` registers a callback function to be called when the currently focused window changes.

Parameters:

- `callback` (function) - The function to be called when the currently focused window changes.
  - params:
    - `windowPath` (string) - The full path of the newly focused window.

Example:
```javascript
import { Window } from '@powerkeys/v1';

Window.OnFocusChange(function (windowPath) {
  Console.Log(windowPath); // Will log the full path of the newly focused window
});
```