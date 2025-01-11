# React setInterval Memory Leak

This repository demonstrates a common error in React applications involving the use of `setInterval` within the `useEffect` hook, leading to a memory leak.  The provided solution corrects this issue.

## Bug Description
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it fails to clear the interval when the component unmounts, resulting in a memory leak.

## Solution
The `bugSolution.js` file shows the corrected version.  The key change is the inclusion of a cleanup function returned from the `useEffect` callback. This cleanup function clears the interval using `clearInterval` when the component is unmounted, preventing the memory leak.

## How to reproduce
1. Clone the repository.
2. Navigate to the project directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe the increasing counter.  The original buggy version will continue incrementing even after unmounting the component. The corrected solution will not.
