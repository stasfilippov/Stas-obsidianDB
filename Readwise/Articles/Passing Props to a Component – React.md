![rw-book-cover](https://readwise-assets.s3.amazonaws.com/static/images/article3.5c705a01b476.png)

## Metadata
- Author: [[react.dev]]
- Full Title: Passing Props to a Component – React
- Category: #articles
- URL: https://react.dev/learn/passing-props-to-a-component

## Highlights
- If you want to give a prop a default value to fall back on when no value is specified, you can do it with the destructuring by putting = and the default value right after the parameter:
- When you nest content inside a JSX tag, the parent component will receive that content in a prop called children.
- You can think of a component with a children prop as having a “hole” that can be “filled in” by its parent components with arbitrary JSX. You will often use the children prop for visual wrappers: panels, grids, etc.
- a component may receive different props over time. Props are not always static!
- Props reflect a component’s data at any point in time, rather than only in the beginning.
- props are immutable—a term from computer science meaning “unchangeable”.
- When a component needs to change its props (for example, in response to a user interaction or new data), it will have to “ask” its parent component to pass it different props—a new object! Its old props will then be cast aside, and eventually the JavaScript engine will reclaim the memory taken by them.
    - Note: Взаимодействие дочернего компонента и родительского при получении динамических props
- Don’t try to “change props”.
- To read props, use the function Avatar({ person, size }) destructuring syntax.
  You can specify a default value like size = 100, which is used for missing and undefined props.
