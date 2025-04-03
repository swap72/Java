# Java Coding Standards



* [Naming](https://cscie22.sites.fas.harvard.edu/problem_sets/coding_standards.html#naming)
* [Curly Braces](https://cscie22.sites.fas.harvard.edu/problem_sets/coding_standards.html#curly-braces)
* [Indentation and Whitespace](https://cscie22.sites.fas.harvard.edu/problem_sets/coding_standards.html#indentation-and-whitespace)
* [Comments](https://cscie22.sites.fas.harvard.edu/problem_sets/coding_standards.html#comments)
* [Miscellaneous](https://cscie22.sites.fas.harvard.edu/problem_sets/coding_standards.html#miscellaneous)
	+ [Keep Line Lengths Under 80 characters](https://cscie22.sites.fas.harvard.edu/problem_sets/coding_standards.html#keep-line-lengths-under-80-characters)



## Naming


Choose your names carefully. As part of program documentation, names
must clearly indicate both the kind of thing being named and its role in
the program. Whenever possible, write short, obvious names for very
local contexts (i.e., a `for` loop counter could be called `i`) and
longer names for bigger contexts (examples to follow). Avoid cryptic
abbreviations (e.g.,use `incrementEventCount()` rather than
`incEvCnt()`). Avoid choosing similar names for different things, e.g.,
`index, indx, index2;` or, on the other hand, similar names for very
different things (example: if `keys[]` is a array of strings, then don’t
use `key` for an integer `for` loop counter).


* **Fields and Local Variables:** A noun phrase, starting with a
 lower-case letter, with multiple words distinguished by
 capitalization, e.g., `eventCount`, `numberOfBasicOperations`.
* **Constants:** A noun phrase in all capitals, with multiple words
 separated by underscore “\_”, e.g., `MAX_SIZE`.
* **Classes and Interfaces:** Same as field and variable names except
 starting with a capital letter, e.g., `Point`, `GeometryDemo`.
 Interfaces should usually be an adjective, e.g.,
 `Throwable`, `Comparable`.
* **Methods:** A imperative verb phrase (if possible), otherwise in
 same format as with field and variable names, e.g.,
 `findMedian()`, `incrementEventCount()`. Accessor methods should start
 with “get”, mutator methods should start with “set”, and a method
 returning a boolean should (if possible) start with “is” or “has”,
 e.g., `getEventCount()`, `setEventCount()`, `isDone()`, `hasNext()`.


## Curly Braces


Curly braces delimit the bodies of classes, methods, and loops. There
are two standard formats for braces, either of which is acceptable:


1. Curly brace goes at the end of the line that starts the class,
 method, loop, etc., and the closing brace is on a line by itself, lined
 up vertically with the start of the first line:



```
public class SomeClass {
    ...
    public SomeClass() {
    ...;
    }

    public int someMethod(int n, float m) {
        ...;
        for (int i = 0; i < someField; i++) {
            ...;
        }
        ...;
    }
}

```

2. Each curly brace is on a new line, and a pair is lined up
 vertically. The previous code in this format would look like this:



```
public class SomeClass
{
    ...
    public SomeClass()
    {
        ...;
    }
    public int someMethod(int n, float m)
    {
        ...;
        for (int i = 0; i < someField; i++) {
            ...;
        }
        ...;
    }
}

```



## Indentation and Whitespace


The placement of syntax on the page is one of the most important aspects
of style and readability, and has three aspects: horizontal placement is
achieved by


1. using spaces or tab stops to indent lines of code and
 other similar items (such as variables in a series of declarations),
2. for inserting “oxygen” around operators and punctuation, and
 vertical placement is achieved by
3. inserting blank lines to separate classes, members of classes, and regions
 of code with various purposes.


The usual standard for indentation is to **indent by four spaces whenever you
are inside a set of curly braces.**


For example:



```
public class SomeClass {
    private int someField; 
    private double anotherField; 
    public SomeClass() { // Constructor
        someField=1;

        anotherField = 3.14; // Initialize all fields
    } 
    public int someMethod(int n,float m) {
        int localVariable=0; // Must initialize local variables
        float anotherLocalVariable=1; // This one too
        localVariable=n-2;
        anotherLocalVariable=localVariable+m*3; 
        for(int i=0;i<someField;i++) {
            localVariable=localVariable*2;
            localVariable=localVariable-someField;
        }
        return localVariable+n;
    }
}

```

This example is not in fact very readable, as it it hard to parse the
structure of the individual lines; the usual standard for increasing
readability of each line is:


* **Indent similar items** in a vertical list (such as end-of-line
 comments, and identifiers in declarations);
* **Surround the binary operators (including assignment) by spaces;**
* **Follow a semicolon or comma by a space;**
* **Put a space between a keyword and a following parenthesis** (e.g.,
 if, while, return, catch, switch, for); and
* **Superfluous parentheses** can also help to emphasize the structure
 of expressions (but not too many nested parentheses).


This example should thus be written as:



```
public class SomeClass {
    private int someField; 
    private double anotherField; 
    public SomeClass() {                   // constructor
        someField = 1; 
        anotherField = 3.14;              
    } 
    public int someMethod(int n, float m) {
        int localVariable = 0;             // must initialize local variables
        float anotherLocalVariable = 1;    // this one, too
        localVariable = (n - 2);
        anotherLocalVariable = localVariable + (m * 3); 
        for (int i = 0; i < someField; i++) {
            localVariable = localVariable * 2;
            localVariable = localVariable - someField;
        }
        return localVariable + n;
    }
}

```

Still too crowded! For vertical arrangement, simply **insert blank lines to
separate important regions of the code:**



```
public class SomeClass {
    private int someField;
    private double anotherField;

    public SomeClass() {                    // constructor
        someField = 1;
        anotherField = 3.14;
    }

    public int someMethod(int n, float m) {
        int localVariable = 0;              // must initialize local variables
        float anotherLocalVariable = 1;     // this one, too

        localVariable = n - 2;
        anotherLocalVariable = localVariable + m * 3;

        for (int i = 0; i < someField; i++) {
            localVariable = localVariable * 2;
            localVariable = localVariable - someField;
        }

        return localVariable + n;
    }
}

```

## Comments


Comments should help the reader of your code to understand it. They may
help *you* to understand it if you need to rework your code at some later
point. In the case of a programs submitted for a course, they also serve
to convince the grader that you grasp the what, how and why of your code
(as opposed to having hacked it into working). Like any other form of
expression, it should not be flowery or repetitive. In particular,
please observe the following guidelines:


* *Header comments* (see below) should use the multi-line comment
 style (i.e., use `\*` and `*/`) and all other comments should use the
 single-line (i.e., use `//`) convention. This is because you can surround
 single-line comments with a multi-line comment, but not multi-line
 around multi-line — if you want to comment out a region of code during
 development, and you used multi-line comments everywhere, you are
 stuck.


* Single-line (i.e., `//`) comments should either line up with code
 or appear to the right of the code, with a somewhat-consistent
 indentation, as shown previously. These should be
 indented along with the code they accompany.


* Each file should have a *header comment block* at the
 top of the file, giving all the essential information about the file
 and the class or classes defined therein. In the following example,
 the first four categories of information are considered absolutely
 essential. If you use another person’s code as part of your program,
 a credits clause such as the one shown below must be included.



```
 /*
 * Customer.java
 * by Alan Turing (aturing@cambridge.edu)
 * 2/4/2004
 *
 * This class represents a bank customer. It contains basic
 * fields and references to the customer's accounts.
 *
 * Note that the main() method's input data file must be
 * called "finance\_data.txt". For the format of this
 * file, see comment above the getData() method.
 *
 * Credits: The code for the hash table in the
 * calculateInterestRate() method was taken from
 * "Algorithms and Data Structures," by George Guidal, pp. 234-35.
 */

```

* **For each significant field or variable declaration**, give a brief
 comment stating the use of the variable, and when useful, the units
 (e.g., feet or inches).



```
// distance in inches from base of rectangle
int x;

for (x = 0; x < sizeOfArray; x++) {
    gravitationalForce[x] = 0;
}

```

Non-significant variables (not requiring explanation) would include
temporary variables, loop counters, and so on.


* **When it helps to understand your code, before each major section**
 of the program, give the purpose of that section. Indent the
 comments to line up with the code.


* **Give end-of-line comments** for any line of code that is trickly,
 or non-obvious; don’t overdo this, and don’t just rephrase the Java
 in English, but DO provide concise, informative comments to help the
 reader (who knows Java idioms, but not your code) understand what is
 going on.


* **Before each significant method**, describe the method and give the
 inputs, output and error conditions of the function. Here is one way
 to do it:



```
// This function returns a boolean value which is true if proposedName is
// a name contains a string which follows the guidelines given in this 
// convention for naming functions, otherwise it returns false.
public boolean isMethodName(String proposedName) {
    ...;
}

```

You don’t need to do this for completely obvious methods, such as
one-line mutator methods, etc.


* **Class Comments** Similarly to method comments, any helper class
 defined in a file should have a comment defining its purpose and
 usage. The public class in a file need not have a comment, as that
 is the purpose of the header file.




## Miscellaneous


### Keep Line Lengths Under 80 characters


On many machines and in many software packages, this is a standard line
length. It makes it easier for others (like graders) to read and/or
print your programs. If your parameter list for a method is too long to
fit within 80 characters, then insert line breaks and indent the
remaining lines of parameters:



```
public boolean calculateAverageDailyReturn(int customerID, double dailyBalanceForMonth[], double dailyInterestRate, double discountRate)
{

```

should be rewritten as:



```
public boolean calculateAverageDailyReturn(int customerID,
    double dailyBalanceForMonth[], double dailyInterestRate,
    double discountRate)
{

```

If your `println()` statement is too long, then you should break this up
as well, using the + operator to concatenate strings:



```
System.out.println("The average daily return for customer " + customerID + " at the discount rate " + discountRate + " is " + A);

```

should be rewritten as:



```
System.out.println("The average daily return for customer " + customerID +
    + " at the discount rate " + discountRate + " is " + A);

```



---


Written by: Wayne Snyder (Fall 2004)  

Updated: Alexandra Stefan (Spring 2006), Dave Sullivan (Fall 2006)


Last updated on January 28, 2025.
[Source](https://cscie22.sites.fas.harvard.edu/problem_sets/coding_standards.html)
