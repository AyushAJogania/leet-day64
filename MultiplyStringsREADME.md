# leet-day64

## Problem Description

You are given two non-negative integers `num1` and `num2`, represented as strings. Your task is to calculate and return the product of these two numbers, also represented as a string. You must not use any built-in BigInteger library or convert the inputs to integers directly.

## Approach

To multiply two numbers represented as strings, we can implement the long multiplication algorithm, similar to how we would do it by hand. Here's a step-by-step explanation of the approach used in the provided solution:

1. Initialize a vector `result` to store the digits of the result. The maximum length of the result is the sum of the lengths of `num1` and `num2`.

2. Iterate through `num1` and `num2` in reverse order using nested loops. For each pair of digits, calculate their product and add it to the corresponding position in the `result` vector.

3. After calculating all the products, go through the `result` vector to handle any carry-over and convert it to a string.

4. Return the final result as a string.

## Example

### Input:

```
num1 = "123", num2 = "456"
```

### Output:

```
"56088"
```

## Constraints

- 1 <= `num1.length`, `num2.length` <= 200
- `num1` and `num2` consist of digits only.
- Both `num1` and `num2` do not contain any leading zero, except the number 0 itself.

## Implementation

The solution is implemented in C++ using standard library functions and data structures.

## How to Use

You can use this C++ function to multiply two large numbers represented as strings without relying on built-in BigInteger libraries. To use it, follow these steps:

1. Include the necessary headers:

```
#include <string>
#include <vector>
```

2. Define your `num1` and `num2` as string variables.

3. Create an instance of the `Solution` class:

```
Solution solution;
```

4. Call the `multiply` method with your `num1` and `num2` as arguments:

```
std::string result = solution.multiply(num1, num2);
```

5. The `result` variable now contains the product of `num1` and `num2` as a string.

## Complexity Analysis

- Time complexity: O(m * n), where m and n are the lengths of `num1` and `num2`, respectively. This is because we perform multiplication digit by digit.
- Space complexity: O(m + n), as we create a `result` vector to store the digits of the product.

This solution efficiently multiplies large numbers represented as strings and returns the result as a string, meeting the constraints of the problem statement.
