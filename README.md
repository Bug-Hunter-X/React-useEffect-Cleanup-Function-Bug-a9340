# React useEffect Cleanup Function Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook: forgetting to return a cleanup function to remove event listeners or other side effects when a component unmounts.  This can lead to memory leaks and unexpected behavior.

## Bug Description
The `MyComponent` component adds an event listener (`keydown`) within the `useEffect` hook. However, it lacks a cleanup function (returned from `useEffect`) to remove this listener when the component is unmounted.  This means that the listener remains active even after the component is no longer rendered, potentially causing issues.

## How to Reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe that event listeners remain attached even after unmounting the component (you can verify using your browser's developer tools).

## Solution
The solution involves adding a cleanup function within `useEffect` to remove the event listener when the component is unmounted. This function is returned from the `useEffect` callback. 