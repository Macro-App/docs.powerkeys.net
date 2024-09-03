---
title: Time
type: docs
prev: docs/module/state
next: docs/module/uibuilder
---

The `Time` module provides functions to delay script execution or call a function after a specified amount of time.

You can access the `Time` module via the `@powerkeys/v1` module.

## Sleep

`Sleep` halts the execution of a script for a specified amount of time.

Parameters:

- `time` (number): The amount of time to sleep in milliseconds.

Example:
```javascript
import { Time } from '@powerkeys/v1';

// Will sleep for 1 second
Time.Sleep(1000);
```

## SetTimeout

`SetTimeout` calls a function after a specified amount of time.

Parameters:

- `callback` (function): The function to call after the time has passed.
- `time` (number): The amount of time to wait before calling the function.

Example:
```javascript
import { Time } from '@powerkeys/v1';

// Will call the function after 1 second
Time.SetTimeout(() => {
  Console.Log("Hello, world!");
}, 1000);
```
