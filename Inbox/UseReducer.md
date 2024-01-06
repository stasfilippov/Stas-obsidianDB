202312212220
Tags: #progr 

---
## Содержание
 - Это **чистая** функция преобразователь - преобразователь стейта
	 - не работает с localstorage
	 - не делает запросы на сервер

 - В нем концентрируется логика изменений, которая должна произойти со стейтом
 - Чаще используется при наличии множества стейтов в компоненте

- На входе он получает - **state** и **action**
	- **action** - это инструкция, объект, содержащий информацию о том, как нужно изменить объект. Должен быть **type** - его название

![[Pasted image 20231221224042.png]]

- как правило **reducer** должен получит несколько **action**
- как правило - нельзя **диспатчить** action, который **не ожидает** reducer 
- **ЖЕЛАТЕЛЬНО**  - по default 
```js
default:  
  throw new Error("Bad action type");
```


### Unit tests for reducer
```js
test("reducer should be false", () => {  
  //data  
  const state: StateType = {  
    collapsed: true,  
  };  
  //action  
  const newState = reducer(state, { type: TOGGLE_COLLAPSED });  
  
  //expect  
  expect(newState.collapsed).toBe(false);  
});  
  
test("reducer should be error", () => {  
  //data  
  const state: StateType = {  
    collapsed: true,  
  };  
  //action  
  const newState = reducer(state, { type: TOGGLE_COLLAPSED });  
  
  //expect  
  expect(() => {  
    reducer(state, { type: "TDSADSd" });  
  }).toThrowError();  
});
```

---
### Zero-Links
[[00 React]]


---
### Links
