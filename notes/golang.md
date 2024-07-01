# Go / Golang

## Table of Contents

- [Language Mechanics]()
  - [Variables]()
  - [Struct Types]()
  - [Pointers]()
  - [Constants]()
  - [Functions]()
  - [Arrays]()
  - [Slices]()
  - [Maps]()
  - [Methods]()
  - [Interfaces]()
  - [Embedding]()
  - [Exporting]()
- [Composition and Interfaces]()
- [Concurrency]()
- [Generics]()

## Language Mechanics
- Covers the language's syntax, idioms, implementation, and specification, how it's used, and how it works with hardware and operating systems

### Variables [1]
- Variables provide the ability to read from and write to memory
- In Go, access to memory is type safe
- The compiler will not allow us to use variables outside the scope of how they are declared
- Built-in types
  - Types provide integrity and readability by specifying
    - The amount of memory to allocate (e.g. 1, 2, 4, 8 bytes)
    - What that memory represents (e.g. int, uint, bool,..)
  - Types can be specific to a precision
    - uint8 represents an unsigned integer with 1 byte of allocation
    - int32 represents a signed integer with 4 bytes of allocation
  - When declaring a type using a non-precision based type (unit, int) the size of the value is based on the architecture being used to build the program
    - 32 bit arch: int represents a signed int at 4 bytes of memory allocation
    - 64 bit arch: int represents a signed int at 8 bytes of memory allocation
- Word size
  - Word size represents the amount of memory allocation required to store integers and pointers for a given architecture
    - 32 bit arch: word size is 4 bytes of memory allocation
    - 64 bit arch: word size is 8 bytes of memory allocation
  - Go has internal data structures (maps, channels, slices, interfaces, and functions) that store integers and pointers
  - The size of these data structures will be based on the architecture being used to build the program
  - In Go, the amount of memory allocated for a value of type int, a pointer, or a word will always be the same on the same architecture
- Zero value concept
  - Every single value you construct in Go is initialized at least to its zero value state unless you specify the initialization value at construction
  - The zero value is the setting of every bit in every byte to zero
  - This is done for data integrity and it’s not free
  - It takes time to push electrons through the machine to reset those bits, but you should always take integrity over performance

    | Type | Zerp Value |
    | ---- | ---------- |
    | Boolean | false |
    | Integer | 0 |
    | Float | 0 |
    | Complex | 0i |
    | String | "" (empty) |
    | Pointer | nil |

- Declaring and initializing variables
  - The keyword `var` can be used to construct values to their zero value state for all types
  - Strings use the UTF8 character set, but are really just a collection of bytes
  - A string is a two-word internal data structure in Go
    - The first word represents a pointer to a backing array of bytes
    - The second word represents the length or the number of bytes in the backing array
    - If the string is set to its zero value state, then the first word is nil and the second word is 0
  - Using the short variable declaration operator `:=`, you can declare, construct, and initialize a value all at the same time
- Conversion vs casting
  - Go doesn't have casting, but conversion
  - Instead of telling the compiler to map a set of bytes to a different representation, the bytes need to be copied to a new memory location for the new representation
  - Go does have a package in the standard library called unsafe if you need to perform an actual casting operation
  - You should really avoid that and be honest with yourself why you are considering using it
  - Performing a conversion provides the highest level of integrity for these types of operations
 
  ```go
  // main.go
  // Sample program to show how to declare variables.
  package main

  import "fmt"

  func main() {
    // Declare variables that are set to their zero value.
    var a int
    var b string
    var c float64
    var d bool
  
    fmt.Printf("var a int \t %T [%v]\n", a, a)
    fmt.Printf("var b string \t %T [%v]\n", b, b)
    fmt.Printf("var c float64 \t %T [%v]\n", c, c)
    fmt.Printf("var d bool \t %T [%v]\n\n", d, d)

    // Declare variables and initialize.
    // Using the short variable declaration operator.
    aa := 10
    bb := "hello"
    cc := 3.14159
    dd := true
  
    fmt.Printf("aa := 10 \t %T [%v]\n", aa, aa)
    fmt.Printf("bb := \"hello\" \t %T [%v]\n", bb, bb)
    fmt.Printf("cc := 3.14159 \t %T [%v]\n", cc, cc)
    fmt.Printf("dd := true \t %T [%v]\n\n", dd, dd)
  
    // Specify type and perform a conversion.
    aaa := int32(10)
  
    fmt.Printf("aaa := int32(10) %T [%v]\n", aaa, aaa)
  }

  /*
    Zero Values:
    Type Initialized Value
    Boolean false
    Integer 0
    Floating Point 0
    Complex 0i
    String "" (empty string)
    Pointer nil
  */
  ```

- Notes
  - The purpose of all programs and all parts of those programs is to transform data from one form to the other
  - Code primarily allocates, reads and writes to memory
  - Understanding type is crucial to writing good code and understanding code
  - If you don't understand the data, you don't understand the problem
  - You understand the problem better by understanding the data
  - When variables are being declared to their zero value, use the keyword var
  - When variables are being declared and initialized, use the short variable declaration operator
 
#### Built-In Types [2]
- A type determines a set of values together with operations and methods specific to those values
- 

#### Variables [3]
- 

#### Gustavo's IEEE-754 Brain Teaser [4]
- 

#### What's in a name [5]
- 

#### A brief history of “type” [6]
- 

### Struct Types
### Pointers
### Constants
### Functions
### Arrays
### Slices
### Maps
### Methods
### Interfaces
### Embedding
### Exporting

---

## Composition and Interfaces

### Grouping With Types
### Type Conversions And Assertions
### Interface Pollution
### Mocking
### Decoupling
### Error Handling

---

## Concurrency

### Goroutines
### Data Races
### Context Package
### Channels

---

## Generics

### Basics
### Underlying Types
### Struct Types
### Behavior As Constraint
### Type As Constraint
### Multi-Type Parameters
### Slice Constraints
### Channels
### Hash Tables

---

## Credits

[1] https://tour.ardanlabs.com/tour/eng/variables/1
[2] https://go.dev/ref/spec#Types
[3] 
[4] 
[5] 
[6] 
[7] 
