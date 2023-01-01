- # useRef React Hook: Proper Usage
    - 1. React 18 must start with the following:
    - ```javascript
import React from 'react';
import { createRoot } from 'react-dom/client';
import './style.css';
import App from './App';

const root = createRoot(document.getElementById('root'));
root.render(<App />);
```
    - useRef returns a mutable ref object whose .current property is initialized to the passed argument (initialValue). The returned object will persist for the entire lifetime of the component.
    - One advantage useRef has over useState could be well stated as “the reference does not trigger a re-render, but in state, when state is updated it triggers a re-render.
    - It’s key to note that we can access anything in our component and set focus to an element. As it has been said forehand, I will go ahead and illustrate how to do that, but before then, I would like to point out two essential take-home keys for the useRef hook:
        - The value persists.
        - Updating the reference does not trip on a re-render.
    - This code using useState will be an infinite loop
    - ```javascript
import React, { useState, useEffect } from 'react';
function Render() {
  
  const [render, setrender]=useState();
  useEffect(()=>{
    setrender(prevrender=>prevrender+1)
  })
  console.log(render);
  
  return (
    <>
      <div>
        This component rendered= {render} times
      </div>
    </>
  
  )
};```
    - Let's fix that by using useRef
    - ```javascript
 const render = useRef(0);
  // current {0} =>

import React, { useRef, useEffect, useState } from 'react';
function Render() {
  const [age, setAge] = useState(20);
  const render = useRef(0)
  
  useEffect(() => {
    render.current = render.current + 1
  })
  function updateAge() {
    setAge(prevage => prevage + 1)
  }
  
  return (
    <>
      <div className='center'>
        <p>This site is strictly for adults ranging from 20-...</p>
        <p>you are {age} years old</p>
        <button onClick={updateAge}>set age</button>
        <p>This state rendered {render.current} times</p>
      </div>
  
    </>
  
  )
};
  
export default Render;```
- 
- 
- 
