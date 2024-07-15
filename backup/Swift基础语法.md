Swift是一种用于编写iOS、macOS、watchOS和tvOS应用程序的编程语言。它由Apple在2014年推出，旨在提供一种简单、安全、高效的编程体验。Swift结合了C语言和Objective-C的优点，同时摒弃了不安全的代码结构和编译过程中的复杂性。本文将介绍Swift的基础语法，包括变量与常量、数据类型、操作符、控制流、函数等。

### 变量与常量

在Swift中，使用`var`关键字声明变量，使用`let`关键字声明常量。变量的值可以在程序运行时修改，而常量的值一旦设置就不能再更改。

```swift
var variableName = "Hello, World!"
let constantName = 42
```

### 数据类型

Swift是一种强类型语言，支持多种数据类型，包括整数（`Int`）、浮点数（`Double`和`Float`）、布尔值（`Bool`）、字符串（`String`）、数组（`Array`）、字典（`Dictionary`）等。

```swift
var integer: Int = 10
var floatingPoint: Double = 3.14
var boolean: Bool = true
var string: String = "Swift"
var array: [Int] = [1, 2, 3, 4, 5]
var dictionary: [String: Int] = ["one": 1, "two": 2, "three": 3]
```

### 操作符

Swift支持多种操作符，包括算术操作符、比较操作符、逻辑操作符、赋值操作符等。

#### 算术操作符

```swift
let sum = 5 + 3       // 加法
let difference = 5 - 3 // 减法
let product = 5 * 3   // 乘法
let quotient = 5 / 3  // 除法
let remainder = 5 % 3 // 取余
```

#### 比较操作符

```swift
let isEqual = 5 == 3      // 等于
let isNotEqual = 5 != 3   // 不等于
let isGreater = 5 > 3     // 大于
let isLess = 5 < 3        // 小于
let isGreaterOrEqual = 5 >= 3 // 大于等于
let isLessOrEqual = 5 <= 3    // 小于等于
```

#### 逻辑操作符

```swift
let and = true && false  // 逻辑与
let or = true || false   // 逻辑或
let not = !true          // 逻辑非
```

#### 赋值操作符

```swift
var a = 5
a += 3  // 等同于 a = a + 3
a -= 3  // 等同于 a = a - 3
a *= 3  // 等同于 a = a * 3
a /= 3  // 等同于 a = a / 3
a %= 3  // 等同于 a = a % 3
```

### 控制流

Swift提供了多种控制流语句，包括条件语句、循环语句、跳转语句等。

#### 条件语句

##### if语句

```swift
let condition = true
if condition {
    print("Condition is true")
} else {
    print("Condition is false")
}
```

##### switch语句

```swift
let value = 2
switch value {
case 1:
    print("Value is 1")
case 2:
    print("Value is 2")
case 3:
    print("Value is 3")
default:
    print("Value is something else")
}
```

#### 循环语句

##### for-in循环

```swift
let numbers = [1, 2, 3, 4, 5]
for number in numbers {
    print(number)
}
```

##### while循环

```swift
var counter = 5
while counter > 0 {
    print(counter)
    counter -= 1
}
```

##### repeat-while循环

```swift
var counter = 5
repeat {
    print(counter)
    counter -= 1
} while counter > 0
```

### 函数

函数是Swift中组织代码的重要手段。使用`func`关键字定义函数。

```swift
func greet(person: String) -> String {
    return "Hello, \(person)!"
}
let greeting = greet(person: "John")
print(greeting)
```

#### 函数参数和返回值

函数可以有多个参数和返回值。

```swift
func add(a: Int, b: Int) -> Int {
    return a + b
}
let result = add(a: 3, b: 5)
print(result)
```

#### 参数标签和默认参数值

参数标签可以提高代码的可读性。默认参数值可以简化函数调用。

```swift
func greet(person: String, from hometown: String = "unknown") -> String {
    return "Hello, \(person) from \(hometown)!"
}
print(greet(person: "Alice", from: "New York"))
print(greet(person: "Bob"))
```

### 闭包

闭包是一种自包含的函数代码块，可以在代码中被传递和使用。闭包可以捕获和存储其上下文中的常量和变量。

```swift
let numbers = [1, 2, 3, 4, 5]
let squaredNumbers = numbers.map { $0 * $0 }
print(squaredNumbers)
```

### 枚举

枚举用于定义一组相关的值。

```swift
enum CompassPoint {
    case north
    case south
    case east
    case west
}
var direction = CompassPoint.north
direction = .east
```

### 结构体和类

结构体和类是构建自定义数据类型的基础。结构体是值类型，类是引用类型。

#### 结构体

```swift
struct Person {
    var name: String
    var age: Int
}
var person = Person(name: "John", age: 30)
person.age = 31
```

#### 类

```swift
class Person {
    var name: String
    var age: Int
    
    init(name: String, age: Int) {
        self.name = name
        self.age = age
    }
    
    func greet() -> String {
        return "Hello, \(name)!"
    }
}
let person = Person(name: "John", age: 30)
print(person.greet())
```

### 属性和方法

结构体和类可以有属性和方法。

#### 存储属性和计算属性

```swift
struct Circle {
    var radius: Double
    var area: Double {
        return 3.14 * radius * radius
    }
}
let circle = Circle(radius: 5)
print(circle.area)
```

#### 实例方法和类方法

```swift
class Counter {
    var count = 0
    func increment() {
        count += 1
    }
    static func reset() -> Counter {
        return Counter()
    }
}
var counter = Counter()
counter.increment()
print(counter.count)
counter = Counter.reset()
print(counter.count)
```

### 继承

类可以继承其他类的属性和方法。

```swift
class Animal {
    var name: String
    
    init(name: String) {
        self.name = name
    }
    
    func makeSound() -> String {
        return "Some sound"
    }
}

class Dog: Animal {
    override func makeSound() -> String {
        return "Bark"
    }
}

let dog = Dog(name: "Buddy")
print(dog.makeSound())
```

### 协议

协议定义了一组方法和属性，类、结构体和枚举可以遵循协议来实现这些方法和属性。

```swift
protocol Describable {
    func describe() -> String
}

class Car: Describable {
    var make: String
    var model: String
    
    init(make: String, model: String) {
        self.make = make
        self.model = model
    }
    
    func describe() -> String {
        return "This is a \(make) \(model)."
    }
}

let car = Car(make: "Toyota", model: "Corolla")
print(car.describe())
```

### 错误处理

Swift提供了基于`do-catch`的错误处理机制，用于捕获和处理运行时错误。

```swift
enum FileError: Error {
    case fileNotFound
    case unreadable
    case encodingFailed
}

func readFile(at path: String) throws -> String {
    // 假设某些逻辑可能抛出错误
    throw FileError.fileNotFound
}

do {
    let content = try readFile(at: "path/to/file")
    print(content)
} catch FileError.fileNotFound {
    print("File not found")
} catch {
    print("An error occurred: \(error)")
}
```

### 泛型

泛型允许你编写灵活且可重用的函数和类型。

```swift
func swapValues<T>(a: inout T, b: inout T) {
    let temp = a
    a = b
    b = temp
}
var x = 1
var y = 2
swapValues(a:

 &x, b: &y)
print("x: \(x), y: \(y)")
```