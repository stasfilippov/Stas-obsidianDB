202401062124
Tags: #progr 

---
## Содержание
### Когда использовать
1. Во всех компонентах используется [[React Memo]]
2. Когда в компоненту обернутую *React Memo* мы передаем **callback**, то мы обязаны использовать `useCallback`

---
 1. является частным случаем [[useMemo]] 
- в том случае, когда нужно избежать перерисовки компоненты при передаче через props callback - хотя ничего нового компонента не получает
- тк при каждом ре-рендере происходит создание новой функции (нового объекта) - в итоге в компоненту передается измененные данные, что и заставляет ее перерисовываться 
- получает **callback** который и нужно запомнить и **зависимость**, при изменении которой и будет возвращаться новый callback
```js
const memoizedAddBook = useCallback(() => {  
  console.log(books);  
  const newBooks = [...books, "Angular" + new Date().getTime()];  
  setBooks(newBooks);  
}, [books]);
```


---
### Zero-Links
[[00 React]]

---
### Links
[[useMemo]]
[[React Memo]]