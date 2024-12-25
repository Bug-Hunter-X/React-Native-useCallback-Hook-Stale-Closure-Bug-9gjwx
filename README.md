# React Native useCallback Hook Stale Closure Bug

This repository demonstrates a common bug in React Native applications involving the `useCallback` hook.  The bug arises from a stale closure, where a callback function references a variable whose value might change, but the callback itself isn't updated to reflect that change.

This issue typically leads to unexpected behavior, particularly when working with state updates or asynchronous operations.

## Bug Description

The `bug.js` file contains a simple component that uses the `useCallback` hook to create a function for incrementing a counter.  However, because the dependency array is empty, the callback doesn't update when the counter's value changes. This results in the counter always incrementing from its initial value, regardless of its current state.

## Solution

The `bugSolution.js` file provides a corrected version.  By including `count` in the dependency array of `useCallback`, we ensure the callback function is updated whenever the `count` variable changes, resolving the stale closure issue.