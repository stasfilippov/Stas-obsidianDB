202309121106
Tags: #progr #html 

---
## Виды svg иконок
 1. **Сплошные** 
	 - изменение с помощью изменения свойства **fill**
 2. **Линейные**
	- изменение с помощью изменения свойства **stroke**

### Использование svg - спрайтов 
- использование иконок по id 
- вставляем первую иконку как svg 
- вторую уже вставляем в теги `<g></g>` как группа
- задаем id в каждый тег `<g></g>`
- в теге `svg` используем тег `<use xlink:href = 'путь к спрайту#id иконки'></use>`

### Использование svg-спрайтов в React
- импортируем спрайт
- в атрибутах компонента передаем iconId
- в компоненте вставляем тег `svg` -> тег `<use xlinkHref={``${sprite}#${props.iconId=``}/>`
- типизируем iconId
---
### Zero-Links
[[00 HTML]]
[[00 React]]

---
### Links