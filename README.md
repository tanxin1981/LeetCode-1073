# LeetCode-1073
## Solution
### Approach: Elementary Math
#### Intuition
Just like how you would sum two binary numbers on a piece of paper, we begin by summing the least-significant digits, which is the last element of *arr1* and *arr2*. Since each digit is **0** or **1**, summing two digits may "overflow". As for base **-2**, means carry will be negative. For example **11** + **1** = **0**. In this case, the last digits **1** + **1** = **2**, which is overflow, so we set the current digit of result to **0** and bring over the carry = **-1** to the next digit.
#### Algorithm
The pseudocode is as following:
- Initialize current digit to last element of *arr1* and *arr2*.
- Initialize carry to **0**.
- Loop through array *arr1* and *arr2* until you reach both *index* < **0** and *carry* = **0**.
- In the loop, calculate the sum of the two digits, let's call it *S*, which can only be **0** or **1** or **2**. Use a stack to store the result digit, which is the last digit of the sum *S*, and update carry with minus the first digit of the sum *S*.
- Loop stack to remove the leading **0** of the result.
- Reverse the stack to get the result array.

#### Complexity Analysis

- Time complexity : *O*(max(*m*, *n*)). Assume that *m* and *n* represents the length of *arr1* and *arr2* respectively, the algorithm above iterates at most max(*m*, *n*) + **1** times.

- Space complexity : *O*(max(*m*, *n*)). The length of two auxiliary array is at most **2** * max(*m*,*n*) .

