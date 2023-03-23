Given an integer x, return true if x is a 
palindrome
, and false otherwise.

 

Example 1:

Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
Example 2:

Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
Example 3:

Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
 

Constraints:

-231 <= x <= 231 - 1
 

Follow up: Could you solve it without converting the integer to a string?


```cpp
class Solution {
public:
    bool isPalindrome(int x) {
        int flag=0;
        int n=x;
        long long temp=0;
        // negative numbers are not palindromes
        if(x<0){
            return false;
        }
        // STAR METHOD - TO REDUCE TIME COMPLEXITY - CHECK! Increase temp and decrease num 
        while(n!=0){
            temp = temp*10 + n%10;
            n/=10;
        }
        if(temp==x){
            flag=1;
        }
        return flag;
    }
};
```
