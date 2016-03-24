# Solutions

## 1.

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

tesla.getFirstModel = getFirstModel;

function getFirstModel() {
  var firstModel = this.models[0];
  
  function getModelName() {
    return this.name;
  }
  
  firstModel.getModelName = getModelName;
  
  return firstModel;
}

var result = tesla.getFirstModel().getModelName();

console.log(result); // 'Model S'
```

+ https://repl.it/BzWs

## 1.1

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

tesla.getModel = getModel;

function getModel(modelNumber) {
  var model = this.models[modelNumber - 1];
  
  function getModelName() {
    return this.name;
  }
  
  model.getModelName = getModelName;
  
  return model;
}

var result = tesla.getModel(1).getModelName();

console.log(result); // 'Model S'
```

+ https://repl.it/BzWw