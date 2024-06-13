# Assignment 1


### 1. Print the Pattern

```kotlin
fun printPattern(n: Int) {
    for (i in 1..n) {
        for (j in 1..i) {
            print("* ")
        }
        println()
    }
}

fun main() {
    val n = 5
    printPattern(n)
}
```

### 2. Check if the Number is an Armstrong Number or Not

```kotlin
fun isArmstrongNumber(number: Int): Boolean {
    val digits = number.toString().map { it.toString().toInt() }
    val sum = digits.map { it * it * it }.sum()
    return sum == number
}

fun main() {
    val number = 153
    if (isArmstrongNumber(number)) {
        println("$number is an Armstrong number")
    } else {
        println("$number is not an Armstrong number")
    }
}
```

### 3. Find the GCD of Two Numbers Using the Euclidean Method

```kotlin
fun gcd(a: Int, b: Int): Int {
    if (b == 0) {
        return a
    }
    return gcd(b, a % b)
}

fun main() {
    val num1 = 56
    val num2 = 98
    println("GCD of $num1 and $num2 is ${gcd(num1, num2)}")
}
```

### 4. Find the Frequency of Letters in a String

```kotlin
fun frequencyOfLetters(str: String): Map<Char, Int> {
    val frequencyMap = mutableMapOf<Char, Int>()
    for (char in str) {
        if (char.isLetter()) {
            frequencyMap[char] = frequencyMap.getOrDefault(char, 0) + 1
        }
    }
    return frequencyMap
}

fun main() {
    val str = "Hello World"
    val frequencyMap = frequencyOfLetters(str)
    for ((char, freq) in frequencyMap) {
        println("$char: $freq")
    }
}
```

### 5. Check if a Number is a Duck Number or Not

```kotlin
fun isDuckNumber(number: String): Boolean {
    if (number[0] == '0') {
        return false
    }
    return '0' in number
}

fun main() {
    val number = "1023"
    if (isDuckNumber(number)) {
        println("$number is a Duck number")
    } else {
        println("$number is not a Duck number")
    }
}
```
