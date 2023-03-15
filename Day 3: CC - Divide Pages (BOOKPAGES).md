PROBLEM 
Chef has N books such that ith book has Ai pages. He wants to divide all the books between Alice and Bob such that:

Both Alice and Bob get at least one book;
The number of pages allotted to Alice and Bob are either both odd or both even.
Find whether such distribution exists.

Input Format
The first line of input will contain a single integer 
T, denoting the number of test cases.
Each test case consists of multiple lines of input.
The first line of each test case contains a single integer 
N — the number of books.
The next line contains 
N space-separated integers, where the 
ith integer denotes the number of pages in the ith book.

Output Format
For each test case, output on a new line, YES, if a valid distribution exists. Otherwise, print NO.

You can print each character in uppercase or lowercase. For example, NO, no, No, and nO, are all considered the same.

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
  // taking number of test cases as input  
  int t;
    cin >> t;
    while(t--) {
        int n;
        cin >> n;
        int a[n];
        int sum = 0;
      // taking array elements as input and calculating their sum
        for(int i=0; i<n; i++) {
            cin >> a[i];
            sum += a[i];
        }
      // the sum of elements has to be even as per the given condition
        if(sum % 2 != 0) {
            cout << "NO" << endl;
            continue;
        }
      // calculating the count of even and odd elements in the array
        int countEven = 0, countOdd = 0;
        for(int i=0; i<n; i++) {
            if(a[i] % 2 == 0) {
                countEven++;
            } else {
                countOdd++;
            }
        }
      // as per the given conditions, both count of even or odd elements has to be 0
        if(countEven == 0 || countOdd == 0) {
            cout << "YES" << endl;
            continue;
        }
    }
    return 0;
}
```
