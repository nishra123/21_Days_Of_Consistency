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


```cpp
class Solution {
public:
    vector<int> plusOne(vector<int>& digits) {
        int n = digits.size();
        // Initialize a variable carry to 1, which represents the carry from the previous digit
        int carry = 1;
        // we traverse vector from least significant to most significant digit (from l to r in reverse order)
        for (int i = n - 1; i >= 0; i--) {
            // For each digit, add the carry to it, and update the digit to the result modulo 10. This gives us the digit for the incremented number at this position.
            int sum = digits[i] + carry;
            digits[i] = sum % 10;
            // Update the carry to the result divided by 10. This gives us the carry to be propagated to the next digit.
            carry = sum / 10;
            // If the carry becomes zero, we can stop iterating, because we don't need to propagate any further carries. 
            if (carry == 0) {
                break;
            }
        }
        // If the loop finishes and the carry is not zero, we need to add a new digit to the beginning of the vector, with the value of the carry.
        if (carry != 0){
            digits.insert(digits.begin(), carry);
        }
        return digits;
    }
};
```

INSIGHTS  - I tried this question way too many times and every time used to get runtime error as constraints were large and method I was using was to first convert given vector to an integer by using while loop - which exceeded the long long datatype. Thus, at last I decided to take help from chatgpt and it provided me with simple soltion, compared to the ones I saw on leetcode discussions and solutions tab I guess. If you have any simpler solution or better approach than this, please let me know!
