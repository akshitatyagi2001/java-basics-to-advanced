### You are given two strings 'S' and 'T' of lengths 'N' and 'M' respectively. Find the "Edit Distance" between the strings.
### Edit Distance of two strings is the minimum number of steps required to make one string equal to the other. In order to do so, you can perform the following three operations:
### 1. Delete a character
### 2. Replace a character with another one
### 3. Insert a character
###   Note:
###   Strings don't contain spaces in between.
###   Constraints:
###   0 <= N <= 10 ^ 3
###   0 <= M <= 10 ^ 3

### Time Limit : 1sec
### Sample Input 1 :
### abc
### dc
### Sample Output 1 :
### 2
### Explanation For Sample Input 1 :
### In 2 operations we can make the string T to look like string S. First, insert the character 'a' to string T, which makes it "adc".

### And secondly, replace the character 'd' of the string T with 'b' from the string S. This would make string T to "abc" which is also the string S. Hence, the minimum distance.
### Sample Input 2 :
### whgtdwhgtdg
### aswcfg
### Sample Output 2 :
### 9

#### Solution

```java
public static int minEditDistance(String S, String T) {
		return calculate(S, T, S.length(), T.length());
	}

	private static int calculate(String S, String T, int i, int j) {

		// Base Cases
		if (i == 0) return j; // Need to insert all j characters
		if (j == 0) return i; // Need to delete all i characters

		if (S.charAt(i - 1) == T.charAt(j - 1)) {
			return calculate(S, T, i - 1, j - 1);
		}
			int insert = calculate(S, T, i-1, j);      // Insert
			int delete = calculate(S, T, i, j-1);      // Delete
			int replace = calculate(S, T, i - 1, j - 1); // Replace
			int result = 1 + Math.min(insert, Math.min(delete, replace));
		return result;
	}
```