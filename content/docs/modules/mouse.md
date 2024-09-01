---
title: Mouse
type: docs
prev: docs/module/keyboard
next: docs/module/state
---

Mouse provides a way to send and receive mouse events

## Enums

### MouseButtons
```javascript
MouseButton.Left
MouseButton.Right
MouseButton.Middle
MouseButton.Button4
MouseButton.Button5
```

## Functions

### GetPos

Returns an object containing the current mouse position

```javascript
const pos = Mouse.GetPos();

Console.Log(pos.x, pos.y);
```

### Move

Moves the mouse to the specified position

Parameters:
- x (number): The x coordinate to move the mouse to
- y (number): The y coordinate to move the mouse to

```javascript
Mouse.Move(100, 100);
```

### SendMousePress

Sends a mouse press event

Parameters:
- button (MouseButton): The button to press

```javascript
Mouse.SendMousePress(MouseButton.Left);
```

### BlockMouseKey

Blocks a mouse key from being sent

Parameters:
- button (MouseButton): The button to block

```javascript
Mouse.BlockMouseKey(MouseButton.Left);
```

### UnblockMouseKey

Unblocks a mouse key from being sent

Parameters:

- button (MouseButton): The button to unblock

```javascript
Mouse.UnblockMouseKey(MouseButton.Left);
```

### OnMousePress

Registers a callback for when a mouse key is pressed

Parameters:
- callback (function): The callback to call when a mouse key is pressed
  - params:
    - button (MouseButton): The button that was pressed

```javascript
Mouse.OnMousePress((button) => {
  Console.Log("Mouse button pressed: " + button);
});
```

