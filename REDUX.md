# redux

## 1. Is it possible to trigger a Redux action outside a component?

In order to dispatch and action outside of the scope of a `React.Component` you need to get the store instance and call `dispatch` on it like:

```js
import { store } from './path/to/createdStore'

function testAction(text) {
  return {
    type: 'TEST_ACTION',
    text
  }
}

store.dispatch(testAction('test'))
```
