# React Native: Stale Closures in useCallback with Async Operations

This repository demonstrates a subtle bug in React Native related to the `useCallback` hook when used with asynchronous operations.  Improper use can lead to stale closures, resulting in functions using outdated values.

## Bug Description
The `useCallback` hook is used to memoize a function that fetches data asynchronously.  Due to the way closures work, if the memoized function's dependencies change between renders, the function still uses the old values.

## How to Reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run `npx react-native run-android` (or equivalent for iOS).
4. Observe that the fetched data does not reflect the latest value of the `count` state.

## Solution
The solution involves restructuring the code so that asynchronous operations always reference the latest values.

## Bug and Solution Files
* `bug.js`: Shows the code with the bug.
* `bugSolution.js`: Provides the corrected code.