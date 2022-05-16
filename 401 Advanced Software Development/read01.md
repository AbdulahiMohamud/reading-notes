

#### Primitive Data Types

| Name    | Default Value | Size          |
| ------- | ------------- | ------------- |
| byte    | 0             | 8-bit signed  |
| short   | 0             | 16-bit signed |
| int     | 0             | 32-bit signed |
| long    | 0L            | 64-bit signed |
| float   | 0.0f          | 32-bit        |
| double  | 0.0d          | 64-bit        |
| char    | \u0000        | 16-bit        |
| boolean | false         | 1-bit-ish     |
| String  | null          | not actually primitive |



#### Arrays

Arrays hold a fixed number of elements of a single type. The size is declared when the array is created. Array elements can be created in groups with curly bracket notation or individual indexes can be assigned with square bracket notation. Multidimensional arrays can be created by including more sets of square brackets. 

A Few Array Examples:
```java
class Example {
  public static void main(String[] args) {
    int[] myArray;
    myArray = new int[5]; // assign the size but leave it empty
    myArray[0] = 5;
    char[] myOtherArray = {'A', 'B', 'C'}; // assign the size and elements all at once
    boolean[][] myMatrix = {true, true}, {false, false}; // two-dimentional array
  }
}
```

### Control Flow Statements 

#### If-Then and If-Then Else Statements

If-then statements control the flow of the program by executing certain code only if a test evaluates to true. Else is used as an alternate route if the test evaluates to false.

#### Switch Statement

Switch statements use one or more cases that behave like a series of if-then tests. A default case can be used to catch anything that fails all previous tests.

#### While and Do While Statements

While statements execute a block of code until a test is false. Do-while tests execute a block of code at least once and then behave just like a while statement.

#### For Statement

The for statement is used to iterate over a range of values. There are two styles of for loops, the first uses an initialization, test, and increment to process a block. The second style is designed for iterating through collections and arrays and a variable holds the value of each element in the collection/array and the loop iterates through the entire collection/array.

#### Branching Statements

The **break** statement can be used to escape a control loop.

The **continue** statement jumps to the beginning of the control loop skipping anything that came after it.

The **return** statement exits the current method and returns a value the method expects or nothing in the case of a void method.


### Compile Code

Java needs a compiler to take what we wrote to understand as a human and compile it or translate it for the computer into 1s and 0s in order for the computer to understand what we wrote. Languages like Java and C# need a compiler.
