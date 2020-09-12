# algorithm-problems
A collection of algorithmic problems

## LeetCode

### Distinct Subsequences II

Given a string `S`, count the number of distinct, non-empty subsequences of `S`.

Since the result may be large, return the answer modulo `10^9 + 7`.

Example 1:
```
Input: "abc"
Output: 7
Explanation: The 7 distinct subsequences are "a", "b", "c", "ab", "ac", "bc", and "abc".
```

Example 2:
```
Input: "aba"
Output: 6 Explanation: The 6 distinct subsequences are "a", "b", "ab", "ba", "aa" and "aba".
```

Example 3:
```
Input: "aaa"
Output: 3 Explanation: The 3 distinct subsequences are "a", "aa" and "aaa".
```

Note:

1. `S` contains only lowercase letters.
2. `1 <= S.length <= 2000`

Solution:

1. 
```
class Solution {
public:
    int distinctSubseqII(string S) {
        int M = 1e9 + 7;
        vector<int> dp(26);
        for (char c : S) {
            dp[c - 'a'] = accumulate(dp.begin(), dp.end(), 1L) % M;
        }
        return accumulate(dp.begin(), dp.end(), 0L) % M;
    }
};
```

## Machine Learning
