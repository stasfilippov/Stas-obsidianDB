![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article0.00998d930354.png)

## Metadata
- Author: [[react.dev]]
- Full Title: Rendering Lists – React
- Category: #articles
- URL: https://react.dev/learn/rendering-lists

## Highlights
- Arrow functions implicitly return the expression right after =>, so you didn’t need a return statement:
- However, you must write return explicitly if your => is followed by a { curly brace!
- Arrow functions containing => { are said to have a “block body”. They let you write more than a single line of code, but you have to write a return statement yourself. If you forget it, nothing gets returned!
- Вам необходимо присвоить каждому элементу массива a key— строку или число, которое однозначно идентифицирует его среди других элементов этого массива
- Правильно выбранный вариант keyпомогает React понять, что именно произошло, и внести правильные обновления в дерево DOM.
- Короткий синтаксис <>...</>Fragment не позволит вам передать ключ, поэтому вам нужно либо сгруппировать их в один <div>, либо использовать немного более длинный и более явный <Fragment>синтаксис:
    - Note: Может быть использован, когда при помощи map мы отрисовываем не один элемент, а несколько. При этом key мы навешиваем на специальную обертку от React, которая при рендеринге исчезает
- используйте увеличивающийся счетчик crypto.randomUUID()или пакет, как uuidпри создании элементов.
    - Note: Используются при получении данных сервера без id
- Ключи должны быть уникальными среди братьев и сестер. Однако можно использовать одни и те же ключи для узлов JSX в разных массивах.
  Ключи не должны меняться , иначе это противоречит их назначению! Не генерируйте их во время рендеринга.
- не генерируйте ключи на лету, например, с помощью key={Math.random()}. Это приведет к тому, что ключи никогда не будут совпадать между рендерингами, что приведет к тому, что все ваши компоненты и DOM будут каждый раз пересоздаваться.
