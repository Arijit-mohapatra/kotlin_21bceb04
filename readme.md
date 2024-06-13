# Assignment 2

### 1. Function Overloading

```kotlin
fun calculateArea(length: Double, breadth: Double): Double {
    return length * breadth
}

fun calculateArea(radius: Double): Double {
    return Math.PI * radius * radius
}

fun main() {
    val rectangleArea = calculateArea(5.0, 3.0)
    val circleArea = calculateArea(4.0)
    println("Area of rectangle: $rectangleArea")
    println("Area of circle: $circleArea")
}
```

### 2. Higher-Order Functions

```kotlin
fun operation(a: Int, b: Int, func: (Int, Int) -> Int): Int {
    return func(a, b)
}

fun add(a: Int, b: Int): Int {
    return a + b
}

fun main() {
    val result = operation(5, 3, ::add)
    println("Result of operation: $result")
}
```

### 3. Extension Functions

```kotlin
fun String.isPalindrome(): Boolean {
    return this == this.reversed()
}

fun main() {
    val str = "madam"
    if (str.isPalindrome()) {
        println("$str is a palindrome")
    } else {
        println("$str is not a palindrome")
    }
}
```

### 4. Recursive Functions

```kotlin
fun factorial(n: Long, accumulator: Long = 1): Long {
    return if (n <= 1) {
        accumulator
    } else {
        factorial(n - 1, n * accumulator)
    }
}

fun main() {
    val num = 20L
    println("Factorial of $num is ${factorial(num)}")
}
```

### Advanced Programming Questions on Classes

### 1. Inheritance and Polymorphism

```kotlin
abstract class Shape {
    abstract fun area(): Double
}

class Rectangle(val length: Double, val breadth: Double) : Shape() {
    override fun area(): Double {
        return length * breadth
    }

    fun perimeter(): Double {
        return 2 * (length + breadth)
    }
}

class Circle(val radius: Double) : Shape() {
    override fun area(): Double {
        return Math.PI * radius * radius
    }

    fun perimeter(): Double {
        return 2 * Math.PI * radius
    }
}

fun main() {
    val shapes: List<Shape> = listOf(Rectangle(5.0, 3.0), Circle(4.0))
    for (shape in shapes) {
        println("Area: ${shape.area()}")
        if (shape is Rectangle) {
            println("Perimeter: ${shape.perimeter()}")
        } else if (shape is Circle) {
            println("Perimeter: ${shape.perimeter()}")
        }
    }
}
```

### 2. Data Classes and Copy Function

```kotlin
data class Person(val name: String, val age: Int, val address: String)

fun main() {
    val person1 = Person("John", 30, "123 Street")
    val person2 = person1.copy(age = 31, address = "456 Avenue")
    println("Person1: $person1")
    println("Person2: $person2")
}
```

### 3. Companion Objects and Factory Methods

```kotlin
class User(val name: String, val age: Int) {
    companion object {
        fun createDefaultUser(): User {
            return User("Default", 0)
        }

        fun createUser(name: String = "Default", age: Int = 0): User {
            return User(name, age)
        }
    }
}

fun main() {
    val user1 = User.createDefaultUser()
    val user2 = User.createUser("Alice", 25)
    val user3 = User.createUser(age = 30)
    println("User1: ${user1.name}, Age: ${user1.age}")
    println("User2: ${user2.name}, Age: ${user2.age}")
    println("User3: ${user3.name}, Age: ${user3.age}")
}
```

### 4. Interface Implementation

```kotlin
interface Drawable {
    fun draw()
    fun resize()
}

class Square(val side: Double) : Drawable {
    override fun draw() {
        println("Drawing a square with side $side")
    }

    override fun resize() {
        println("Resizing the square")
    }
}

class Triangle(val base: Double, val height: Double) : Drawable {
    override fun draw() {
        println("Drawing a triangle with base $base and height $height")
    }

    override fun resize() {
        println("Resizing the triangle")
    }
}

fun main() {
    val square: Drawable = Square(4.0)
    val triangle: Drawable = Triangle(3.0, 5.0)
    square.draw()
    square.resize()
    triangle.draw()
    triangle.resize()
}
```

### 5. Singleton Pattern

```kotlin
object DatabaseConnection {
    init {
        println("Initializing DatabaseConnection")
    }

    fun connect() {
        println("Connecting to the database")
    }

    fun disconnect() {
        println("Disconnecting from the database")
    }
}

fun main() {
    DatabaseConnection.connect()
    DatabaseConnection.disconnect()
}
```
