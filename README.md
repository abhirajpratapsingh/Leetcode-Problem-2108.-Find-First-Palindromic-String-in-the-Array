
# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->
- The goal of this code appears to be finding the first palindrome in a given vector of strings.

![Screenshot (47).png](https://assets.leetcode.com/users/images/cf0248f6-b636-43c3-a02f-253b2e30bb51_1706559755.8927596.png)


---


---

# Approach
<!-- Describe your approach to solving the problem. -->
1. **isPalin Function:**
    - Takes a string s as input.
    - Initializes start to 0 and end to the last index of the string.
    - Uses a while loop to iterate until start is less than end.
    - Checks if the characters at start and end are equal. If not, returns false.
    - Increments start and decrements end in each iteration.
    - If the loop completes without returning false, returns true.

2. **firstPalindrome Function:**

    - Takes a vector of strings words as input.
    - Uses a for loop to iterate through each string in the vector.
    - For each string, calls the isPalin function to check if it is a palindrome.
    - If a palindrome is found, returns that string.
    - If no palindrome is found after checking all strings, returns an empty string.

3. **Overall Approach:**

    - The primary goal is to find and return the first palindrome from the given vector of strings.
    - The isPalin function is employed to check if a string is a palindrome or not.
    - The firstPalindrome function iterates through each string in the vector and utilizes isPalin to determine if the string is a palindrome.
    - Returns the first palindrome found or an empty string if none is found.

---

# Complexity

**Time Complexity:**
- isPalin has a time complexity of O(n), where n is the length of the string.
- firstPalindrome has a time complexity of O(m * n), where m is the number of strings and n is the average length of the strings.

**Space Complexity:**
- O(1) for both functions as they use a constant amount of extra space.


---


# Code
```
class Solution {
public:
    bool isPalin(string s)
    {
        int start=0;
        int end=s.length()-1;
        while(start<end)
        {
            if(s[start]!=s[end])
                return false;
            start++;
            end--;
        }
        return true;
    }
    string firstPalindrome(vector<string>& words) 
    {
        for(int i=0;i<words.size();i++)
        {
            if(palin(words[i]))
                return words[i];
        }
        return "";
    }
};
```

----
