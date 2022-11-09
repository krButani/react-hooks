# React Hooks

# useState()

* The React useState Hook allows us to track state in a function component.
```

import { useState } from 'react'

let { count, setCount } = useState(0); 

// define variable in {} So, you can define only number,string,boolean variables

let [ arr, setArr ] = useState([]);
let [ obj, setObj ] = useState({});

// define variable in [] So, you can define all type of variable only

// best things is you can use []

```

[useState() Example](https://www.w3schools.com/react/react_usestate.asp)

[useState() Video Tutorial](https://www.youtube.com/watch?v=CABs284dEpQ)

[useState() with array Video Tutorial](https://www.youtube.com/watch?v=MQ7H4TpgXsQ)

---
# useEffect()

* useEffect runs on every render. That means that when the count changes, a render happens, which then triggers another effect.
* 3 types

### 1. No dependency passed:
```
useEffect(() => {
  //Runs on every render
});
// it execute every time when state or component change.
```

### 2. An empty array:
```
useEffect(() => {
  //Runs only on the first render
}, []);

// its run only first time when component is load.
```

### 3. Props or state values:
```
useEffect(() => {
  //Runs on the first render
  //And any time any dependency value changes
}, [prop, state]);

// pass variable or function on [], when every that variable or function changed that time useEffect function is called.
```
[useEffect() Example](https://www.w3schools.com/react/react_useeffect.asp)

[useEffect() Video Tutorial](https://www.youtube.com/watch?v=5gCtW7RCtQA)

---
# useRef()

* The useRef Hook allows you to persist values between renders.

### 2 type
1. Does Not Cause Re-renders
   * It can be used to store a mutable value that does not cause a re-render when updated.

```
const count = useRef(0); 
// you can define variable and if you try to change value component is not re-render. 



```
2. Accessing DOM Elements
   * It can be used to access a DOM element directly.

[useRef() Example](https://www.w3schools.com/react/react_useref.asp)

[useRef() Video Tutorial](https://www.youtube.com/watch?v=qv2YPOnDwvA)

---

# useMemo()

* This can improve performance.

```

const [count, setCount] = useState(0);
const calculation = useMemo(() => expensiveCalculation(count), [count]);

const expensiveCalculation = (num) => {
  console.log("Calculating...");
  for (let i = 0; i < 1000000000; i++) {
    num += 1;
  }
  return num;
};

```
[useMemo() Example](https://www.w3schools.com/react/react_usememo.asp)

[useMemo() Video Tutorial](https://www.youtube.com/watch?v=5uiv8MFD1rc)

---

# useContext()

* React Context is a way to manage state globally.
* It can be used together with the useState Hook to share state between deeply nested components more easily than with useState alone.

```
import { useState, createContext } from "react";
import ReactDOM from "react-dom/client";
const UserContext = createContext()

function Component1() {
  const [user, setUser] = useState("Jesse Hall");

  return (
    <UserContext.Provider value={user}>
      <h1>{`Hello ${user}!`}</h1>
      <Component2 user={user} />
    </UserContext.Provider>
  );
}

```

```
import { useState, createContext, useContext } from "react";
function Component5() {
  const user = useContext(UserContext);

  return (
    <>
      <h1>Component 5</h1>
      <h2>{`Hello ${user} again!`}</h2>
    </>
  );
}
```

[useContext() Example](https://www.w3schools.com/react/react_usecontext.asp)

[useContext() Video Tutorial](https://www.youtube.com/watch?v=kSIm78jmqhE)

---

# useReducer()

* The useReducer Hook is similar to the useState Hook.

* It allows for custom state logic.

* If you find yourself keeping track of multiple pieces of state that rely on complex logic, useReducer may be useful.

#### Syntax

```useReducer(<reducer>, <initialState>)```

[useReducer() Example](https://www.w3schools.com/react/react_usereducer.asp)

[useReducer() Video Tutorial](https://www.youtube.com/watch?v=VdXGIEYZuCw)

---

# useCallback()

* The React useCallback Hook returns a memoized callback function.
* Think of memoization as caching a value so that it does not need to be recalculated.
* This allows us to isolate resource intensive functions so that they will not automatically run on every render.
* The useCallback Hook only runs when one of its dependencies update.
* This can improve performance.


[useCallback() Example](https://www.w3schools.com/react/react_usecallback.asp)

[useCallback() Video Tutorial](https://www.youtube.com/watch?v=N62nXHTydpA)

---
# React Custom Hooks

[Custom Hooks Example](https://www.w3schools.com/react/react_customhooks.asp)

[Custom Hooks Video Tutorial](https://www.youtube.com/watch?v=ZyNWBiay5S4)
