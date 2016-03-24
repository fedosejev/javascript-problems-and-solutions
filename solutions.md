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