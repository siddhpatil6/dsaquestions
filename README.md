# dsaquestions


<h1>2) Reverse string in effitiend way with minimum time complexity without inbuild fuction </h1>

```
public class Main {
    public static void main(String[] args) {
        String s = "Hello, World!";
        String reversed = reverseString(s);
        System.out.println(reversed);
    }

    public static String reverseString(String s) {
        // Convert the string to a character array since strings in Java are immutable
        char[] charArray = s.toCharArray();
        // Get the length of the string
        int n = charArray.length;
        // Swap characters from the beginning and end of the string
        for (int i = 0; i < n / 2; i++) {
            char temp = charArray[i];
            charArray[i] = charArray[n - i - 1];
            charArray[n - i - 1] = temp;
        }
        // Convert the character array back to a string and return
        return new String(charArray);
    }
}
```

<h1> 2nd highest from array </h1>

```
public class Main {
    public static void main(String[] args) {
        int[] numbers = {5, 10, 2, 8, 15, 3};
        int secondHighest = findSecondHighest(numbers);
        System.out.println("Second highest number: " + secondHighest);
    }

    public static int findSecondHighest(int[] numbers) {
        int highest = Integer.MIN_VALUE;
        int secondHighest = Integer.MIN_VALUE;

        for (int number : numbers) {
            if (number > highest) {
                secondHighest = highest;
                highest = number;
            } else if (number > secondHighest && number != highest) {
                secondHighest = number;
            }
        }

        return secondHighest;
    }
}
```


<h1> find duplicate no.s in array </h1>

```
import java.util.HashSet;
import java.util.Set;

public class Main {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5, 2, 6, 7, 8, 3, 9, 1, 10};

        Set<Integer> seen = new HashSet<>();
        Set<Integer> duplicates = new HashSet<>();

        for (int number : numbers) {
            if (!seen.add(number)) {
                // If the number is already in the set, it's a duplicate
                duplicates.add(number);
            }
        }

        System.out.println("Duplicate numbers in the array: " + duplicates);
    }
}
```
