# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: an infinite loop caused by the absence of a cleanup function.  The component continuously updates, leading to an infinite render cycle and potentially crashing the application.

## Bug Description

The `MyComponent` uses `useEffect` to log the count whenever it changes. However, because it doesn't include a cleanup function (returned from `useEffect`), the effect runs continuously, triggering an infinite loop.  This causes the `count` to increment and the effect to trigger, over and over again.

## Solution

The solution involves adding a cleanup function to the `useEffect` hook to prevent the infinite loop. The cleanup function will be executed before the next effect runs. This allows us to control the behaviour and avoid the continuous render cycle.