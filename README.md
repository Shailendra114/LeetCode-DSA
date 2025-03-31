# LeetCode-DSA


# Arrays :

## Problem: Merge Strings Alternately :

You are given two strings `word1` and `word2`. Merge the strings by adding letters in alternating order, starting with `word1`. If a string is longer than the other, append the additional letters onto the end of the merged string.

Write a function to merge these two strings as described and return the merged string.

Example1 :

```
Input: word1 = "abc", word2 = "pqr"
Output: "apbqcr"
Explanation:
The merged string will be merged as follows:
word1:  a   b   c  
word2:    p   q   r  
merged: a p b q c r

```
Example2 :

```
Input: word1 = "ab", word2 = "pqrs"
Output: "apbqrs"
Explanation:
Notice that as `word2` is longer, "rs" is appended to the end.
word1:  a   b  
word2:    p   q   r   s  
merged: a p b q   r   s

```
Example3: 

```
Input: word1 = "abcd", word2 = "pq"
Output: "apbqcd"
Explanation:
Notice that as `word1` is longer, "cd" is appended to the end.
word1:  a   b   c   d  
word2:    p   q  
merged: a p b q c   d

```
Constraints :

1 <= word1.length, word2.length <= 100
word1 and word2 consist of lowercase English letters.

Solution :

``` python
    def mergeAlternately(self, word1: str, word2: str) -> str:
        result = []
        i, j= 0,0
        while i<len(word1) and j<len(word2):
           result.append(word1[i])
           result.append(word2[j])
           i += 1
           j += 1

        result.append(word1[i:])
        result.append(word2[j:])

        return ''.join(result)


```

## Problem : Greatest common divisor of Strings

For two strings s and t, we say "t divides s" if and only if s = t + t + t + ... + t + t (i.e., t is concatenated with itself one or more times).

Given two strings str1 and str2, return the largest string x such that x divides both str1 and str2.


Example 1:

```
Input: str1 = "ABCABC", str2 = "ABC"
Output: "ABC"

```

Example 2:

```
Input: str1 = "ABABAB", str2 = "ABAB"
Output: "AB"
```

Example 3:

```
Input: str1 = "LEET", str2 = "CODE"
Output: ""

```
Constraints:

- 1 <= str1.length, str2.length <= 1000
- str1 and str2 consist of English uppercase letters.

Solution :

```python
import math
class Solution:
    def gcdOfStrings(self, str1: str, str2: str) -> str:
        if str1 + str2 != str2 + str1:
          return ""

        gcd_len = math.gcd(len(str1), len(str2))

        return str1[:gcd_len]
```


