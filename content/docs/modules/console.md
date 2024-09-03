---
title: Console
type: docs
prev: docs/module/
next: docs/module/keyboard
---

The `Console` module provides functionality to log messages to the app window, which is useful for debugging and providing feedback to the user.

You can access the `Console` functionality via the `@powerkeys/v1` module.

## Log

`Log` outputs a message to the output tab in the app window.

Parameters:

- `message` (string): The message to log.

Example:
```javascript
import { Console } from '@powerkeys/v1';

Console.Log('Hello, world!');
```

## Warn

`Warn` outputs a warning message to the output tab in the app window. Warnings are displayed in yellow and include a warning icon.

Parameters:

- `message` (string): The warning message to log.

Example:
```javascript
import { Console } from '@powerkeys/v1';

Console.Warn('Warning: This is a warning message.');
```

## Error

`Error` outputs an error message to the output tab in the app window. Errors are displayed in red and include an error icon.

Parameters:

- `message` (string): The error message to log.

Example:
```javascript
import { Console } from '@powerkeys/v1';

Console.Error('Error: This is an error message.');
```
