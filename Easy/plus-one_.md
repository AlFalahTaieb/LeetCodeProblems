# 66. Plus One

You are given a large integer represented as an integer array digits, where each digits[i] is the ith digit of the integer. The digits are ordered from most significant to least significant in left-to-right order. The large integer does not contain any leading 0's.

Increment the large integer by one and return the resulting array of digits.



Example 1:

Input: digits = [1,2,3]
Output: [1,2,4]
Explanation: The array represents the integer 123.
Incrementing by one gives 123 + 1 = 124.
Thus, the result should be [1,2,4].

Example 2:

Input: digits = [4,3,2,1]
Output: [4,3,2,2]
Explanation: The array represents the integer 4321.
Incrementing by one gives 4321 + 1 = 4322.
Thus, the result should be [4,3,2,2].

Example 3:

Input: digits = [9]
Output: [1,0]
Explanation: The array represents the integer 9.
Incrementing by one gives 9 + 1 = 10.
Thus, the result should be [1,0].



Constraints:

    1 <= digits.length <= 100
    0 <= digits[i] <= 9
    digits does not contain any leading 0's.



```typescript
function plusOne(digits: number[]): number[] {
  // Initialize a carry variable to 1
  let carry = 1;
  
  // Iterate over the input array of digits from right to left
  for (let i = digits.length - 1; i >= 0; i--) {
    // Add the carry to the current digit
    digits[i] += carry;
    
    // Check if the current digit has carried over to the next most significant digit
    carry = digits[i] > 9 ? 1 : 0;
    
    // Reduce the current digit to its single-digit representation
    digits[i] %= 10;
    
    // If the carry is zero, there is no need to continue iterating
    if (carry === 0) {
      return digits;
    }
  }
  
  // If the function completes the iteration without returning, it means that there is still a carry left over.
  // In this case, add a new digit to the most significant position using the unshift method, and return the resulting array.
  if (carry > 0) {
    digits.unshift(carry);
  }
  
  return digits;
}


```
