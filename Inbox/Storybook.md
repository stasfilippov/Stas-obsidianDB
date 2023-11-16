202311162303
Tags: #progr 

---
## Содержание
https://storybook.js.org/

--- 
### Установка
1. `npx storybook@latest init` 
2. eslint для strorybook `yarn add eslint-plugin-storybook --dev`

**Обязательно в компоненте**
```JS
// Button.stories.ts|tsx 
import type { Meta } from '@storybook/react'; 
import { Button } from './Button'; 

const meta: Meta<typeof Button> = { component: Button, }; 

export default meta;
```

- Обязательно нужно экспортировать одну **story** - какое либо состояние компонента

---
### Zero-Links
[[00 Srorybook]]
[[00 React]]

---
### Links
