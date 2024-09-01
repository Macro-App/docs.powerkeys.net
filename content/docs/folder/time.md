---
title: Time
type: docs
prev: docs/folder/state
next: docs/folder/uibuilder
---

Time is a module that allows you to delay or call a function after a certain amount of time.

## Sleep

Sleep will halt the execution of a script for a specified amount of time.

Parameters:

- `time` (number): The amount of time to sleep in milliseconds.

```javascript
// Will sleep for 1 second
Time.Sleep(1000);
```

## SetTimeout

SetTimeout will call a function after a specified amount of time.

Parameters:

- `callback` (function): The function to call after the time has passed.
- `time` (number): The amount of time to wait before calling the function.

```javascript
// Will call the function after 1 second
Time.SetTimeout(() => {
  Console.Log("Hello, world!");
}, 1000);
```
