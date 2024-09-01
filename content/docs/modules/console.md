---
title: Console
type: docs
prev: docs/module/
next: docs/module/keyboard
---

The console provides a way to log to the app window. It is useful for debugging and for providing feedback to the user.

## Log

Logs to the output tab in the app window.

Parameters:

- `message` (string): The message to log.

```javascript
Console.Log('Hello, world!');
```


## Warn

Logs a warning to the output tab in the app window. Warnings are displayed in yellow and have a warning icon.

Parameters:

- `message` (string): The warning message to log.

```javascript
Console.Warn('Warning: This is a warning message.');
```

## Error

Logs an error to the output tab in the app window. Errors are displayed in red and have an error icon.

Parameters:

- `message` (string): The error message to log.

```javascript
Console.Error('Error: This is an error message.');
```
