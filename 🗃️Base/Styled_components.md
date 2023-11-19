202308191332
Tags: #

---
## Определение
https://styled-components.com/docs/basics#installation
- библиотека для создания стилизованных компонентов 
**Установка**
`yarn add styled-components`
`yarn add @types/styled-components`
### Создание простого стилизованного компонента
- создаем константу и присваиваем ей **styled."тег на базе которого будет строиться стилизованная компонента"**
- стили пишутся внутри **бек-тиков**

```
const StyledBtn = styled.button `
border: none;  
background-color: pink;  
padding: 18px 20px;  
border-radius: 5px;  
color: black;  
font-size: 2rem;  
font-weight: bold;
`
```
### Extends
- создание на основе базы новых свойств
```
const SuperBtn = styled(StyledBtn)`  
border-radius: 50%;  
background-color: green;  
color: white;  
`
```

### As 
- когда имеются кнопки и ссылки, но они выглядят одинаково
```
<StyledBtn as="a" href='#'>Link</StyledBtn>  
<StyledBtn as={Link} href='#'>LinkComponent</StyledBtn>
```

### Синтаксис 
- похож на **sass**
- ссылка на родительский контейнер
- использование **псевдоклассов**:
```
const StyledBtn = styled.button`  
border: none;  
  
&:hover {  
background-color: #f55f6f;  
}  
  
&:last-child {  
background-color: #b39f13;  
}  
`
```

- *Обращение к родителю* 
```
const Box = styled.div`  
display: flex;  
height: 100vh;  
justify-content: center;  
align-items: center;  
gap: 20px;  
  
button {cursor: pointer;  
}  
`
```
- *Обращение к конкретной компоненте внутри одной компоненты*
```
${Link} {  
cursor: zoom-in;  
}
```

### Комбинаторы
```
li > a {color: green;  // для всех А вложенных в Li
font-weight: bold;  
}  
  
li + li {margin-left: 20px;  //для тех у кого имеется сосед слева 
}
```

### Структура файлов
- могут быть в компоненте "где созданы, там и лежат"
- отдельный файл, где будут все
- все компоненты в отдельные файлы

### Адаптив 
- в самом конце компонента
```
@media screen and (max-width: 800px) {  
flex-direction: column;  
}
```

### Анимации
- создаем отдельную **папку styles** -> **animations** -> файл **Animations.tsx** (здесь пишутся все анимации)
- затем **экспортируем**, созданную анимацию 
```
export const MyAnimation = keyframes`  
from {transform: rotate(0deg);  
}  
to {transform: rotate(360deg);  
}  
`
```
- и используем ее в файлах **.styles.tsx** 
```
&:hover {  
animation: ${MyAnimation} 2s ease-in-out infinite;}
```

### Создание глобальных стилей
- создание в папке styles файла **GlobalStyles.tsx**
```
export const GlobalStyles = createGlobalStyle`  
*,  
*::before,  
*::after {  
margin: 0;  
padding: 0;  
box-sizing: border-box;  
}  
  
body {background-color: antiquewhite;  
margin: 0;  
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',  
'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',  
sans-serif;  
-webkit-font-smoothing: antialiased;  
-moz-osx-font-smoothing: grayscale;  
}  
`
```
- и его импорт в index.tsx в качестве компонента после компонента App
### Переменные 
1. Создаем в папке styles => файл Theme.styled.tsx
```
export const Theme = {  
	colors: {  
	primary: 'gold',  
	secondary: 'pink',  
	gray: {  
			dark: '#898989',  
			light: '#dcdcdc'  
		},  
	},  
}
```
2. В index.tsx оборачиваем тегом ThemeProvider, где в атрибуте указываем theme = "название нашей темы"
```
root.render(  
	<ThemeProvider theme={MyTheme}>  
		<App/>  
		<GlobalStyles/>  
	</ThemeProvider>  
);
```
3. можем использовать в качестве атрибутов в тегах компонентов 
```
<StyledBtn btnType={'outlined'} color={MyTheme.colors.secondary}>Hello</StyledBtn>
```

### Для чего использовать переменные
- цвета
- настройки кнопки 
- breakpoints


---
### Zero-Links
[[00 StyledComponents]]
[[00 React]]
[[00 Программирование]]

---
### Links
[[Props]]
[[Атрибут .attr]]