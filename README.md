# Collection of problems to solve in JavaScript

## 1.

Given `tesla` object:

```js
var tesla = {
  models: [
    {
      name: 'Model S'
    },
    {
      name: 'Model X'
    }
  ]
};
```

Write two functions: 1) `getFirstModel` that returns the first object from the `models` array and 2) `getModelName` that returns model's `name`. These functions should be called like this:

```js
tesla.getFirstModel().getModelName(); // 'Model S'
```

__Extra points__: use `this` keyword.

## 1.1

Modify previous solution: instead of `getFirstModel` function, write `getModel` function that accepts number as a parameter. That number tells which object to return from `models` array.

Example:

```js
tesla.getModel(1).getModelName(); // 'Model S'
```

## 1.2

Modify previous solution: instead of number, `getModel` should accept a function as a parameter. That function knows which object to return from `models` array.

Example:

```js
tesla.getModel(getFirstModel).getModelName(); // 'Model S'
```

## 1.3

Modify previous solution: `getModel` function should accept two parameters - 1) a function that knows which model to return and 2) a function that knows which property of the model to return. Then write `getIt` function that actually returns the value of that property.

Example:

```js
tesla.getModel(getFirstModel, getModelName).getIt(); // 'Model S'
```

## 1.4

In your previous solution avoid creating `getModel` property on `tesla` object.

For example, don't do this:

```js
tesla.getModel = getModel;
```

Use __Prototype Linking__ and __Behaviour Delegation__ instead.

## Solutions

+ [Solutions](solutions.md)
