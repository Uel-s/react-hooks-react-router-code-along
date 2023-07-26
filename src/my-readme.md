# Learning Goals
1. Add react-router-dom to an existing React application
2. Create multiple client-side routes

## CODE ALONG

1. **To start using React Router, we need to install `react-router-dom`**,i the terminal.
`npm install react-router-dom@5`

2. In the index.js componet import;
  `import { BrowserRouter, Route } from "react-router-dom";`

  `follow this steps`
```js
  // Step 1. Import react-router functions

import { BrowserRouter, Route } from "react-router-dom";

function Home() {
  return (
    <div>
      <h1>Home!</h1>
    </div>
  );
}

// Step 2. Use <Route> components to define client-side routes in our app
function App() {
  return (
    <Route path="/">
      <Home />
    </Route>
  );
}

// Step 3. Use <BrowserRouter> component to wrap the entire application and provide React Router context features
ReactDOM.render(
  <BrowserRouter>
    <App />
  </BrowserRouter>,
  document.getElementById("root")
);
```
Inorder to switch in between paths in the same page we use  <switch> attribute.


```jsx
function App() {
  return (
    <Switch>
      <Route path="/about">
        <About />
      </Route>
      <Route path="/login">
        <Login />
      </Route>
      <Route path="/">
        <Home />
      </Route>
    </Switch>
  );
}
```
I put <Home> in the buttom since its our default display page.

**using <exact>**

this prop `exact` is used to go to a specific path when page loads.

```js
function App() {
  return (
    <Switch>
     
      <Route path="/about">
        <About />
      </Route>
      <Route path="/login">
        <Login />
      </Route>
      <Route exact path="/">
        <Home />
      </Route>
    </Switch>
  );
}
```
**NavLink and Link**

They replace <a>(anchour) in React.

DIfference between the two in `NavLink` one can add styling.
