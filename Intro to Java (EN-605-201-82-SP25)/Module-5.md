Mod 5
# Arrays
# 5A
Motivation for using arrays
What is a Java array?
Declaring and using single dimensional arrays
multiple dimension arrays

Motivation:
Average 50 test scores - declare each variable? nah

What is an array?
  it is an object
    uses dynamic memory
  collection of elements of single type 
  number of elements (size) is specified when created
    cannot change size after created
  Individual elements accessed by position, starting at 0

Declare a single dimensional array

int [] myIntArray
type  [] = array, variable name

THIS is also acceptable
int myIntArray[];

both are ok, but top is more object oriented, 
Consistency matters most

declaring an array doesn't make it usable - memory must be allocated 
  initialization includes allocation


How to allocate: New operator

Default value for 0 is zero

Example:
int [] myIntArray = new int[5];
will allocate 5 int spaces with value of 0 initially 

myIntArray => 0 0 0 0 0 
indexes    => 0 1 2 3 4

index values always start with zero
initialized to default vale for type

Assigning values to array elements
- specify array name, index, value

- myIntArray[2] = 5;
  sets index position 2 (3rd element) value to 5

after assignment: 
0 0 5 0 0 

reading values from array elements:
  specify array name and index position
  |myInt| = |myIntArray|[2];
  variable receiving value | array name | index of element

Initializing a single-dimensional array
  allocates memory and initializes values
  int [] myIntArray = {5,10,15,20,25};

Multi-dimensional arrays?
  array inside of array
  in java each array element of a multidimensional array is an array except for last one (element)

declare 2d array:
  int[][] myIntArray2;
  type | indicates 2d array | name

  size of dimensions must be specified

EX allocate 2d
int [][] myIntArray = newInt [][]5

assigning values to 2d array elements
myIntArray2d[3] = new int[5]
this gives the 1st dimension (index) space 4 (index 3) a new array that consists of 5 non-null positions

index 
0 
1
2
3 => 0 0 0 0 0 
4

myIntArray2d[3][2] = 5;
assigns 5 t6o element
 
index
0
1
2
3 => 0 0 5 0 0
4

Reading values from 2d array:

more dimensions you have, more index to specify
to read array values: put array element specification on right side of '='
student3test5 = studentTests[3][5];
student3Age = studentAges[3];

multidimension can read array or element
int [] intArray3 = myIntArray2d[3];
  copies reference (not elements) of array


