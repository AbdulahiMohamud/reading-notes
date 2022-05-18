## Primitives vs. Objects

From the article on [Baeldung](https://www.baeldung.com/java-primitives-vs-objects)

When working with very large collections or systems with low resources, the decisions made about data types can have a big impact. In most cases primitive types are much faster and require less memory but come with the trade off that they aren't allowed in parametrized types e.g. `ArrayList<Integer>`.

- The memory footprint of primitives double and long have a larger footprint than the object wrapper classes.
- Wrapper object classes have an advantage in default values because they all default to null until primitives, although this is less useful since leaving variables uninitialized is poor practice to begin with.

![memory useage](../img/plot-memory-bits.gif)
Image Credit  [Baeldung](https://www.baeldung.com/java-primitives-vs-objects)


### Terms

**Autoboxing** is a conversion that the Java compiler automatically does when a object wrapper class is assigned to a primitive e.g. `Integer myInt = 25`

**Unboxing** is the opposite conversion when an a primitive is assigned to a object wrapper class e.g. `char myChar = new Char('Z')`

## Exceptions in Java

From the [Oracle Java Documentation](https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html)

### What is an Exception?

An exception is an object that a method will create when an error occurs. The object is passed up the call stack looking for a handler to deal with the exception object. If the runtime system doesn't find a handler and exhausts the stack then the program and runtime terminate.

### The Catch or Specify Requirement

Certain exceptions require a Catch or Specify Requirement, and without this the code will not compile. **Checked** exceptions have these requirements. Checked exceptions are exceptions that the program should anticipate and recover from. Typically this is related to user prompts for data.

Another category of exception is an error. Errors come from sources external to the program and the application can not usually anticipate or recover. Often this is related to hardware and system malfunctions.

The last type of exception is a runtime exception. This type of exception usually comes from buggy software or miss-used APIs. Instead of trying to deal with these exceptions it is better to remove the bug from the program.

### Catching and Handling Exceptions

The **try block** is a code block that contains the code that has the chance of throwing an exception. Commonly code used for accessing the file system goes in a try block.

The **catch block** will follow a try block and contain an named exception handler. Multiple catch blocks can follow a try block for dealing with multiple types of exceptions. Each catch block has code that will run if its exception handler is invoked. The runtime system will invoke the first catch block that matches the exception and is moves through that call stack. The `|` can be used to separate if multiple exception handlers are wanted in a single catch block.

The **finally block** follows the catch block(s) and this block of code is invoked whether or not an exception occurs in the try block. It is helpful for cleanup if an unexpected exception occurs that were not identified in the catch block. It's also commonly used to prevent memory leaks by placing code here to recover resources.

The **try-with-resources statement** adds parenthesis right after the keyword try, and resources can be declared in here that are ensured to close at the end of the statement.

Summary example from the Oracle Java Docs:
```java
public void writeList() {
    PrintWriter out = null;

    try {
        System.out.println("Entering" + " try statement");

        out = new PrintWriter(new FileWriter("OutFile.txt"));
        for (int i = 0; i < SIZE; i++) {
            out.println("Value at: " + i + " = " + list.get(i));
        }
    } catch (IndexOutOfBoundsException e) {
        System.err.println("Caught IndexOutOfBoundsException: "
                           +  e.getMessage());
                                 
    } catch (IOException e) {
        System.err.println("Caught IOException: " +  e.getMessage());
                                 
    } finally {
        if (out != null) {
            System.out.println("Closing PrintWriter");
            out.close();
        } 
        else {
            System.out.println("PrintWriter not open");
        }
    }
}
```


## Scanner Objects

From the [Oracle Java Documentation](https://docs.oracle.com/javase/tutorial/essential/io/scanning.html)

A scanner can be used to parse primitive types and strings. We can use scanners to traverse external files and get tokens one at a time. Various types of scanners and methods can be enacted to change the behavior of the scanner like assigning a specific delimiter or seeking the next specific primitive type.

Example from Oracle Java Docs of a simple text file tokenized:

```java
import java.io.*;
import java.util.Scanner;

public class ScanXan {
    public static void main(String[] args) throws IOException {

        Scanner s = null;

        try {
            s = new Scanner(new BufferedReader(new FileReader("xanadu.txt")));

            while (s.hasNext()) {
                System.out.println(s.next());
            }
        } finally {
            if (s != null) {
                s.close();
            }
        }
    }
}
```
