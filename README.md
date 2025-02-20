# React useEffect setInterval Memory Leak
This example demonstrates a common error in React applications: using setInterval within useEffect without proper cleanup, leading to memory leaks.  The component continues to update its state even after it has been unmounted, causing unexpected behavior and potentially performance issues.

## Problem
The `setInterval` function is used within the `useEffect` hook without a cleanup function.  This means that when the component unmounts, the interval continues to run, causing a memory leak.  In addition, attempting to update state after unmounting will not work. 

## Solution
The solution is to add a cleanup function to the `useEffect` hook that uses `clearInterval` to stop the interval when the component unmounts. 