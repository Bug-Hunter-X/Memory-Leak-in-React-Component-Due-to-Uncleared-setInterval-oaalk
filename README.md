# React setInterval Memory Leak
This example demonstrates a common error in React: using setInterval within useEffect without properly clearing the interval.  This leads to a memory leak because the interval continues to run even after the component unmounts.

The `bug.js` file contains the erroneous code, while `bugSolution.js` provides a corrected version.

## Problem
The initial implementation uses `setInterval` to update a counter every second. However, it fails to clear the interval using `clearInterval` when the component unmounts, leading to a memory leak.

## Solution
The corrected version uses the return value of `setInterval` to store the interval ID.  This ID is then used in the cleanup function returned by `useEffect` to clear the interval before the component unmounts, preventing the memory leak.