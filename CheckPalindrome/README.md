# Java String Reverse

## A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward or forward.
## Given a string , print Yes if it is a palindrome, print No otherwise.

### Sample Input
### madam

### Sample Output
### Yes

#### Solution

```java
class Solution {
    private static void reverseString(String str){
        str = str.toLowerCase();
        String reversed = "";
        for(int i = str.length()-1; i >=0; i--){
            reversed += str.charAt(i);
            if(reversed.equals(str)){
                System.out.println("Yes");
            }
            else{
                System.out.println("No");
            }
        }
    }
}
```