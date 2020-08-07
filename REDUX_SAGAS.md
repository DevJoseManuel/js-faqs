# redux-sagas

## 1. How do I access the redux state inside a saga?

`redux-sagas` exposes a very useful API [select()](https://redux-saga.js.org/docs/api/#selectselector-args) to invoke a `selector` on the state for getting some part of it available inside the saga.

A simple implementation example could be:

```javascript
import { select } from 'redux-saga/effects'

/*
 * Selector. The query depends by the state shape.
 */
export const getProject = state => state.project

// Saga
export function* saveProjectTask() {
  // Get the project
  let project = yield select(getProject) 
  // ...
}
```
