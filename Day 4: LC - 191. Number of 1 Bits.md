Write a function that takes the binary representation of an unsigned integer and returns the number of '1' bits it has (also known as the Hamming weight).

Note:

Note that in some languages, such as Java, there is no unsigned integer type. In this case, the input will be given as a signed integer type. It should not affect your implementation, as the integer's internal binary representation is the same, whether it is signed or unsigned.
In Java, the compiler represents the signed integers using 2's complement notation. Therefore, in Example 3, the input represents the signed integer. -3.
 

Example 1:

Input: n = 00000000000000000000000000001011
Output: 3
Explanation: The input binary string 00000000000000000000000000001011 has a total of three '1' bits.
Example 2:

Input: n = 00000000000000000000000010000000
Output: 1
Explanation: The input binary string 00000000000000000000000010000000 has a total of one '1' bit.
Example 3:

Input: n = 11111111111111111111111111111101
Output: 31
Explanation: The input binary string 11111111111111111111111111111101 has a total of thirty one '1' bits.
 

Constraints:

The input must be a binary string of length 32.
 
 
 ```cpp
class Solution {
public:
    int hammingWeight(uint32_t n) {
        int count=0;
        // we use a while lloop to travel through 32 bit integer string n
        while(n!=0){
            // we do AND operation of each bit with 1, if that is TRUE; we increase count
            if(n&1){
                count++;
            }
            // by using right shift operator with 1, we "SHIFT 1 BIT TOWARDS RIGHT" in n and check again
            n= n>>1;
        }
        return count;
    }
};
```


INSIGHTS:
This question was totally new for me as by solving this question I came to know about the datatype "BIT_STRINGS" usch as uint_32t, uint_64t, uint_8t;
Earlier I had only known of the common dtatypes like int, float, double, long long, etc.
That's why I had to refer solution to solve this question as my first approach was to convert this binary string to actual string or vector int and then count the number of ccurences of 1 in it,
C had a function to do so called "sprintf" or "snprintf" in which we had to specify "%u" or "%lu" as datatype to do so-
it was like this: snprintf(str, sizeof str, "%lu", (unsigned long)n);
snprintf(str, sizeof str, "%" PRIu32, n);
 unsigned char buf[4];
 
        /* pack into buf string */
        buf[0] = x >> 24;
        buf[1] = x >> 16;
        buf[2] = x >> 8;
        buf[3] = x;
 
        /* convert the string back to a uint32_t */
        y = (buf[0] <<  24) | (buf[1] << 16) | (buf[2] << 8) | buf[3];
        
It went over my head, seriously!
But now that I get it, I will remember it!
 
