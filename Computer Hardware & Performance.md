# Computer Hardware & Performance

YAGNI - You aint gonna need it!

Turing Tape

- A long piece of tape marked off into equal sections
- A machine can move back and forth along the tape
- Each section is refered to as a bit.

8 bits = 1 byte
2^10 (1024) bytes

Swapping
Performing RAM operations on the harddrive when ram is not available.


Algorithm Speed

What order does your algorithm run at?
Order of n. Is there a faster way to do the same thing?

## Big-O notation
As the size of the collection grows, what is the impact of on the amount of time it takes to perform the action. Linear, Constant, Logorithmic, Exponential.

https://www.bigocheatsheet.com/  
https://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation/

### O(n) 

Linear relationship - The number of items in the collection will multiply the amount of time it takes to perform the operation on the collection. 

    Example: Looping through a array to check if something is inside it.

### O(1)
Constant Time - No matter how many items in collection it takes the same amount of time to perform the operation.

    Example: Finding an item in an array by its index. Or by looking up a value in an object by its key.

### O(log n)
Logorithmic Time - Quick for larger numbers in the collection but take longer with less in the collection. 

    Example: Binary Search - go the middle throw away half... continue until you find the item you want  (good for things that are presorted)

### O(n log n)
Exponential Growth - As the collection size grows the time to perform goes up logorithimically.

    Example: Sorting - There are different sorting algorithms for sorting. Fastest is known to run at O(n log n)

O(n) is faster then O(n log n) + O(log n)... but it depends on number in collection and wether your going to save the sorted list for later lookup.

### O(n^2)  - **BAD**

Exponential Growth - As the collection grows the time to perform grows exponentially. 

    Example: A loop with another operation that performs a loop on each item

