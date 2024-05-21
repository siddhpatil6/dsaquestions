![1_6Ay06giAcrgH0TWI5tiv6Q](https://github.com/siddhpatil6/dsaquestions/assets/5618021/1011a245-8068-4336-bb16-1666f47b244f)![1_6Ay06giAcrgH0TWI5tiv6Q](https://github.com/siddhpatil6/dsaquestions/assets/5618021/653124c7-4e71-4b11-a94b-212880482d66)# dsaquestions


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


<h1> So how does HashMap internally work? </h1>

HashMap uses HashTable implementation internally and consists of two important data structures which are LinkedList and Array. There is a bucket of arrays with each element representing an individual LinkedList. The Inner Node class consists of a hash value, key, value, and the link to the next Node as seen below.

![1_Pnz-AZsYuhhQtY0HJqnjgQ](https://github.com/siddhpatil6/dsaquestions/assets/5618021/cba4e7db-f103-4440-ab87-47668a75ab0a)

Now, the question arises, how does HashMap know where to store the value in a bucket? <br>
 <br>
To store the values, HashMap uses a concept known as Hashing. Hashing is performed using a hashCode() function that converts an Object into HashCode. Based on the hash index results, a slot in the bucket is selected, and the value results are stored. <br>
 <br>
As you might think, there would be multiple objects which get hashed to the same bucket index. This is known as collision, and therefore we use a LinkedList to store the values which are linked with each other. This can be seen in the representation below. <br>
<br>

![1_GHmgcVUiWcu770PO3Yhv2A](https://github.com/siddhpatil6/dsaquestions/assets/5618021/0f12abb0-50b1-425d-8eff-d930268f865c)

<br>
A collision occurs when two different values hash to the same bucket index. Let’s consider an example that two integers “1000” and “500” gives us two hash values 100 and 50 respectively. If we consider the total array size as 10, both of them end up in the same bucket i.e. 100 % 10 and 50 % 10). What chaining does is whenever you call the function map.get( “100” );, you are able to retrieve the correct value associated with the key. To verify, we can also utilize the equals method in HashMap. <br>
 <br>
You can also override this hashcode function and provide your own implementation. A good hash function is one which distributes the objects evenly. <br>
<br>
Changes in the Java 8 implementation:
To improve the working of HashMap, Java 8 made updates to the internal implementation workflow. Once a certain threshold level is reached, the values are now automatically stored in a tree manner rather than a linked list. So instead of O(n) retrieval time, we now have better O(log n) retrieval performance. Java only does this when there is a performance gain. This can be seen in the representation below. <br>
<br>

![1_6Ay06giAcrgH0TWI5tiv6Q](https://github.com/siddhpatil6/dsaquestions/assets/5618021/0f138db3-9e79-42b5-a22c-14363811aa83)

<h2> How does HashMap provide a constant time (O(1)) retrieval when LinkedList/Tree data Structures are used to store the values? </h2>
In real life, the time complexity of HashMap is not O(1). It is Big O(average size of the collision structure) and is known as amortized O(1). <br>
 <br>
True O(1) is only achieved by collision-less hashing(also known as “perfect” hashing). <br>
<br>
 
<h3>Difference between TreeMap, HashMap, LinkedHashMap, and HashTable in Java: </h3>
All of the above helps us to store data in key: value format. The important distinction is between the ordering and time complexity of the retrieval of data. <br>

<h3> HashMap: </h3>

HashMap offers O(1) insertion and retrieval time. <br>
It contains value based on keys. <br>
The ordering of keys is random <br>
It uses a linked list to store the data. <br>
It contains only unique elements <br>
It may have one null key and multiple null values <br>
It is not thread-safe <br>

<h3> LinkedHashMap: </h3>
LinkedHashMap is the same as HashMap but maintains the insertion order. <br>
The other properties align with that of HashMap. <br>

<h3> TreeMap: </h3>
TreeMap offers O(log N) insertion and retrieval time. <br>
It cannot have a null key but can have multiple null values. <br>
It maintains ascending order of keys. <br>
The rest of the properties align with that of HashMap. <br>

<h3>Hashtable:</h3>
It is thread-safe. <br>
Since it is thread-safe the performance might be low <br>
Null is not allowed for both key and value <br>


