## java imports

Java classes can be grouped together into directories refered to as **packages**. An optional package declaration can be added to the top of a source file. A java file in a folder named "basics" could be declared `package basics;`.

The imports section follows the optional package declaration section. Imports can be made with the `import` keyword followed by the package to be imported. 

- The asterix `*` wildcard character can be used to make all classes inside a package availible e.g. `import java.time.format.*;`
- Instead of importing needed classes can be used fully qualified e.g. `java.util.Random rand = new java.util.Random();`


### Loops

#### For Loop

- A loop that uses a counter that is initalized and is incremented or decremented looping through a set of steps. Usually used for traversing arrays.

#### Enhanced For-Each loop

- A For loop that iterates through each index of an array, and stops when it gets through the entire array.

#### While Loop

- While loops continues a set of steps while its boolean statement is true. Usually used when we don't know how maany times we need the loop to run.

#### Do-while Loop

Do wile is like the while loop but loops through the set of steps first and then evaluetes its condition to conitinue