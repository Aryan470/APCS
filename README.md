# APCS 2020 Review
Welcome to the APCS review, here you will find content summaries of each unit along with code examples to help you build a conceptual and practical understanding of the content.
Units on Exam (Covered):

    1. Primitive Types
    2. Objects
    3. Boolean Logic and Conditionals
    4. Iteration
    5. Classes
    6. Arrays
    7. ArrayLists
Units not on 2020 exam:

    8. 2D Arrays
    9. Inheritance
    10. Recursion

## Minimal Fundamentals
In this section we will go over the very basics of Java to give you a quick refresher. You can probably skip over this.


```Java
// Variable declaration is:
// Type name;
int num;

// Variable initialization is:
// name = value;
num = 5;

// Both can be combined with:
// Type name = value;
int x = 4;

// Basic math is performed with:
// + - * / %
x + 5 == 4 + 5;
// Modulo (%) is the remainder in division, ex:
x % 3 == 1;

// A shorthand for changing a variables value:
x = x + 5;
x += 5;

// Output is done like this:
System.out.print("print");
System.out.println("println");
System.out.println("println2");
// print() is used for printing text without moving to the next line
// println() prints the text, and "presses enter"
```

    printprintln
    println2


## Primitive Types
The types to be seen on the exam are:
+ `int` (whole numbers)
+ `double` (decimal numbers)
+ `boolean` (true or false values)
+ `char` (single characters)
+ not primitive but important: `String` (text, an array of characters)

Tips:
+ Integer division will truncate the result, as seen below. For precision beyond whole numbers, use doubles
+ Generally, one uses `==` to compare two variables. With strings you have to use `.equals()` to check equality
+ Boolean logic is easiest to evaluate inside out
+ When converting between types, you must cast to the desired type

Boolean comparison table:

|   a   | operator |   b   | result |
|:-----:|:--------:|:-----:|:------:|
|  true |    &&    |  true |  true  |
| false |    &&    | false |  false |
|  true |   \|\|   |  true |  true  |
| false |   \|\|   | false |  false |
|  true |    &&    | false |  false |
|  true |   \|\|   | false |  true  |



```Java
// Integer usage:
int a = 5;
int b = 2;

System.out.println("--Integers--");
System.out.println(a + " + " + b + " = " + (a + b));
System.out.println(a + " - " + b + " = " + (a - b));
System.out.println(a + " * " + b + " = " + (a * b));
System.out.println(a + " / " + b + " = " + (a / b));
```

    --Integers--
    5 + 2 = 7
    5 - 2 = 3
    5 * 2 = 10
    5 / 2 = 2



```Java
// Double usage:
double a = 20;
double b = 0.5;

System.out.println("--Doubles--");
System.out.println(a + " + " + b + " = " + (a + b));
System.out.println(a + " - " + b + " = " + (a - b));
System.out.println(a + " * " + b + " = " + (a * b));
System.out.println(a + " / " + b + " = " + (a / b));
```

    --Doubles--
    20.0 + 0.5 = 20.5
    20.0 - 0.5 = 19.5
    20.0 * 0.5 = 10.0
    20.0 / 0.5 = 40.0



```Java
// Boolean usage:
boolean a = true;
boolean b = false;

System.out.println("--Booleans--");
System.out.println("Negation:");
System.out.println("!" + a + " = " + !a);
System.out.println("!" + b + " = " + !b);
System.out.println();

System.out.println("Boolean Operators:");
System.out.println(a + "  && " + a + " = " + (a && a));
System.out.println(b + " && " + b + " = " + (b && b));
System.out.println();

System.out.println(a + "  || " + a + " = " + (a || a));
System.out.println(b + " || " + b + " = " + (b || b));
System.out.println();

System.out.println(a + " && " + b + " = " + (a && b));
System.out.println(a + " || " + b + " = " + (a || b));
```

    --Booleans--
    Negation:
    !true = false
    !false = true
    
    Boolean Operators:
    true  && true = true
    false && false = false
    
    true  || true = true
    false || false = false
    
    true && false = false
    true || false = true



```Java
// Basic String usage
String name = "Will";
System.out.println("Name: " + name);
```

    Name: Will



```Java
// Casting
int x = 10;
double newx = (double) (x);

double y = 2.5;
int newy = (int) (y);

System.out.println(x + " -> " + newx);
System.out.println(y + " -> " + newy);
```

    10 -> 10.0
    2.5 -> 2


