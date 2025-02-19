# React useEffect Infinite Loop Bug
This repository demonstrates a common error in React's `useEffect` hook:  forgetting to include state variables in the dependency array. This leads to an infinite render loop.

## Bug Description
The `MyComponent` function uses `useState` to manage a counter. The `useEffect` hook logs the count to the console.  The problem is that `count` is missing from the dependency array. As a result, the effect runs after every render, causing a new state update which in turn triggers another render, creating an infinite loop.

## Bug Solution
Adding `count` to the dependency array fixes the issue. This ensures the effect only runs when the `count` value changes.