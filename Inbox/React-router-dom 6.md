202311122219
Tags: #progr 

---
## Подключение

`yarn add react-router-dom`
`yarn add @types/react-router-dom`

1.  Подключение в **index.tsx**
```TS
<BrowserRouter>  
  <App />  
</BrowserRouter>
```
2. 
### Навигация
1. **useNavigate()** с помощью хука - возможно передать в **качестве колбека**
	- - **navigate ( -n )** - может принимать в параметры *число* - возврат на  *n* последних переходов по cтраницам
```JS
const navigate = useNavigate()

navigate('/login');
```



2. **Redirection** - если пользователь еще не зарегистрирован (не открыт доступ)
```JS
useEffect(() => {  
    if (true) navigate('/login')  
}, [])

//ИЛИ 

{true && <Navigate to={'/login'}/>}
```


### Query параметр
- параметр = переменная - в url -> /profile **?name=sgn**
- имеется хук useSearchParams ()
```JS
const [searchParams, setSearchParams] = useSearchParams()  
  
console.log(searchParams.get('name'))  
console.log(Object.fromEntries(searchParams))  
  
useEffect(() => {  
    console.log('research...')  
}, [searchParams])  
  
return <div>  
    <button onClick={() => {  
       setSearchParams({...Object.fromEntries(searchParams), age: '32'})  
    }}> Set age  
    </button>  
</div>
```

---
### Zero-Links
[[00 React]]

---
### Links