## Using Objects
Here we'll review some commonly used objects such as the `Math`, `Scanner`, `String` classes.
+ `Math`: has methods for more complex mathematical tasks.
+ `Scanner`: used to get input from the console or files
+ `String`: array of chars for storing text

Important String methods:
+ `length()`: returns the length of the string. ex: `"abcde".length()` will be `5`
+ `substring(int a)`: returns the string starting at index `a`. ex: `"01234".substring(2)` will be `"234"`
+ `substring(int a, int b)`: returns the string starting at index `a`, ending at `b` exclusive. ex: `"01234".substring(1, 3)` will be `"12"`
+ `charAt(int a)`: returns the char at index `a`. ex: `"abcde".charAt(2)` is `'c'`
+ `indexOf(String target)`: returns index of `target` in the string, and `-1` if not found. ex: `"abc april".indexOf("bc")` is `1`
+ `split(String delimiter)`: splits the string up by the delimeter and returns the array of results. ex: `"word1 word2".split(" ")` is `["word1", "word2"]`

    Note: you can add strings or characters with +. ex: `"abc" + "def"` will give `"abcdef"`


```Java
// Common Math methods:
System.out.println("sqrt(9): " + Math.sqrt(9));
System.out.println("3^2 or pow(3, 2): " + Math.pow(3, 2));
System.out.println("ln(2.71828) -> log(): " + Math.log(2.71828));
System.out.println("log10(1000) -> log10(): " + Math.log10(1000));
System.out.println();

System.out.println("random in [0.0, 1.0) -> random(): " + Math.random());
System.out.println("random in [0.0, 5.0) -> random() * 5: " + Math.random() * 5);
System.out.println("random in [-1.0, 1.0) -> random() * 2 - 1.0: " + (Math.random() * 2 - 1.0));
System.out.println();

// Common Math constants:
System.out.println("Math.PI: " + Math.PI);
System.out.println("Math.E: " + Math.E);
```

    sqrt(9): 3.0
    3^2 or pow(3, 2): 9.0
    ln(2.71828) -> log(): 0.999999327347282
    log10(1000) -> log10(): 3.0
    
    random in [0.0, 1.0) -> random(): 0.95824668787821
    random in [0.0, 5.0) -> random() * 5: 1.6931239557560436
    random in [-1.0, 1.0) -> random() * 2 - 1.0: -0.6449271552879705
    
    Math.PI: 3.141592653589793
    Math.E: 2.718281828459045



```Java
// Scanner usage:
// 1. Declare and initialize for console input
// Type name = new Type();
Scanner console = new Scanner(System.in);

// Show prompt
System.out.print("Enter a number: ");
// calling console.nextInt() will get int from user
// console.next() gives a word
// console.nextDouble() gives double
int x = console.nextInt();
System.out.println("Number you entered: " + x);
```

    Enter a number: 

     5


    Number you entered: 5



```Java
// Scanner can also be used on a string
String text = "apcs will be the easiest exam";
Scanner textReader = new Scanner(text);

System.out.println(textReader.next());
System.out.println(textReader.next());
System.out.println(textReader.next());
```

    apcs
    will
    be



```Java
// String usage
String text = "apcs will be the easiest exam";

// Adding indexes for reference:
System.out.print("index:");
for (int i = 0; i < text.length(); i++) System.out.print(i % 10);
System.out.println("\ntext: " + text);
System.out.println("text.length(): " + text.length());
System.out.println("text.substring(11): " + text.substring(11));
System.out.println("text.substring(0, 11): " + text.substring(0, 11));
System.out.println("text.charAt(13): " + text.charAt(13));
System.out.println("text.indexOf(\"easiest\"): " + text.indexOf("easiest"));
System.out.println("text.split(\" \"): " + Arrays.toString(text.split(" ")));
System.out.println("text.split(\"e\"): " + Arrays.toString(text.split("e")));
```

    index:01234567890123456789012345678
    text: apcs will be the easiest exam
    text.length(): 29
    text.substring(11): e the easiest exam
    text.substring(0, 11): apcs will b
    text.charAt(13): t
    text.indexOf("easiest"): 17
    text.split(" "): [apcs, will, be, the, easiest, exam]
    text.split("e"): [apcs will b,  th,  , asi, st , xam]


## Booleans and Conditionals
In this section we will review boolean usage and conditional statements

