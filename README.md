# React useEffect setInterval Memory Leak
This repository demonstrates a common error in React applications: memory leaks caused by improper usage of `setInterval` within the `useEffect` hook.

The `bug.js` file contains a component with an `useEffect` hook that uses `setInterval` to update the state. However, it fails to clear the interval before the component unmounts, resulting in a memory leak. 

The `bugSolution.js` file provides a corrected version that includes a cleanup function to clear the interval when the component unmounts, preventing the memory leak.

## How to reproduce the bug
1. Clone this repository
2. Navigate to the repository's directory in the terminal
3. Run `npm install` to install the dependencies
4. Run `npm start` to start the development server
5. Open your browser and navigate to `http://localhost:3000`
6. Observe the counter incrementing every second
7. Open your browser's developer tools and check the console for any memory leaks or warnings

## How to fix the bug
Refer to the code in `bugSolution.js` to see the corrected implementation. Key change is to include a cleanup function inside the useEffect hook that calls `clearInterval`. This function will clear the interval when the component unmounts, preventing the memory leak.