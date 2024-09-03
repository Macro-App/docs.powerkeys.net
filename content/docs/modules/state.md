---
title: State
type: docs
prev: docs/module/mouse
next: docs/module/time
---

The `State` module is a key-value store that can be used to store and retrieve data. It is particularly useful for persisting data across script executions.

The state is synced to the cloud every 5 seconds and is accessible across all devices.

You can access the `State` module via the `@powerkeys/v1` module.

## Get

`Get` retrieves the value associated with a specified key from the state.

If the key does not exist, it will return `null`.

Parameters:

- `key` (string): The key to retrieve from the state.

Returns:

- The value of the key in the state, or `null` if the key does not exist.

Example:
```javascript
import { State } from '@powerkeys/v1';

// Will get the value of the key 'myKey'
let value = State.Get('myKey');

// Will log either the value of 'myKey' or null
Console.Log(value);
```

## Set

`Set` assigns a value to a specified key in the state.

Parameters:

- `key` (string): The key to set in the state.
- `value` (any): The value to set in the state.

`value` can be of any type, including objects and arrays.

> **Warning:** `value` must be JSON serializable.

Example:
```javascript
import { State } from '@powerkeys/v1';

// Will set the key 'myKey' to the value '5'
let value = 5;
State.Set('myKey', value);

// Later on, you can retrieve the value
let retrievedValue = State.Get('myKey');

// Will log the value of 'myKey', in this case 5
Console.Log(retrievedValue);
```

## Has

`Has` checks whether a specified key exists in the state.

Parameters:

- `key` (string): The key to check in the state.

Returns:

- `boolean`: Whether the key exists in the state.

Example:
```javascript
import { State } from '@powerkeys/v1';

// Will check if the key 'myKey' exists in the state
const exists = State.Has('myKey');

if (exists) {
  Console.Log('The key exists!');
} else {
  Console.Log('The key does not exist!');
}
```

## Remove

`Remove` deletes a specified key from the state.

Parameters:

- `key` (string): The key to remove from the state.

Example:
```javascript
import { State } from '@powerkeys/v1';

// Will remove the key 'myKey' from the state
State.Remove('myKey');

// Later on...
const exists = State.Has('myKey');
Console.Log(exists); // Will log false
```
