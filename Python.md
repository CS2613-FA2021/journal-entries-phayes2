# Table of Contents

* [Week One to Three](#week-one-to-three)
  * Syntax and Semantics
  * Data Structures and Libraries
  * Supported Paradigms
  * Under the Hood
  * Conclusion
* References

## Week One to Three
##### September 13th to October 3rd

Isn't it tough to get started on daunting tasks? I find in computer science a lot of things are harder to do than they seem, or at least take a while longer. Maybe this applies to more than computer science, though. It pays to start early and start often, rather than only giving myself five days to complete a big project and start to feel the pressure.

My past semesters have not been too code-heavy, so although I have taken a course using Python, I am coming into this section with Java on the forefront of my brain. The difference, syntax-wise, is very striking to me. In Python, things just work (largely how expected). 

### Syntax and Semantics
### Data Structures and Libraries
### Supported Paradigms

I find Python to be very intuitive and versatile. Python is imperative, like most programming languages we all use (except SQL). The program flows in a line by line way, which helps readability and helps the *programmer* think through the problems in a sub-goal-heuristic kind of way. This is very helpful for me. One exception I've found though is in dictionaries. Sometimes printing a dictionary leads to seemingly random order. Maybe this is less of a Python issue and more of a me issue! Although my expectation is for the order to be how it was added, the [docs](https://docs.python.org/2/tutorial/datastructures.html#dictionaries) say otherwise.

> It is best to think of a dictionary as an unordered set of key: value pairs

Alright then. Next, Python is functional. Things can get pretty complicated with [lambda functions](https://blog.finxter.com/python-one-liners/#Python_One_Line_Quicksort).
```python
q = lambda l: q([x for x in l[1:] if x <= l[0]]) + [l[0]] + q([x for x in l if x > l[0]]) if l else []
```
This is a one-line quick sort and a far-cry from a [java implementation:](https://www.programiz.com/java-programming/examples/quick-sort#:~:text=Quicksort%20in%20Java%20Quicksort%20algorithm%20is%20based%20on,greater%20than%20pivot%20are%20on%20the%20right%20side.)
```java
static void quickSort(int array[], int low, int high) {
    if (low < high) {
      int pi = partition(array, low, high);
      quickSort(array, low, pi - 1);
      quickSort(array, pi + 1, high);
    }
  }
  
  static int partition(int array[], int low, int high) {
    int pivot = array[high];
    int i = (low - 1);

    for (int j = low; j < high; j++) {
      if (array[j] <= pivot) {
        i++;
        int temp = array[i];
        array[i] = array[j];
        array[j] = temp;
      }

    }
```
So Python functions promote stateless functions and are able to get things done with far few less lines of code.

Python is procedural, but you don't have to fuss over where the functions or procedures lay in the structure of the code, which is a bonus. Finally, Python is object oriented which feels largely comfortable coming from mostly using Java. This helps code reusability but can be complicated a lot of the time. You need to know that, for example, objects are pass by reference while strings and ints are pass by value. You mostly learn this the hard way.
### Under the Hood
### Conclusion
### References
* [Dictionaries](https://docs.python.org/2/tutorial/datastructures.html#dictionaries)
* [Functional Programming](https://en.wikipedia.org/wiki/Functional_programming)
* [Programming Paradigms](https://opensource.com/article/19/10/python-programming-paradigms)
* [Python Quicksort](https://blog.finxter.com/python-one-liners/#Python_One_Line_Quicksort)
* [Java Quicksort](https://www.programiz.com/java-programming/examples/quick-sort#:~:text=Quicksort%20in%20Java%20Quicksort%20algorithm%20is%20based%20on,greater%20than%20pivot%20are%20on%20the%20right%20side.)
