### Study links/references

#### React & Redux
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


### Study notes
#### React-Router (not react-router-redux)
My demo: https://github.com/poscoict-arvrmr/edit-boilerplate
- Containers folder
- Components folder
- routes.js file

##### When you want to create a new page called xxx

  1. Create xxx.js file on /app/componetnts folder
    - This file should include all the components you want to draw in the page
    - Create xxx.css file if needed, and import .css inside .js 
  2. Create xxx.js file on /app/containers folder
    - This file makes xxx as a page
    - Should import app/components/xxx.js
  3. Edit routes.js file
    - This file allows the page transition to happen (via hyperlink)
    - make sure you import /app/containers/xxx.js (not from /components folder)
    - Choose the path url names for xxx Page
  4. Make sure you use that xxx url you just defined in 'routes.js' in any other pages when you want to redirect to xxx page via Link


#### Redux

##### Understanding what Redux is..

Redux is a state container.

State means data.

State is changed by functions.

- Action: information about event :: static information about event that initiates state change
  Dispatching action (1) --> Update state (2)

- Reducer: When action is dispatched, it is sent to REDUCER
  Pure function, never mutates the store, returns same output

- Store: 'application state' stored as objects in STORE


GREAT IMAGE TO UNDERSTAND THE BENEFIT OF REDUX:
https://cdn-images-1.medium.com/max/1000/1*f3gS9znOZvX8HfCLg7T--Q.gif


UI (user triggers something - mouse or button click) --> Dispatch action --> Reducer --> Store (change the state) --> UI (updates with new state)
