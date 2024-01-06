202312241153
Tags: #progr 

---
## Содержание
- **ИСПОЛЬЗОВАТЬ ВСЕГДА!!!**
 - это **Hight Order Component** - HOC. 
 - компонент высшего порядка 
 - это функция, получающая компоненту, и возвращает другую компоненту, как правило, это та же самая компонента, но с доп возможностями (доп props) = **контейнерная компонента с props**
 - примеры - **withRouter, connect**, **react Memo**

### React.memo
- мемоизация - как кэширование, запомни и если ничего не поменялось возвращай тоже самое
- если же мы даем это напрямую пользователю, то при передаче одних и тех же props пользователем -> react работает в холостую
- А если используется react.memo - он проверяет props, если пользователь передал те же props, то не будет ничего перерисовывать
- ![[Pasted image 20231224213445.png]]
- ![[Pasted image 20231224120818.png]]
```ts
const UsersSecret = (props: { users: Array<string> }) => {  
  console.log("USERS");  
  return (  
    <div>  
      {props.users.map((u, i) => (  
        <div key={i}>{u}</div>  
      ))}    </div>  
  );};  
  
const Users = React.memo(UsersSecret);
```


---
### Zero-Links
[[00 React]]

---
### Links
[[useMemo]]
