# React useEffect Hook Memory Leak with setInterval

This example demonstrates a common mistake when using the `useEffect` hook with `setInterval` in React.  Forgetting to return a cleanup function from `useEffect` leads to memory leaks.

## Bug
The `bug.js` file contains a component that uses `setInterval` to update a counter every second.  However, it lacks a cleanup function to clear the interval when the component unmounts, resulting in the interval continuing to run indefinitely, even after the component is no longer needed.

## Solution
The `bugSolution.js` file corrects this issue by including a return statement in the `useEffect` hook that uses `clearInterval` to clear the interval when the component unmounts.