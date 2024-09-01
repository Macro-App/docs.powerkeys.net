---
title: State
type: docs
prev: docs/folder/mouse
next: docs/folder/time
---

The State module is a key value store that can be used to store and retrieve data. It is useful to store data across script executions.

State is synced to the cloud every 5 minutes and is available across all devices.

## Get

`Get` takes 1 parameter, the key to retrieve from the state.

If the key does not exist, it will return `null`.

Parameters:

- `key` (string): The key to retrieve from the state.

Returns:

- `any`: The value of the key in the state.

```javascript
// Will get the value of the key 'myKey'
let value = State.Get('myKey');

// Will log either the value of 'myKey' or null
Console.Log(value);
```


## Set

`Set` takes 2 parameters, the key to set in the state, and the value to set.

Parameters:

- `key` (string): The key to set in the state.
- `value` (any): The value to set in the state.

`value` can be any type of data, including objects and arrays.

```javascript
// Will set the key 'myKey' to the value 'myValue'
let value = 5

State.Set('myKey', value);

// Later on, you can retrieve the value

let retrievedValue = State.Get('myKey');

// Will log the value of 'myKey', in this case 5
Console.Log(retrievedValue);
```

## Has

`Has` takes 1 parameter, the key to check if it exists in the state.

Parameters:

- `key` (string): The key to check if it exists in the state.

Returns:

- `boolean`: Whether the key exists in the state.

```javascript
// Will check if the key 'myKey' exists in the state
const exists = State.Has('myKey');

if (exists) {
  Console.Log('The key exists!');
} else {
  Console.Log('The key does not exist!');
}
```

## Remove

`Remove` takes 1 parameter, the key to remove from the state.

Parameters:

- `key` (string): The key to remove from the state.

```javascript
// Will remove the key 'myKey' from the state
State.Remove('myKey');

// Later on...
const exists = State.Has('myKey');
Console.Log(exists); // Will log false
```
