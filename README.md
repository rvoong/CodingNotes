# Coding Notes

# 1. Variables

## 1.1 Variables are dynamically typed

    n = 0

## 1.2 Type is determined at run time so n can be reassigned

Input:

    n = "abc"

Output:

    abc

## 1.3 Multiple assignments

Input:

    n, m = 0, "abc"
    n, m, z = 0.125, "abc", False

Output:

    0 abc
    0.125 abc False

## 1.4 Incrementing

    n = n + 1   //good
    n += 1      //good
    n++         //bad

## 1.5 None is null (absence of value)

    n = 3
    n = None

## 1.6 If Statements

If statements don't need parentheses or curly braces. Use indentation to indicate where code corresponds to

    n = 1
    if n > 2:
        n -= 1
    elif n == 2:
        n *= 2
    else:
        n += 2

## 1.7 Logical operations

<ul>
<li> and = && </li>
<li> or = || </li> 
</ul>

    n, m = 1, 2
    if ((n > 2 and n!=m) or n == m):
        n += 1

## 1.8 While Loops

    n = 0
    while n < 5:
        print(n)
        n += 1

## 1.9 For loops i = 0 to i = 4

    for i in range(5)
        print(i)

### 1.10 For loops i = 2 to i = 5

    for i in range(2, 6)
        print(i)

# 2. Array Review

    arr = [1, 2, 3]

## Can be used as a stack

    arr.append(4)
    arr.append(5)

## popping from an array O(1)

    arr.pop()

## inserting is O(n)

    arr.insert(1,7)

## indexing and reassigning are O(n)

    arr[3] = 0

## Initialize arr of size n with default value of 1

    n = 5
    arr =  [1] * n

## Careful : -1 is not out of bounds, it is the last value

    arr = [1, 2, 3]
    print(arr[-1]) # reads the last value
    print(arr[-2]) # reads the second to last value

## Sublists (aka slicing)

    arr = [1, 2, 3, 4]
    print(arr[1:3]) # does not include 3

## Similar to for-loop ranges, last index is non-incluesive

    print(arr[0:4])

## Unpacking

    a, b, c = [1, 2, 3]
    print (a, b, c)

## Loop through arrays

    nums = [1, 2, 3]

## Using Index

    for i in range(len(nums)):
        print(nums[i])

## Without Index

    for n in nums:
        print(n)

## With index and value

    for i, n in enumerate(nums):
        print(i, n)

## Loop through multiple arrays simultaneously with unpacking

    nums1 = [1, 2 ,3]
    nums2 = [4, 5, 6]
    for n1, n2 in zip(nums1, nums2):
        print(n1, n2)

Output:
1 2
3 4
5 6

## Reversing array

    nums = [1, 2 ,3]
    nums.reverse()

## Sorting array

    arr = [5, 4, 7, 3, 8]
    arr.sort()

## Sort in reverse

    arr.sort(reverse=True)

## Sorting list of strings

By default it will be sorted in alphabetical order

    arr = ["bob", "alice", "jane", "doe"]
    arr.sort()

## Custom sort (by length of string)

    arr.sort(key=lambda x: len(x))

Output:

    ['bob', 'doe', 'jane', 'alice']

## List comprehension

Creates an array of the range

    arr = [i for i in range(5)]

Output:

    [0, 1, 2, 3, 4]

## Can add 1 to each value with

    arr = [i+1 for i in range(5)]

## 2-D lists

    arr = [[0]* 4 for i in range(4)]

Output:

    [[0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0]]

## 2-D lists continued

    arr = [0]* 4 for i in range(4)]

## This won't work

    arr = [[0] * 4] * 4

# Strings

    s = "abc"
    print(s[0:2])

## So this creates a new String

Modifying a string is O(n)

    s += "def"
    print(s)

## Valid numeric strings can be converted

    print(int("123") + int("123"))

Output:

    246

## And Numbers can be converted to strings

    print(str(123) + str(123))

Output:

    123123

# ASCII values of a character

    print(ord("a"))
    print(ord("b"))

Output:

    97
    98

## Combine a list of strings (with an empty string delimitor)

    strings = ["ab", "cd", "ef"]
    print("".join(strings))

Output:

    abcdef

