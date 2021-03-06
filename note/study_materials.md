## Study links/references

### React & Redux
1. (korean) https://velopert.com
    - By velopert, a front-end developer based in South Korea
    - Explanations, Youtube links, etc.
2. (english) https://egghead.io/ :egg:
    - Good to learn JS frameworks and libraries
    - Focused on tutorial videos
3. (english) https://medium.com/dailyjs/when-do-i-know-im-ready-for-redux-f34da253c85f
    - Good to understand what Redux does in a nutshell
4. (english) Udemy courses, https://www.udemy.com/react-2nd-edition
    - Lots of courses for newbies at a cheap price
5. (korean) INF LEARN courses, https://www.inflearn.com/
    - Various video tutorials
    - nomad-coder : https://academy.nomadcoders.co/
        - pretty good to follow along 
        - did not go through the functions that I wanted to try out, ex) react-router


## Study notes
### :star: React-Router (not react-router-redux)
My demo: https://github.com/poscoict-arvrmr/edit-boilerplate
- Containers folder
- Components folder
- routes.js file

#### When you want to create a new page called xxx

  1. Create xxx.js file on /app/componetnts folder
    - This file should include all the components you want to draw in the page
    - Create xxx.css file (if needed), and import xxx.css inside xxx.js 
  2. Create xxx.js file on /app/containers folder
    - This file makes xxx as a page
    - Should import app/components/xxx.js
  3. Edit routes.js file
    - This file allows the page transition to happen (via hyperlink)
    - make sure you import /app/containers/xxx.js (not from /components folder)
    - Choose the path url names for xxx Page
  4. Make sure you use that xxx url you just defined in 'routes.js' in any other pages, when you want to redirect to xxx page via hyperlink or button..


### :star: Redux
#### Understanding what Redux is..
(thanks to https://medium.com/dailyjs/when-do-i-know-im-ready-for-redux-f34da253c85f , Udemy, velopert, and more)

Redux is a state container.

State means data.

State is changed by functions.

- Action: information about event :: static information about event that initiates state change
  - Dispatching action (1) --> Update state (2)

- Reducer: When action is dispatched, it is sent to REDUCER
  - Pure function, never mutates the store, returns same output

- Store: 'application state' stored as objects in STORE

#### example (courtesy of Udemy The Complete React: 2nd edition)

```
import { createStore } from 'redux';
    
// ACTION GENERATORS - functions that return action objects
const incrementCount = ({ incrementBy = 1 } = {}) => ({
  type: 'INCREMENT',
  incrementBy
});
const decrementCount = ({ decrementBy = 1 } = {}) => ({
  type: 'DECREMENT',
  decrementBy
});
const setCount = ({ count }) => ({
  type: 'SET',
  count
});

// REDUCERS
// 1. Reducers are pure functions
// 2. Never change state or actiton

const countReducer = (state = { count: 0 }, action) => {
  switch (action.type) {
    case 'INCREMENT':
      return {
        count: state.count + action.incrementBy
      };
    case 'DECREMENT':
      return {
        count: state.count - action.decrementBy
      };
    case 'SET':
      return {
        count: action.count
      };
      default:
      return state;
  }
};

const store = createStore(countReducer);
const unsubscribe = store.subscribe(() => {
  console.log(store.getState());
});

//DISPATCH
store.dispatch(incrementCount({ incrementBy: 5 }))
store.dispatch(incrementCount());
store.dispatch(decrementCount({ decrementBy: 10 }));
store.dispatch(setCount({ count: -100 }));
```


- ACTION GENERATORS: define functions that will be dispatched, declare any data parameters that will be used in each function
- DISPATCH: call the action (that are previously defined w/ ACTION GENERATOR)
- REDUCER: (switch/case/return chunk) see matching ACTION GENERATOR's [type: 'name'] --> REDUCER searches this 'name' within its switch loop --> matching ACTION GENERATOR function is executed --> returns the certain value

<b> DISPATCH ----> (ACTION GENERATORS) ------> REDUCER </b>


GREAT IMAGE TO UNDERSTAND THE BENEFIT OF REDUX:
https://cdn-images-1.medium.com/max/1000/1*f3gS9znOZvX8HfCLg7T--Q.gif


UI (user triggers something - mouse or button click) --> Dispatch action --> Reducer --> Store (change the state) --> UI (updates with new state)
