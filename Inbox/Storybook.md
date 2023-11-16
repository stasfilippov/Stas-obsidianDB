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

### Setup Controls
```ts
export default meta;
type Story = StoryObj<typeof Button>;


export const Primary: Story = {
  args: {
    variant: 'primary',
  },
};
```
- указываем какие **props** будут приходить в компоненту
- ![[Pasted image 20231116234718.png]]- способны управлять и тестировать состояние компонента
---
### Zero-Links
[[00 Srorybook]]
[[00 React]]

---
### Links
