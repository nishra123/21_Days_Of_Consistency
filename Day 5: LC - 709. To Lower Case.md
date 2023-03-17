Given a string s, return the string after replacing every uppercase letter with the same lowercase letter.

 

Example 1:

Input: s = "Hello"
Output: "hello"
Example 2:

Input: s = "here"
Output: "here"
Example 3:

Input: s = "LOVELY"
Output: "lovely"
 

Constraints:

1 <= s.length <= 100
s consists of printable ASCII characters.

```cpp
class Solution {
public:
    string toLowerCase(string s) {
        int i, n=s.length();
        for(i=0; i<n; i++){
            // uppercase characters have ASCII values from 65 to 90 while lowercase values have ASCII values from 97 to 122
            if(s[i]>=65 && s[i]<=90){
                s[i]+=32;
            }
        }
        return s;
    }
};
```

INSIGHTS: Whenever string appears in the question - keep ASCII as one of the options when no logic is working!
