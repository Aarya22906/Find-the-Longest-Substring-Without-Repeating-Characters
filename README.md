# Find-the-Longest-Substring-Without-Repeating-Characters
given a string S and task is to find length of longest substring that contains no repeating characters.In this problem, you need to find length of longest substring where all characters are unique. The substring can be formed by starting at any position in string, but it must not contain any repeated characters
def lengthOfLongestSubstring(s: str) -> int:
    char_set = set()
    left = 0
    max_len = 0
    for right in range(len(s)):
        while s[right] in char_set:
            char_set.remove(s[left])
            left += 1
        char_set.add(s[right])
        max_len = max(max_len, right - left + 1)
    return max_len
S = "abcabcbb"
print(lengthOfLongestSubstring(S))  
