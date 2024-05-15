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
