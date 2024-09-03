---
title: Keyboard
type: docs
prev: docs/module/console
next: docs/module/mouse
---

The `Keyboard` module provides functionality to send keys to the system and listen for key events. It also allows blocking and unblocking keys from being sent to the system.

You can access the `Keyboard` functionality via the `@powerkeys/v1` module.

## SendKey

`SendKey` sends a key press to the system for a specified duration. The key can be any key on the keyboard, and the duration is in milliseconds.

Parameters:

- `key` (string): The key to send to the system.
  - Example: `'A'`
- `time` (number, optional): The amount of time to hold the key down. Default is `50` milliseconds.
  - Example: `1000`

Example:
```javascript
import { Keyboard } from '@powerkeys/v1';

// Will press the 'A' key for 1000 milliseconds
Keyboard.SendKey("A", 1000);
```

## SendKeyDown

`SendKeyDown` simulates pressing a key down on the system. The key can be any key on the keyboard.

Parameters:

- `key` (string): The key to send to the system.
  - Example: `'A'`

Example:
```javascript
import { Keyboard } from '@powerkeys/v1';

// Will press the 'A' key down
Keyboard.SendKeyDown("A");
```

## SendKeyUp

`SendKeyUp` simulates releasing a key on the system. The key can be any key on the keyboard.

Parameters:

- `key` (string): The key to release on the system.
  - Example: `'A'`

Example:
```javascript
import { Keyboard } from '@powerkeys/v1';

// Will release the 'A' key
Keyboard.SendKeyUp("A");
```

## BlockKey

`BlockKey` prevents a specified key from being sent to the system.

Parameters:

- `key` (string): The key to block from being sent to the system.
  - Example: `'A'`

Example:
```javascript
import { Keyboard } from '@powerkeys/v1';

// Will block the 'A' key from being pressed
Keyboard.BlockKey("A");
```

## UnblockKey

`UnblockKey` allows a previously blocked key to be sent to the system again.

Parameters:

- `key` (string): The key to unblock from being sent to the system.
  - Example: `'A'`

Example:
```javascript
import { Keyboard } from '@powerkeys/v1';

// Will unblock the 'A' key from being pressed
Keyboard.UnblockKey("A");
```

## OnKeyDown

`OnKeyDown` registers a callback function that is called when a specified key is pressed down.

Parameters:

- `callback` (function): The function to be called when the key is pressed.
  - params:
    - `key` (string): The key that was pressed.

Example:
```javascript
import { Keyboard } from '@powerkeys/v1';

// Will call the function when the 'A' key is pressed
Keyboard.OnKeyDown(function (key) {
  Console.Log(`The ${key} key was pressed!`);
});
```

## OnKeyUp

`OnKeyUp` registers a callback function that is called when a specified key is released.

Parameters:

- `callback` (function): The function to be called when the key is released.
  - params:
    - `key` (string): The key that was released.

Example:
```javascript
import { Keyboard } from '@powerkeys/v1';

// Will call the function when the 'A' key is released
Keyboard.OnKeyUp(function (key) {
  Console.Log(`The ${key} key was released!`);
});
```

## OnKeyPress

`OnKeyPress` registers a callback function that is called when a specified key is pressed or released.

Parameters:

- `callback` (function): The function to be called when the key is pressed or released.
  - params:
    - `key` (string): The key that was pressed or released.
    - `down` (boolean): Indicates whether the key was pressed down (`true`) or released (`false`).

Example:
```javascript
import { Keyboard } from '@powerkeys/v1';

// Will call the function when the 'A' key is pressed or released
Keyboard.OnKeyPress(function (key, down) {
  if (down) {
    Console.Log(`The ${key} key was pressed!`);
  } else {
    Console.Log(`The ${key} key was released!`);
  }
});
```