# Queues (double ended queue by default)

    from collections import deque

    queue = deque()
    queue.append(1)
    queue.append(2)
    print(queue)

    queue.popleft()
    print(queue)

    queue.appendleft(1)
    print(queue)

    queue.pop()
    print(queue)

Output:

    deque([1, 2])
    deque([2])
    deque([1, 2])
    deque([1])

# HashSets

Search and remove are O(n)

    mySet = set()

    mySet.add(1)
    mySet.add(2)
    print(mySet)
    print(len(mySet))

    print(1 in mySet)
    print(2 in mySet)
    print(3 in mySet)

    mySet.remove(2)
    print(2 in mySet)

Output:

    {1, 2}
    2
    True
    True
    False
    False

## Initializing a hashset

    print (set([1, 2, 3]))

Output:

    {1, 2, 3}

## Set Comprehension

    mySet = {i for i in range(5)}

Output:

    {0, 1, 2, 3, 4}

# HashMap (aka dict)

    myMap = {}
    myMap["alice"] = 88
    myMap["bob"] = 77
    print(myMap)
    print(len(myMap))

    myMap["alice"] = 80
    print(myMap["alice"])

## Time complexity O(n):

    print("alice" in myMap)
    myMap.pop("alice")

## Initializing

    myMap = {"alice": 90, "bob": 70}
    print(myMap)

## Dict compreshension ("fancy")

    myMap = {i: 2*i for i in range(3)}

Output:

    {0: 0, 1: 2, 2: 4}

## Looping through maps

    myMap = {"alice": 90, "bob": 70 }
    for key in myMap:
        print(key, myMap[key])

    for val in myMap.values():
    print(val)

    ## similar to the first loop
    for key, val in myMap.items():
        print(key, val)

# Tuples

    tup = (1, 2, 3)
    print(tup)
    print(tup[0])
    print(tup[-1])

## Can't modify

    tup[0] won't work

## Can be used as key for HashMap/set

    myMap = {(1, 2): 3}
    print(myMap[(1, 2)])

    mySet = set()
    mySet.add((1, 2))
    print((1, 2) in mySet)

## Lists can't be keys

    myMap[[3,4]] = 5

# Heaps:

Binary trees for which every parent node has a value less than or equal to any of its children
Common to find the min and max

    import heapq

## Under the hood, heaps are arrays

    minHeap = []
    heapq.heappush(minHeap, 3)
    heapq.heappush(minHeap, 2)
    heapq.heappush(minHeap, 4)

## Min is always at index [0]

    print(minHeap[0])

## Loop through a heap while it is non-zero

    while len(minHeap):
        print(heapq.heappop(minHeap))

Output:

    2
    2
    3
    4

There are no max heaps by default, work around is to use min heap and multiply by -1 when push and pop

    maxHeap = []
    heapq.heappush(maxHeap, -3)
    heapq.heappush(maxHeap, -2)
    heapq.heappush(maxHeap, -4)

## Max is always at index 0

    print(-1 * maxHeap[0])

    while len(maxHeap):
        print(-1 * heapq.heappop(maxHeap))

Output:

    4
    4
    3
    2

## Building a heap from initial values

    arr = [2, 1, 8, 4, 5]
    heapq.heapify(arr)
    while arr:
        print(heapq.heappop(arr))

# Functions

    def myFunc(n, m):
        return n * m

    print(myFunc(3, 4))

## Nested Functions have access to outer variables

    def outer(a, b):
        c = "c"

        def inner()
        return a + b + can

    print(outer("a", "b"))

Output:

    abc

## Can modify objects, but cannot reassign unless nonlocal keyword is used

    def double(arr, val):
        def helper():
            #Modifying array works
            for i, n in enumerate(arr):
                arr[i] *=2

            # will only modify val in the helper scope
            # val *= 2

            # this will modify val outside helper scope
            nonlocal val
            val *= 2
        helper()
        print(arr, val)

    nums = [1, 2]
    val = 3
    double(nums, val)

Output:

    [2, 4] 6

# Class

    class My Class:
        #Constructor
        def __init__(self, nums):
            # Create member variables
            # self is similiar to this
            self.nums = nums
            self.size = len(nums)

        #self key word required as param
        def getLength(self):
            return self.size

        # calling another member function of the class
        def getDoubleLength(self):
            return 2* self.getLength()


      ```javascript
      function Person() {}
      Person.prototype.name = "Sudheer";
      var object = new Person();
      ```
