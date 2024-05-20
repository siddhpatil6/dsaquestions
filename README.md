# dsaquestions


<h1> Reverse string in effitiend way with minimum time complexity without inbuild fuction </h1>

```
fun main() {
    val input = "Hello, World!"
    val reversed = reverseString(input)
    println("Reversed string: $reversed")
}

fun reverseString(input: String): String {
    val charArray = input.toCharArray()
    val length = charArray.size
    for (i in 0 until length / 2) {
        val temp = charArray[i]
        charArray[i] = charArray[length - i - 1]
        charArray[length - i - 1] = temp
    }
    return String(charArray)
}
```

<h1> 2nd highest from array </h1>

```
fun main() {
    val numbers = arrayOf(5, 10, 2, 8, 15, 3)
    val secondHighest = findSecondHighest(numbers)
    println("Second highest number: $secondHighest")
}

fun findSecondHighest(numbers: Array<Int>): Int? {
    if (numbers.size < 2) return null

    var highest = Int.MIN_VALUE
    var secondHighest = Int.MIN_VALUE

    for (number in numbers) {
        if (number > highest) {
            secondHighest = highest
            highest = number
        } else if (number > secondHighest && number != highest) {
            secondHighest = number
        }
    }

    return if (secondHighest == Int.MIN_VALUE) null else secondHighest
}
```


<h1> find duplicate no.s in array </h1>

```
fun main() {
    val numbers = arrayOf(1, 2, 3, 4, 5, 2, 6, 7, 8, 3, 9, 1, 10)

    val seen = HashSet<Int>()
    val duplicates = HashSet<Int>()

    for (number in numbers) {
        if (!seen.add(number)) {
            // If the number is already in the set, it's a duplicate
            duplicates.add(number)
        }
    }

    println("Duplicate numbers in the array: $duplicates")
}
```


<h1> Sort array without using default methods in kotlin </h1>

```
fun main() {
    val numbers = arrayOf(4, 2, 7, 1, 9, 5, 3)
    bubbleSort(numbers)
    println("Sorted array: ${numbers.joinToString()}")
}

fun bubbleSort(arr: Array<Int>) {
    val n = arr.size
    for (i in 0 until n - 1) {
        for (j in 0 until n - i - 1) {
            if (arr[j] > arr[j + 1]) {
                // Swap arr[j] and arr[j+1]
                val temp = arr[j]
                arr[j] = arr[j + 1]
                arr[j + 1] = temp
            }
        }
    }
}
```
<h1> write extenstion fun, which return string without 1st charecte r</h1>

```
fun String.removeFirstCharacter(): String {
    return if (this.length > 1) {
        this.substring(1)
    } else {
        ""
    }
}

fun main() {
    val input = "Hello"
    val result = input.removeFirstCharacter()
    println("Result: $result")
}
```


<h1> Exception Hierarchy </h1>
All exception and error types are subclasses of the class Throwable, which is the base class of the hierarchy. One branch is headed by Exception. This class is used for exceptional conditions that user programs should catch. NullPointerException is an example of such an exception. Another branch, Error is used by the Java run-time system(JVM) to indicate errors having to do with the run-time environment itself(JRE). StackOverflowError is an example of such an error. <br> <br>

![Exception-Handling-768](https://github.com/siddhpatil6/dsaquestions/assets/5618021/b5718d43-1bd3-44b9-a045-8461318182e0)

<h3> Types of Exceptions </h3>
Java defines several types of exceptions that relate to its various class libraries. Java also allows users to define their own exceptions. <br> <br>

![Exceptions-in-Java-1-768](https://github.com/siddhpatil6/dsaquestions/assets/5618021/015e8a7d-670e-4122-ba6d-bf2e3c60670b)

<h3> Exceptions can be categorized in two ways: </h3>
 <br>
Built-in Exceptions <br>
Checked Exception <br>
Unchecked Exception  <br>
User-Defined Exceptions  <br>

Let us discuss the above-defined listed exception that is as follows:

<h2>1. Built-in Exceptions </h2>
Built-in exceptions are the exceptions that are available in Java libraries. These exceptions are suitable to explain certain error situations.

<h3>Checked Exceptions: </h3>
Checked exceptions are called compile-time exceptions because these exceptions are checked at compile-time by the compiler.
 
<h3>Unchecked Exceptions: </h3>
The unchecked exceptions are just opposite to the checked exceptions. The compiler will not check these exceptions at compile time. In simple words, if a program throws an unchecked exception, and even if we didn’t handle or declare it, the program would not give a compilation error.
Note: For checked vs unchecked exception, see Checked vs Unchecked Exceptions 

<h2> 2. User-Defined Exceptions: </h2>
Sometimes, the built-in exceptions in Java are not able to describe a certain situation. In such cases, users can also create exceptions, which are called ‘user-defined Exceptions’. 

<h3> The advantages of Exception Handling in Java are as follows: </h3>

Provision to Complete Program Execution <br>
Easy Identification of Program Code and Error-Handling Code <br>
Propagation of Errors <br>
Meaningful Error Reporting <br>
Identifying Error Types <br>




