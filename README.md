# React 19 useEffect Hook Memory Leak

This repository demonstrates a common error in React 19's `useEffect` hook that can lead to memory leaks. The `setInterval` function is started in the effect but never stopped, leading to continuous updates even after the component is unmounted.

## Bug
The `bug.js` file contains the faulty component.  The `setInterval` lacks a cleanup function resulting in a memory leak.

## Solution
The `bugSolution.js` file shows the corrected component. A cleanup function is implemented using the return statement in `useEffect` to clear the interval when the component unmounts, thus preventing the memory leak.

## How to reproduce
1. Clone this repository.
2. Navigate to the directory.
3. Run `npm install`.
4. Run `npm start`. Observe the counter increasing even after navigating away from the component. Then compare the performance after fixing the bug.