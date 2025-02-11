# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React applications involving the `useEffect` hook.  The example shows an infinite loop caused by a missing dependency array in `useEffect`.

## Bug Description
The `useEffect` hook, when called without a dependency array, runs after every render. In this case, the `console.log` statement is executed repeatedly, and because the `count` changes, the component immediately re-renders again and again resulting in an infinite loop and potential performance issues.

## Bug Solution
The solution involves adding a dependency array to `useEffect`. This array specifies which values the effect should watch for changes. If any value in the array changes between renders, the effect will run again. If the array is empty (`[]`), the effect only runs after the initial render.