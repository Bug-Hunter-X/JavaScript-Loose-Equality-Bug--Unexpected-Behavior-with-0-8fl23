# JavaScript Loose Equality Bug

This repository demonstrates a common, yet subtle, bug in JavaScript related to the loose equality (==) operator and type coercion.  The bug arises when checking for null or undefined values, as the comparison behaves unexpectedly with the number 0.

## Bug Description

The provided JavaScript function `foo` attempts to handle cases where the first argument (`a`) might be null. If `a` is null, it should return the second argument (`b`). However, due to loose equality, when `a` is 0, the condition `a == null` evaluates to true, incorrectly returning `b` even when a numerical value is expected.

## Bug Solution

The solution uses strict equality (===) to accurately check for null or undefined values without type coercion.  This prevents the unexpected behavior with the number 0.

## How to reproduce the bug

1. Clone this repository.
2. Run `bug.js` using Node.js (or a similar JavaScript environment).
3. Observe the unexpected output when calling `foo(0, 10)`. The function should return 10, but with loose equality, it returns 10 incorrectly.  Using strict equality (===), the result would be correct (10).

## How to fix the bug

1. Replace the loose equality (==) with strict equality (===) in the if condition.
2. Run `bugSolution.js` to see how the correct behaviour should be.