Conditional structures:
+ `if (this) {A}`: if `this` is true, then run `A`
+ `if (this) {A} else {B}`: same as first, but if `this` is false, run `B`. Only A or B can be run, not both
+ `if (this) {A} else if (that) {B} else {C}` same as second but if `that` is true, then run `B`. Only one of A, B, or C can be run.


```Java
int x = 5;
int y = 6;

if (x == y) {
    System.out.println("x == y");
} else if (x + 1 == y) {
    System.out.println("x + 1 == y");
} else {
    System.out.println("x != y and x + 1 != y");
}
```

    x + 1 == y



```Java
if (x == y - 1) {
    System.out.println("x == y - 1");
}
if (x + 1 == y) {
    System.out.println("x + 1 == y");
}
```

    x == y - 1
    x + 1 == y



```Java
boolean a = true;
boolean b = false;
if (a && b) {
    System.out.println("a and b are true");
} else if (a != b) {
    System.out.println("a is not b");
}

if (a || b) {
    System.out.println("a or b is true");
}
```

    a is not b
    a or b is true


## Iteration
Here we'll review iterative structures such as the for loop and while loop

Tips:
+ Use for loop for a known number of iterations
+ Use while loop for an unknown number

For Loop Syntax:

```java
for (init; condition; statement) {
    code;
}
```

Upon reaching the for loop, `init` is run. Then, if `condition` is true, `code` will be run. Next, `statement` is run. `condition` is checked again and the process cycles.

`init`->`condition`->`code`->`statement`->`condition`


```Java
for (int i = 0; i < 5; i++) {
    System.out.print(i);
}
```

    01234


```Java
for (int i = 10; i > 0; i--) {
    System.out.print(i + " ");
}
```

    10 9 8 7 6 5 4 3 2 1 


```Java
for (int i = 1; i < 10; i *= 2) {
    System.out.print(i + " ");
}
```

    1 2 4 8 

While Loop Syntax:

    while (condition) {
        code;
    }

Upon reaching the loop, if `condition` is true, `code` will be run. Then `condition` is checked again, and it keeps running.


```Java
int numPeople = 10;
int numPizzas = 0;

System.out.println("People: " + numPeople);
System.out.println("Pizzas: " + numPizzas);
```

    People: 10
    Pizzas: 0



```Java
while (numPizzas < numPeople) {
    numPizzas += 1;
}

System.out.println("People: " + numPeople);
System.out.println("Pizzas: " + numPizzas);
```

    People: 10
    Pizzas: 10



```Java
while (numPeople > 0) {
    numPeople -= 1;
}

System.out.println("People: " + numPeople);
System.out.println("Pizzas: " + numPizzas);
```

    People: 0
    Pizzas: 10


## Writing Classes
This is by far one of the most intricate topics in APCS, so we will do an in depth review.

A class is a "template" for an object. For example, if `Car` is a class, then the object is `myHondaAccord`. An object (instance) is an example of a class. `lily` is an instance of the `Dog` class. Classes and objects are defined by 2 things, state and behavior. These are represented with fields (variables) and methods respectively. Take an example `Dog` class:


```Java
// For convenience, I will not make the instance fields public. Know that they 100% should be private.
// Class header
public class Dog {
    // Instance Fields
    String name;
    
    // Static Fields
    static int numLegs = 4;
    static String foodType = "meat";
    
    // Constructor
    public Dog(String name) {
        this.name = name;
    }
    
    // Instance method bark
    public void bark() {
        System.out.println("woof");
    }
    
    // Static method getFoodType
    public static String getFoodType() {
        return foodType;
    }
    
    public String toString() {
        return name + " (Dog)";
    }
}
```

### Fields
The distinction between classes and objects allows us to define 2 types of fields and methods: static (shared) and instance (individual). A static field in the `Dog` class could be `hasTail`, a boolean with a value that is the same across all instances. An instance field would be `name`, which varies depending on which instance (dog) you are talking about. The purpose of static fields is general values such as constants across all instances. Static fields can be accessed with `Type.field` while instance fields are accessed with `object.field`. Another thing to note is that there is only one value of a static field that is used by all instances, where instance fields are unique and private. Take a look at this example:


```Java
Dog lily = new Dog("Lily");

System.out.println(lily.name); // "Lily"
System.out.println(Dog.numLegs); // 4

System.out.println(lily.numLegs); // 4
System.out.println(Dog.name); // does not exist, will cause error
```

    Lily
    4
    4



    |   System.out.println(Dog.name); // does not exist, will cause error

    non-static variable name cannot be referenced from a static context

    


