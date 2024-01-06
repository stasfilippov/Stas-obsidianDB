202312212220
Tags: #progr 

---
## Содержание
 - Это **чистая** функция преобразователь - преобразователь стейта - нет **sideEffect**
	 - не работает с localstorage
	 - не делает запросы на сервер
	 - *иммутабельность*
	 - *предсказуемость* (**детерминированность** - сколько бы раз мы не вызывали функцию с одинаковыми данными - результат будет как в первый раз, **индентопатентность** - сколько бы раз мы не вызывали функцию с одинаковыми данными - результат один и тот же)

 - В нем концентрируется логика изменений, которая должна произойти со стейтом
 - Чаще используется при наличии множества стейтов в компоненте

- На входе он получает - **state** и **action**
	- **action** - это инструкция, объект, содержащий информацию о том, как нужно изменить объект. Должен быть **type** - его название

![[Pasted image 20231221224042.png]]


- как правило **reducer** должен получит несколько **action**
- как правило - нельзя **диспатчить** action, который **не ожидает** reducer 
### Action 
- это объект
- создаем за счет **функций фабрик - Action Creator**
```JS
export const changeTodolistTitleAC = (id: string, title: string) => {  
    return {type: 'CHANGE-TODOLIST-TITLE', payload: {id, title}} as const  
}
```
- обязательно указываем - **as const**
- проводим типизацию данного **action creator**
```js
type ChangeTodolistTitleACType = ReturnType<typeof changeTodolistTitleAC>
```
- в дальнейшем при **dispatch** какого-либо action - вызываем данный **action creator**




#### Если пришел не тот action
```js
default:  
  throw new Error("Bad action type");
```
- Или желательно возвращать тот же state, который пришел изначально 

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
