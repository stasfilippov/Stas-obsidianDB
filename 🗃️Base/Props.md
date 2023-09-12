202308182028
Tags: #progr 

---
## Что это??
 - это **объект**, собирающий **все атрибуты**, которые мы указали **в теге компонента** в родителе в виде **key={value}**
 - управляются из вне 
 - доступ в ребенке получаем в виде -> **props.key = value**
 - props - активно влияют на JSX

### Props в StyledComponents
- те в зависимости от атрибута = props -> будет обрисовываться соответствующие стили для компонента
```
${props => props.color}
```

- если не приходит ничего -> указываем по default
```
background-color: ${props => props.color || "pink"};
```
- необходимо типизировать все атрибуты, которые придут в компоненту
```
export const StyledBtn = styled.button<fontSizePropsType>`
```
- обязательно указываем, что они могут и не приходить
```
type fontSizePropsType = {  
fontSize?: string,  
color?: string  
}
```
### Применение нескольких свойств по одному атрибуту
- когда существует две кнопки -> сначала:
1. делаем общие стили для кнопки 
2. потом для каждой отдельные стили
```
export const StyledBtn = styled.button<fontSizePropsType>`  
border: none;  
padding: 18px 20px;  
border-radius: 5px;  
font-size: ${props => props.fontSize || '2rem'};  
font-weight: bold;  
  
&:hover {  
background-color: #f55f6f;  
}  
  
${props => props.outlined && css<fontSizePropsType>`  
border: 2px solid ${props => props.color || "pink"};  
color: ${props => props.color || "pink"};  
background-color: transparent;  
  
&:hover {  
border-color: #f55f6f;  
background-color: transparent;  
color: #f55f6f;  
}  
`} //outlined  
${props => props.primary && css <fontSizePropsType>`  
background-color: ${props => props.color || "pink"};  
color: snow;  
`}  
`
```

---
### Zero-Links
-[[00 React]]

---
### Links
