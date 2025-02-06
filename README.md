# Stale Closures in React's useEffect Hook

This repository demonstrates a common error in React applications involving stale closures within the `useEffect` hook.  The provided code snippet showcases how incorrect usage of state variables inside `useEffect` can result in unexpected behavior and prevent proper updates.

## Problem

The primary issue lies in accessing the `count` state variable directly within the `setInterval` callback function. Because the callback is created during the initial render, it maintains a reference to the initial value of `count`, rather than the updated value. This leads to the counter not incrementing properly.

## Solution

The solution utilizes the functional update form of `setCount` which guarantees that the update uses the latest state value.