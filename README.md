---
# react-hooks
useEffect Hooks 
it has two parameter a call back function  and a dependency array in this hooks we pass things in it if there is change in these function that you  would write in the useEffect if you doing anything to these then useEffect update the page  if there is any chnge in the useEFect a function are variable that are defined in the useEffect it update the page.
Example:
const [count, setCount] = useState(0);

useEffect(() => {
  console.log(`Count is now: ${count}`);
}, [count]);

useRef Hook:
used for reference to object like the user want to copy only the input text so the input and the copy button are not joint so if the copy button its on the end of the page we reference the input value we pass a variable reference that we define for useRef and in the button we call a function like onclick =copyimage so the input referecne the  we an use the useRef hook in callback 
useRef is a React Hook that lets you reference a value that’s not needed for rendering.
const ref = useRef(initialValue)
Usage
Referencing a value with a ref
Manipulating the DOM with a ref
Avoiding recreating the ref contents
import { useRef } from 'react';

export default function Counter() {
  let ref = useRef(0);

  function handleClick() {
    ref.current = ref.current + 1;
    alert('You clicked ' + ref.current + ' times!');
  }

  return (
    <button onClick={handleClick}>
      Click me!
    </button>
  );
}

useCallback():
its like memoization cache to store value so when the browser re-render it contain some values
Memoizes a function definition
React useCallback() is a hook that memoizes a function definition and ensures its referential integrity between re-renders of a React component. It works by accepting the function as an argument, memoizing it, and then returning the memoized function.
syntax:
const cachedFn = useCallback(fn, dependencies)
it has two paramter a function that hold value for cache and the dependency variable when these variable changes the cache also change
example:
function ProductPage({ productId, referrer, theme }) {
  // Tell React to cache your function between re-renders...
  const handleSubmit = useCallback((orderDetails) => {
    post('/product/' + productId + '/buy', {
      referrer,
      orderDetails,
    });
  }, [productId, referrer]); // ...so as long as these dependencies don't change...

  return (
    <div className={theme}>
      {/* ...ShippingForm will receive the same props and can skip re-rendering */}
      <ShippingForm onSubmit={handleSubmit} />
    </div>
  );
}


useID:
The useId hook in React is a built-in hook introduced in React 18. It is used to generate unique IDs that are stable across server and client rendering, making it particularly useful for accessibility attributes like id and htmlFor in forms or other components.

Here’s a quick overview and example of how to use it:

Key Features of useId:
Unique and Stable IDs: Ensures IDs are unique within the app and consistent between server and client.
Avoids Collisions: Prevents ID collisions when rendering multiple components.
Useful for Accessibility: Ideal for linking labels to inputs or other accessibility-related attributes.
Basic Example:

Copy the code
import React, { useId } from 'react';

function FormComponent() {
  const id = useId();

  return (
    <div>
      <label htmlFor={`${id}-input`}>Enter your name:</label>
      <input id={`${id}-input`} type="text" />
    </div>
  );
}

export default FormComponent;
Explanation:

useId generates a unique ID (e.g., :r0:).
The ID is appended with a suffix (e.g., -input) to create a unique identifier for the input field.
Example with Multiple IDs:

Copy the code
import React, { useId } from 'react';

function MultiFieldForm() {
  const id = useId();

  return (
    <form>
      <div>
        <label htmlFor={`${id}-email`}>Email:</label>
        <input id={`${id}-email`} type="email" />
      </div>
      <div>
        <label htmlFor={`${id}-password`}>Password:</label>
        <input id={`${id}-password`} type="password" />
      </div>
    </form>
  );
}

export default MultiFieldForm;
Explanation:

The same id is reused with different suffixes (-email, -password) to create unique IDs for multiple fields.
When to Use useId:
For accessibility: Linking labels to inputs.
In server-side rendering (SSR): Ensures IDs are consistent between server and client.
To avoid manual ID management: Especially in reusable components.
Important Notes:
Do not use useId for dynamic or frequently changing IDs (e.g., list keys). Use useState or other methods for such cases.
Requires React 18 or later.
This hook simplifies managing unique IDs, especially in complex or reusable components!
import React, { useId } from 'react';

function FormComponent() {
  const id = useId();

  return (
    <div>
      <label htmlFor={`${id}-input`}>Enter your name:</label>
      <input id={`${id}-input`} type="text" />
    </div>
  );
}
export default FormComponent;



example:

Generating unique IDs for accessibility attributes 
Call useId at the top level of your component to generate a unique ID:

import { useId } from 'react';

function PasswordField() {
  const passwordHintId = useId();
  // ...
You can then pass the generated ID to different attributes:

<>
  <input type="password" aria-describedby={passwordHintId} />
  <p id={passwordHintId}>
</>
###React Libraries
https://www.reactbits.dev/components/model-viewer  React Bits 
http://velocityjs.org/                             Velocity js
https://react-spring.dev/                          React-Spring
https://ui.aceternity.com/                         Accertinity UI
https://gsap.com/scroll/                           GSAP
[https://www.npmjs.com/package/@lynx-js/react](https://lynxjs.org/)       LYNX
https://threejs.org/                               Three.js
https://mui.com/material-ui/                       Material UI
https://animejs.com/                               AnimeJS
https://mantine.dev/                               Mantime Dev
https://daisyui.com/                               Daisy UI
https://huntscreens.com/en/products/lynx
---
