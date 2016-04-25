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

## 1.2

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

function getFirstModel() {
  return this.models[0];
}

function getModel(getSpecificModel) {
  var model = getSpecificModel.call(this);
  
  function getModelName() {
    return this.name;
  }
  
  model.getModelName = getModelName;
  
  return model;
}

var result = tesla.getModel(getFirstModel).getModelName();

console.log(result); // 'Model S'
```

+ https://repl.it/BzWx

## 1.3

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

function getFirstModel() {
  return this.models[0];
}

function getModelName() {
  return this.name;
}

function getModel(getSpecificModel, getSpecificProperty) {
  var model = getSpecificModel.call(this);
  var property = getSpecificProperty.call(model);
  
  function getIt() {
    return property;
  }
  
  model.getIt = getIt;
  
  return model;
}

var result = tesla.getModel(getFirstModel, getModelName).getIt();

console.log(result); // 'Model S'
```

+ https://repl.it/BzXD

## 1.4

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

Object.prototype.getModel = getModel;

function getFirstModel() {
  return this.models[0];
}

function getModelName() {
  return this.name;
}

function getModel(getSpecificModel, getSpecificProperty) {
  var model = getSpecificModel.call(this);
  var property = getSpecificProperty.call(model);

  function getIt() {
    return property;
  }

  model.getIt = getIt;

  return model;
}

var result = tesla.getModel(getFirstModel, getModelName).getIt();

console.log(result); // 'Model S'
```

+ https://repl.it/BzXF

## 2

```js
function processData(data) {
	var result;
	var arrayOfKeys = Object.keys(data);
	
	result = arrayOfKeys // ['list1', 'list2', 'list3']
			.reduce(function (accumulator, currentValue, currentIndex, array) {
				return accumulator.concat(data[currentValue]);
			}, [])
			.filter(function (arrayElement) {
				return arrayElement < 10;
			})
			.sort()
			.reverse()
			.join('');
	
	return result;
}

var sample = {
	list1: [10, 1, 22],
	list2: [7, 99, 12.5],
	list3: [0.75, 67, 11]
};

console.log(processData(sample));
```