### Methods
We have the same thing with methods, where static methods are shared across instances and vice versa. Static methods are used for utility operations whereas instance methods are used when the method needs information from instance fields for an action specific to one instance. Here's an example:


```Java
Dog lily = new Dog("Lily");

System.out.println(Dog.getFoodType()); // "meat"
System.out.println(lily.getFoodType()); // "meat"

lily.bark(); // Lily barks
Dog.bark(); // this doesn't work, will cause error
```

    meat
    meat
    woof



    |   Dog.bark(); // this doesn't work, will cause error

    non-static method bark() cannot be referenced from a static context

    


### Constructors
Here is the constructor from the `Dog` class, let's take a closer look at it.
```java
public Dog(String name) {
    this.name = name;
}
```
The important things here are the header and the instance field assignment. The header for any constructor will be `public Type(params)` where `Type` is the name of the class. This is an important thing to remember as it's different from other methods.

Next, look at the line in the constructor. Since we have a collision between the instance field `name` and the parameter `name`, how will the computer know which is which? We use the `this` keyword to solve this. The `this` keyword will always refer to this instance, so in the line in the constructor we are setting the instance field `this.name` to the parameter `name`'s value.

### toString()
The `toString` method is an optional method included in classes that is used whenever an instance is referred to as a string. This is more straightforward than it sounds. Look at the `toString` for the `Dog` class:

```java
public String toString() {
    return name + " (Dog)";
}
```

Whenever this method is called, it will return the `name` of the `Dog` it was called on plus some clarification as to the class. The toString method makes it much easier to display the state of the instance. We can see this in action with a simple comparison between the `Dog` toString and the default `Object` toString:


```Java
Dog lily = new Dog("Lily");
Object bad = new Object();

System.out.println(lily);
System.out.println(bad);
```

    Lily (Dog)
    java.lang.Object@a8bd490


### A proper example
This is a `Vector` class I wrote awhile ago, and I think it would be useful to read through the annotations and understand the design choices made.


```Java
public class Vector {
    // Instance fields
    private int x;
    private int y;
    
    // i and j basis vectors, static because constants
    public static final Vector i = new Vector(1, 0);
    public static final Vector j = new Vector(0, 1);

    // Constructor to take (x, y) and make new vector
    public Vector(int x, int y) {
        this.x = x;
        this.y = y;
    }
    
    // Constructor to duplicate another vector
    public Vector(Vector v) {
        this.x = v.getX();
        this.y = v.getY();
    }

    // Find the distance from this vector to the other:
    // d(v1, v2) = sqrt((dx)^2 + (dy)^2)
    public double getDistance(Vector v) {
        int dx = v.getX() - x;
        int dy = v.getY() - y;
        return Math.sqrt(dx * dx + dy * dy);
    }

    // Add two vectors: V1 + V2 = [V1x + V2x, V1y + V2y]
    public Vector addVector(Vector v) {
        int newX = x + v.getX();
        int newY = y + v.getY();
        return new Vector(newX, newY);
    }

    // Scale a vector: V * k = [Vx * k, Vy * k]
    public Vector scale(double scalar) {
        int newX = (int) (x * scalar);
        int newY = (int) (y * scalar);
        return new Vector(newX, newY);
    }

    // Get the X value
    public int getX() { return x; }

    // Get the Y value
    public int getY() { return y; }

    // Show vector state
    public String toString() {
        return "(" + x + ", " + y + ")";
    }
}
```


```Java
Vector V1 = new Vector(1, 2);
Vector V2 = new Vector(4, 6);
System.out.println("i: " + Vector.i);
System.out.println("j: " + Vector.j);
System.out.println();

System.out.println("V1: " + V1);
System.out.println("V2: " + V2);
System.out.println();

System.out.println("V1.getDistance(V2): " + V1.getDistance(V2));
System.out.println("V1.addVector(V2): " + V1.addVector(V2));
System.out.println("V1.scale(2): " + V1.scale(2));
```

    i: (1, 0)
    j: (0, 1)
    
    V1: (1, 2)
    V2: (4, 6)
    
    V1.getDistance(V2): 5.0
    V1.addVector(V2): (5, 8)
    V1.scale(2): (2, 4)
