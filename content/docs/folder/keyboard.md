---
title: Keyboard
type: docs
prev: docs/folder/console
next: docs/folder/mouse
---

Keyboard provides a way to send keys to the system. It also provides ways to listen for key events, you can also block and unblock keys from being sent to the system.

## SendKey

`SendKey` takes 2 parameters, the key to send to the system, and the amount of time to hold the key down for. The key can be any key on the keyboard, and the time is in milliseconds.

Parameters:

- `key` (string) - The key to send to the system.
  - example: `'A'`
- `time` (number?) - The amount of time to hold the key down for.
  - example: `1000`
  - default: `50`

```javascript
// Will press the 'A' key for 1000 milliseconds
Keyboard.SendKey("A", 1000);
```

## SendKeyDown

`SendKeyDown` takes 1 parameter, the key to send to the system. The key can be any key on the keyboard.

Parameters:

- `key` (string) - The key to send to the system.
  - example: `'A'`

```javascript
// Will press the 'A' key down
Keyboard.SendKeyDown("A");
```

## SendKeyUp

`SendKeyUp` takes 1 parameter, the key to release on the system. The key can be any key on the keyboard.

Parameters:

- `key` (string) - The key to release on the system.
  - example: `'A'`

```javascript
// Will release the 'A' key
Keyboard.SendKeyUp("A");
```

## BlockKey

`BlockKey` takes 1 parameter, the key to block from being sent to the system. The key can be any key on the keyboard.

Parameters:

- `key` (string) - The key to block from being sent to the system.
  - example: `'A'`

```javascript
// Will block the 'A' key from being pressed
Keyboard.BlockKey("A");
```

## UnblockKey

`UnblockKey` takes 1 parameter, the key to unblock from being sent to the system. The key can be any key on the keyboard.

Parameters:

- `key` (string) - The key to unblock from being sent to the system.
  - example: `'A'`

```javascript
// Will unblock the 'A' key from being pressed
Keyboard.UnblockKey("A");
```

## OnKeyDown

`OnKeyDown` takes 1 parameter, the callback function to call when the key is pressed. The key can be any key on the keyboard.

Parameters:

- `callback` (function) - The function to be called when the key is pressed.
  - params:
    - `key` (string): the key that was pressed

```javascript
// Will call the function when the 'A' key is pressed
Keyboard.OnKeyDown(function (key) {
  Console.Log(`The ${key} key was pressed!`);
});
```

## OnKeyUp

`OnKeyUp` takes 1 parameter, the callback function to call when the key is released. The key can be any key on the keyboard.

Parameters:

- `callback` (function) - The function to be called when the key is released.
  - params:
    - `key` (string): the key that was released

```javascript
// Will call the function when the 'A' key is released
Keyboard.OnKeyUp(function (key) {
  Console.Log(`The ${key} key was released!`);
});
```

## OnKeyPress

`OnKeyPress` takes 1 parameter, the callback function to call when the key is pressed. The key can be any key on the keyboard.

Parameters:

- `callback` (function) - The function to be called when the key is pressed.
  - params:
    - `key` (string): the key that was pressed
    - `down` (boolean): whether the key was pressed down or released

```javascript
// Will call the function when the 'A' key is pressed
Keyboard.OnKeyPress(function (key, down) {
  if (down) {
    Console.Log(`The ${key} key was pressed!`);
  } else {
    Console.Log(`The ${key} key was released!`);
  }
});
```
