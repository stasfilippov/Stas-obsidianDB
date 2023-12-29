202312292024
Tags: #progr 

---
## Содержание
 1. Получает callback - в котором происходят различные вычисления
 2. Вторым параметром получает переменную, за изменением которой нужно следить и если она изменилась, то сделать перерасчет
```js
export function Example1() {  
  const [a, setA] = useState<number>(5);  
  const [b, setB] = useState<number>(5);  
  
  let resultA = 1;  
  let resultB = 1;  
  
  resultA = useMemo(() => {  
    let tempResult = 1;  
    for (let i = 1; i <= a; i++) {  
      let fake = 0;  
      while (fake < 100000000) {  
        fake++;  
        const fakeValue = Math.random();  
      }  
      tempResult = tempResult * i;  
    }  
    return tempResult;  
  }, [a]);  
  
  for (let i = 1; i <= b; i++) {  
    resultB = resultB * i;  
  }  
  
  return (  
    <>  
      <input value={a} onChange={(e) => setA(+e.currentTarget.value)} />  
      <input value={b} onChange={(e) => setB(+e.currentTarget.value)} />  
      <hr />      <div>Result for a: {resultA}</div>  
      <div>Result for b: {resultB}</div>  
    </>  );  
}
```

#### Использование для помощи для React.memo
- при использовании filter, map - которые заставляют перерисовывать компоненту, тк React.memo думает, что получает новые props

---
### Zero-Links


---
### Links
