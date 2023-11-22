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

2. Создать коробку **Routes** - где будет отображаться постраничный контент
```JS
<Routes>  
    <Route path={'/page1'} element={<PageOne/>}/>  
    <Route path={'/page2'} element={<PageTwo/>}/>  
    <Route path={'/page3'} element={<PageThree/>}/>  
</Routes>
```

3.  Для каждой страницы **Route** 
	- в аттрибутах указываем путь (**path**) - выдумываем сам
	- **element** - компонент какой будет отображаться по данному пути
```
<Route path={'/page1'} element={<PageOne/>}/>
```

4. ==Обязательно добавить route на **страницу 404==**
`<Route path={'/*'} element={<Error404/>}/>`

5.  Настраиваем route при **первой загрузке** страницы на **первую страницу**
`<Route path={'/'} element={<Navigate to={'/page1'}/>}/>`
- используем Navigate - для переадресации главной страницы по правильному пути

6. Настраиваем **ссылки на страницы**
```JS
<div>  
    <NavLink to={'/page1'}>PageOne</NavLink>  
</div>  
<div>  
    <NavLink to={'/page2'}>PageTwo</NavLink>  
</div>  
<div>  
    <NavLink to={'/page3'}>PageThree</NavLink>  
</div>
```

7.  Реализация большого количества страниц
- Создание файла tsx **dataState**
- Создание одной страницы с методом **map**
	- то есть будет страница с адресом `/path` и в ней множество подстраниц с индексами `/path/index`
- Создание **Route**
`<Route path={'/page/:id'} element={<Page/>}/>`
- Передача в **props** компоненты Pages
`<Route path={'/page/:id'} element={<Page pages={dataState.pages}/>}/>`
- Использование хука **useParams ()** в компоненте Page
`const params = useParams()`
- Отрисовка контента с помощью map 
```JS
{pages[Number(params.id)].heading}  
{pages[Number(params.id)].about}
```
- Использование хука useLocation - можно использовать для отображения контента характерного только для определенной страницы
```JS
const locate = useLocation()


{locate.pathname === '/page/0' && <div>secret text</div>}
```

8. Работа со **страницей 404**
- Добавление двух Route 
```JS
<Route path={'/page/error'} element={<Error404/>}/>  
<Route path={'/*'} element={<Navigate to={'/page/error'}/>}/>
```
- При отображения страниц через map - проверка на правильный id (реализация через хук useParams)
```JS
pages[Number(params.id)]  
    ? <div>  
       {locate.pathname === '/page/0' && <div>secret text</div>}  
       {pages[Number(params.id)].heading}  
       {pages[Number(params.id)].about}  
    </div>  
    : <Navigate to={'/page/error'}/>
```

---
### БИЖУТЕРИЯ
- использование **Link** вместо NavLink
	 *Отличие* - NavLink - запоминает на какой страницы мы были и находимся (дает возможность навесить классы)
	 - если выбираем NavLink - в аттрибутах в className даем **callback**
	 `className={({isActive}) => isActive ? s.active : s.navLink}`

- установить [[Styled_components]]
- создать отдельный файл со стайлами 

---

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

## Новый синтаксис
1. Создание папки в src - **Routes**
2. В ней создается файл **router.tsx**
3. ![[Pasted image 20231123001324.png]]
4. 


---
### Zero-Links
[[00 React]]

---
### Links
