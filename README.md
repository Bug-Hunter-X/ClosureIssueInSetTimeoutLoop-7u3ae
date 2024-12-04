# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common closure-related issue in JavaScript when using `setTimeout` within a loop.  The expected behavior is to print numbers 0 through 9 with a one-second delay between each. However, due to the way closures work in JavaScript, the output is unexpected.

## Problem Description

The problem arises because the `setTimeout` callback function doesn't create a new scope for the variable 'i' for each iteration. By the time `setTimeout` finally executes the callback, the loop has already completed, and 'i' holds its final value (9).

## Solution

The solution involves creating a new scope for each iteration of the loop, typically by using an Immediately Invoked Function Expression (IIFE) or using `let` within the loop itself which declares a block scope.