---
title: Mouse
type: docs
prev: docs/module/keyboard
next: docs/module/state
---

The `Mouse` module provides a way to send and receive mouse events.

You can access the `Mouse` module via the `@powerkeys/v1` module.

## Enums

### MouseButtons
The `MouseButtons` enum defines the available mouse buttons:

```javascript
import { MouseButton } from '@powerkeys/v1';

MouseButton.Left
MouseButton.Right
MouseButton.Middle
MouseButton.Button4
MouseButton.Button5
```

## Functions

### GetPos

`GetPos` returns an object containing the current mouse position.

Returns:

- `object`: An object with `x` and `y` properties representing the current mouse coordinates.

Example:
```javascript
import { Mouse, Console } from '@powerkeys/v1';

const pos = Mouse.GetPos();
Console.Log(pos.x, pos.y);
```

### Move

`Move` moves the mouse by the specified x and y offsets.

Parameters:

- `x` (number): The x offset to move the mouse by.
- `y` (number): The y offset to move the mouse by.

Example:
```javascript
import { Mouse } from '@powerkeys/v1';

Mouse.Move(100, 100);
```

### MoveTo

`MoveTo` moves the mouse to the specified x and y coordinates.

Parameters:

- `x` (number): The x coordinate to move the mouse to.
- `y` (number): The y coordinate to move the mouse to.

Example:
```javascript
import { Mouse } from '@powerkeys/v1';

Mouse.MoveTo(200, 150);
```

### SendMousePress

`SendMousePress` sends a mouse press event.

Parameters:

- `button` (MouseButton): The button to press.

Example:
```javascript
import { Mouse, MouseButton } from '@powerkeys/v1';

Mouse.SendMousePress(MouseButton.Left);
```

### BlockMouseKey

`BlockMouseKey` blocks a mouse key from triggering any events.

Parameters:

- `button` (MouseButton): The button to block.

Example:
```javascript
import { Mouse, MouseButton } from '@powerkeys/v1';

Mouse.BlockMouseKey(MouseButton.Left);
```

### UnblockMouseKey

`UnblockMouseKey` unblocks a mouse key, allowing it to trigger events again.

Parameters:

- `button` (MouseButton): The button to unblock.

Example:
```javascript
import { Mouse, MouseButton } from '@powerkeys/v1';

Mouse.UnblockMouseKey(MouseButton.Left);
```

### OnMousePress

`OnMousePress` registers a callback for when a mouse key is pressed.

Parameters:

- `callback` (function): The callback to call when a mouse key is pressed.
  - params:
    - `button` (MouseButton): The button that was pressed.

Example:
```javascript
import { Mouse, Console } from '@powerkeys/v1';

Mouse.OnMousePress((button) => {
  Console.Log("Mouse button pressed: " + button);
});
```
