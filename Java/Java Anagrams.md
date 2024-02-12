# Java Anagrams

https://www.hackerrank.com/challenges/java-anagrams/problem?isFullScreen=true

# Solution

Using HashMap
```
import java.util.HashMap;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        
        Scanner scan = new Scanner(System.in);
        
        String a = scan.nextLine();
        String b = scan.nextLine();

        System.out.println(isAnagram(a, b) ? "Anagrams" : "Not Anagrams");
    }

    static boolean isAnagram(String a, String b) {
        if (a == null || b == null || a.length() != b.length()) {
            return false;
        }

        a = a.toLowerCase();
        b = b.toLowerCase();

        HashMap<Character, Integer> map = new HashMap<>();

        // Count frequency of each character in the first string
        for (int i = 0; i < a.length(); i++) {
            char ch = a.charAt(i);
            map.put(ch, map.getOrDefault(ch, 0) + 1);
        }

        // Decrease the frequency based on the second string
        for (int i = 0; i < b.length(); i++) {
            char ch = b.charAt(i);
            if (!map.containsKey(ch)) {
                return false;
            }
            map.put(ch, map.get(ch) - 1);
            if (map.get(ch) == 0) {
                map.remove(ch);
            }
        }

        // If the map is empty, the strings are anagrams
        return map.isEmpty();
    }
}

```