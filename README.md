All Possible Strings (Subsequences)

This project provides a Java solution to generate all possible non-empty subsequences of a given string and return them in lexicographically sorted order.

🚀 Problem Statement

Given a string s, generate all possible subsequences (excluding the empty string) and return them sorted in lexicographical order.

🔎 Example

Input:

s = "abc"

Output:

[a, ab, abc, ac, b, bc, c]
🧠 Approach

We use Recursion (Backtracking) to generate subsequences.

For each character, we have two choices:

Include the character

Exclude the character

This results in 2ⁿ combinations, where n is the length of the string.

After generating all subsequences:

Remove the empty string

Sort the list using Collections.sort()

💻 Implementation (Java)
import java.util.*;

class Solution {
    public List<String> AllPossibleStrings(String s) {
        List<String> list = new ArrayList<>();
        Subset("", s, 0, list);
        Collections.sort(list);
        return list;
    }

    public void Subset(String ans, String s, int idx, List<String> list) {
        if (idx == s.length()) {
            if (!ans.equals("")) {
                list.add(ans);
            }
            return;
        }

        // Include current character
        Subset(ans + s.charAt(idx), s, idx + 1, list);

        // Exclude current character
        Subset(ans, s, idx + 1, list);
    }
}
⏱ Time & Space Complexity

Time Complexity: O(2ⁿ)

Space Complexity: O(2ⁿ) (for storing subsequences)


✨ Author

Sanjeev Sharma
