# DataStructureNotes

## Matrix example

```python
# Python 3 Representation of matrix A

matrix_A = [
    [1, 2, 3, 4],
    [5, 6, 7, 8]
]

# Accessing Matrix A
print('Row 1: %s' % matrix_A[0]) # Recall: Indexing starts at zero in Python
print('Value at Row 2 Column 2: %s' % matrix_A[1][1])
```

Row 1: [1, 2, 3, 4]
Value at Row 2 Column 2: 6
In Python 3, there is no data structure called a "Matrix".

Therefore, we are programming a list within a list and following the rules of a regular matrix:
- All rows must have the same number of values
- All columns must have the same number of values
- All items in the 2D List must have the same data types
- Since indexing always starts at 0 ... row 1 is technically located at matrix_A[0]

### List Comprehension

The list is a result of some operations applied to all its items
It is a made from another sequence/iterable data
The list is member of another list/sequence/iterable data that satisfies a certain condition

List Comprehension consists of a square bracket containing an expression that describes the list. 
It also includes one or more __For Clauses__ depending on the complexity of the list

##### List Comprehension Examples
```python
# Old Method
squares = []
for i in range(10):
    squares.append(i ** 2)

print('Our result: %s' % squares)
Our result: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
# List Comprehension

squares = [i**2 for i in range(10)]

print('Our new result: %s' % squares)
Our new result: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

```python
# Solution
a = [1,2,3]
b = [3,1,4]

result = [[x, y] for x in a for y in b if x != y]
print(result)
```
The result is [[1, 3], [1, 4], [2, 3], [2, 1], [2, 4], [3, 1], [3, 4]]

# Map & Filter

The idea of a map function is to apply a function to an iterable data.

##### Format 
the formatting is: map(FunctionName, Sequence)

##### Example
```python
# Example
def square(num):
    ''' squares the given num argument '''
    return num ** 2
# end of square

array = list(range(1,11))
square_array = list(map(square, array))

print('Original Array:', array)
print('Array Squared:', square_array)
```
The output:
Original Array: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
Array Squared: [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

The map function doesn't return a specific data type, but instead it returns iterable data. Therefore, it can be used to execute a list function in it

##### Example of executing list function 
```python
# Example 2

def upper(x):
    ''' upper() turns string x into its uppercased counter part '''
    return x.upper()

word = 'hello world!'
upper_word = ''.join(list(map(upper, word)))

print(word)
print(upper_word)

# simpler way:
print(word.upper())
```

The output: 
hello world!
HELLO WORLD!
HELLO WORLD!

## Filter FUnction
The idea of the filter function is to filter out items from a data set that meets a certain condition.
##### Example
```python
# Example 3

def isOdd(x):
    ''' isOdd() returns True if x is odd.'''
    return x % 2 != 0

array = list(range(1,101))
odds = list(filter(isOdd, array))

print('Odd Numbers from 1 to 100:', odds)
```
The output: 
Odd Numbers from 1 to 100: [1, 3, 5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 51, 53, 55, 57, 59, 61, 63, 65, 67, 69, 71, 73, 75, 77, 79, 81, 83, 85, 87, 89, 91, 93, 95, 97, 99]


# Tuples

strings and lists are basic iterable data types that are very similar with some differences which consist of only allowing alphanumeric characters and special symbols to represent text for strings. Lists allow all data types as its items. Strings are immutable while Lists are mutable

These differences are why Tuples exist. 

#### How to use Tuples

Example

```python
tup = ('C', ' Java', 'Python')
empty_tup = ()
single_tup = ('Park',)

print(tup)
print(empty_tup)
print(single_tup)
```
The output: 
('C', ' Java', 'Python')
()
('Park',)

### Tuple Operators
```python 
# Concatenation: Joining two tuples
a = (1,2,3)
b = (4,5,6)
concat_result = a + b
print('a+b:', concat_result)


# Repetition: Repeating a list multiple times
c = ('Hi!',)
repet_result = c * 3
print('c*3', repet_result)

# Membership: Check if a value exists in a tuple
d = a + b + c
print('d:', d)
print('\'Hi!\' in d:', 'Hi!' in d)
print('7 in d:', 7 in d)
```
Output: 
a+b: (1, 2, 3, 4, 5, 6)
c*3 ('Hi!', 'Hi!', 'Hi!')
d: (1, 2, 3, 4, 5, 6, 'Hi!')
'Hi!' in d: True
7 in d: False

Tuples are iterable, indexable and sliceable


# Sets

A set is an unordered collection with no duplicate elements in Python 3.

Set is a mathematical way to describe collection of different unique objects.

By following the operations and characteristics of the mathematical set, we can utilizie such data structure in our Python code.

Example: 
```python 
# Set definition examples:
example_set1 = {1, 2, 3}
example_set2 = {'h','e','l','l','o'}

print('example_set1:', example_set1)
print('example_set2:', example_set2) # Notice there is only 1 'l'; Also notice the order of the values outputted
print('--')

singleton_set = {7}
empty_set = set() # this is because {} is reversed for a different feature in python 3.

print('Singleton:', singleton_set)
print('Empty Set:', empty_set)
```

#### Sets are mutable

Example 
```python 
# Adding and Removing Values
languages = set() # empty set initialization

programming_languages = ['C', 'C#', 'Java', 'Python', 'HTML', 'CSS', 'JavaScript', 'Haskell']

for item in programming_languages:
    languages.add(item) # .add() method adds an item to a set

print('Languages set:', languages)
print('--')

languages.discard('HTML') # looks for the target value, if found, it will remove from the set
print('HTML deleted:', languages)

languages.remove('CSS') # remove can be used to delete a value;
# only difference is it will raise an error if the target is not found
print('CSS deleted:', languages)

random_remove = languages.pop() # .pop() method deletes a random value and return the value ... not recommended
print('Randomly Removed value:', random_remove)

languages.clear() # .clear() will empty out a set : output is set()
print('Empty languages:', languages)
```
Output:
Languages set: {'HTML', 'CSS', 'JavaScript', 'Python', 'Haskell', 'Java', 'C', 'C#'}
--
HTML deleted: {'CSS', 'JavaScript', 'Python', 'Haskell', 'Java', 'C', 'C#'}
CSS deleted: {'JavaScript', 'Python', 'Haskell', 'Java', 'C', 'C#'}
Randomly Removed value: JavaScript
Empty languages: set()
