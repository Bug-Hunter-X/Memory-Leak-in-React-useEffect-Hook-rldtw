# React useEffect Hook Memory Leak

This repository demonstrates a common mistake in React's `useEffect` hook that can lead to memory leaks.  The example shows a component that uses `setInterval` to update a counter, but fails to correctly clean up the interval when the component unmounts.

## Bug Description

The `useEffect` hook, without a return function, creates a memory leak because the `setInterval` continues to run even after the component is unmounted from the DOM. This results in unnecessary memory usage and can degrade application performance.

## Solution

The solution involves adding a return function to the `useEffect` hook that clears the interval when the component unmounts. This ensures that the interval is stopped when it's no longer needed.