#https://github.com/Pri1076/Python-Notebook/blob/master/Project.md

# Python

    -Top 5 Python IDEs For Data Science
    -Basic Data Types
        -Bool
        -Numbers
        -List
        -String
        -Dictionaries
        -Sets
        -Tuples
    -Function
    -Class
    
    -Overview about some important libraries in Python
    -Numpy
        -Arrays
        -Array Math
        -Broadcasting
    -Scipy
    -Requests
    -BeautifulSoup
    -wxPython 
        
    
    
    
**Python**
<br>Python is a cross-platform programming language, meaning, it runs on multiple platforms like Windows, Mac OS X, Linux, Unix and has even been ported to the Java and .NET virtual machines. It is free and open source.</br>



```python
eip=10
if (eip/2==0):
    print("This is Even Number")
else:
    print("This is Odd Number")
```

    This is Odd Number
    

**Top 5 Python IDEs For Data Science**

The best Python IDEs for data science that make data analysis and machine learning easier!

1.Spyder<br>
2.PyCharm<br>
3.Rodeo<br>
4.Atom<br>
5.Jupyter Notebook<br>

**Basic Datatypes in Python**

There are eight kinds of types supported by Python:

**1.Bool-**

Boolean values are the two constant objects False and True. They are used to represent truth values (other values can also be considered false or true). In numeric contexts (for example, when used as the argument to an
arithmetic operator), they behave like the integers 0 and 1, respectively.The built-in function <b>bool()</b> can be used to cast any value to a Boolean,if the value can be interpreted as a truth value




```python
#If the given number available in the list 
eip_in=[2,3,4,5,6]
eip_out=6
eip=[]
for eip in eip_in:
    if eip==eip_out:
       print(True)
    else:
       print(False)
        
```

    False
    False
    False
    False
    True
    

**2.Number**

**2.1 int-** 

It comes from the word integer and means a whole number.For example::



```python
eip=5
print(eip)
type(eip)
```

    5
    




    int



**2.2 Float-** 

It means a number with a decimal part such as 1.5, and some others.For example:



```python
mlblr=2.5
print(mlblr)
type(mlblr)
```

    2.5
    




    float



**2.3 Complex-**

For Example:


```python
eip= 1+2j
print(eip)
type(eip)

```

    (1+2j)
    




    complex



**3. List**

List is an ordered sequence of items. It is one of the most used datatype in Python and is very flexible. All the items in a list do not need to be of the same type.


```python
mlblr=[2,3,4,9]
print(mlblr)
type(mlblr)
```

    [2, 3, 4, 9]
    




    list



**4.String**

String is sequence of Unicode characters. We can use single quotes or double quotes to represent strings. Multi-line strings can be denoted using triple quotes, ''' or """.


```python
eip_in="You are most welcome"
print(eip_in)
type(eip_in)
```

    You are most welcome
    




    str



**5.Dictionaries**

A dictionary in Python is a collection of unordered values accessed by key rather than by index. The keys have to be hashable: integers, floating point numbers, strings, tuples, and frozensets are hashable, while lists, dictionaries, and sets other than frozensets are not.

For Example:


```python
eip_dict={"A":123,"B":4563}
print(eip_dict)
type(eip_dict)
```

    {'A': 123, 'B': 4563}
    




    dict



**6.Sets**

Python also includes a data type for sets. A set is an unordered collection with no duplicate elements. Basic uses include membership testing and eliminating duplicate entries. Set objects also support mathematical operations like union, intersection, difference, and symmetric difference.

For Example:


```python
#Example 1
eip={"Apple","Orange","Banana"}
print(eip)
type(eip)

```

    {'Banana', 'Orange', 'Apple'}
    




    set




```python
#Example 2-We have a duplicate enter in Set variable but it will print only unique value.
eip={"Apple","Orange","Banana","Apple"}
print(eip)
```

    {'Orange', 'Banana', 'Apple'}
    

**7 Tuple**

A tuple is a sequence of immutable Python objects. Tuples are sequences, just like lists. The differences between tuples and lists are, the tuples cannot be changed unlike lists and tuples use parentheses, whereas lists use square brackets. Creating a tuple is as simple as putting different comma-separated values.

For Example:


```python
mlblr= 124,34526,"Ya"
print(mlblr)
print(mlblr[2])
type(mlblr)
```

    (124, 34526, 'Ya')
    Ya
    




    tuple



**Function**

Functions are used to utilize code in more than one place in a program. The only way without functions to reuse code consists in copying the code. A function in Python is defined by a def statement.We define function with def in python.

For Example:


```python
def eip(x,y):
    if (x>0 and y>0):
        mlblr=x+y
        print(mlblr)
    else:
        print("Please Enter positive number")

eip(12,98)

```

    110
    


```python
eip(-5,12)
```

    Please Enter positive number
    

**Class**

Python is an “object-oriented programming language.” This means that almost all the code is implemented using a special construct called classes. Programmers use classes to keep related things together. This is done using the keyword “class,” which is a grouping of object-oriented constructs.

For Example:


```python
class eip_in:
  Name="Pooja"
  Age= 25
  Education="12th"

print(eip_in.Name)
print(eip_in.Age)
print(eip_in.Education)
```

    Pooja
    25
    12th
    

**Numpy**


```python
1. Numpy--array

<br>NumPy’s main object is the homogeneous multidimensional array. It is a table of elements (usually numbers), all of the same type, indexed by a tuple of positive integers. In NumPy dimensions are called axes.

NumPy’s array class is called ndarray. It is also known by the alias array. Note that numpy.array is not the same as the Standard Python Library class array.array, which only handles one-dimensional arrays and offers less functionality. The more important attributes of an ndarray object are:</br>

ndarray.ndim -The number of axes (dimensions) of the array.<br>

ndarray.shape -The dimensions of the array. This is a tuple of integers indicating the size of the array in each dimension. For a matrix with n rows and m columns, shape will be (n,m). The length of the shape tuple is therefore the number of axes, ndim.<br>

ndarray.size -The total number of elements of the array. This is equal to the product of the elements of shape.<br>

ndarray.dtype -An object describing the type of the elements in the array. One can create or specify dtype’s using standard Python types. Additionally NumPy provides types of its own. numpy.int32, numpy.int16, and numpy.float64 are some examples.<br>

ndarray.itemsize -The size in bytes of each element of the array. For example, an array of elements of type float64 has itemsize 8 (=64/8), while one of type complex32 has itemsize 4 (=32/8). It is equivalent to ndarray.dtype.itemsize.<br>

ndarray.data -The buffer containing the actual elements of the array. Normally, we won’t need to use this attribute because we will access the elements in an array using indexing facilities.<br>
```


```python
import numpy
mlblr = numpy.arange(15).reshape(3, 5)
mlblr
```




    array([[ 0,  1,  2,  3,  4],
           [ 5,  6,  7,  8,  9],
           [10, 11, 12, 13, 14]])




```python
mlblr.shape
```




    (3, 5)




```python
mlblr.size
```




    15




```python
mlblr.itemsize
```




    4



2. Numpy-- Data type


```python
import numpy as np
eip = np.array([1, 2, 3, 4])
eip+1

```




    array([2, 3, 4, 5])




```python
mlblr = np.ones(4) + 1
mlblr
```




    array([2., 2., 2., 2.])




```python
import numpy as np
eip = np.ones((3, 3))
eip*eip
```




    array([[1., 1., 1.],
           [1., 1., 1.],
           [1., 1., 1.]])




```python
eip = np.array([1, 2, 3, 4])
mlblr = np.array([4, 2, 2, 4])
eip==mlblr
```




    array([False,  True, False,  True])




```python
import numpy as np
eip = np.array([1, 3, 2])
eip.min()
```




    1




```python
eip.max()
```




    3



3. Numpy- Broadcasting

<br>The term broadcasting describes how numpy treats arrays with different shapes during arithmetic operations. Subject 
to certain constraints, the smaller array is “broadcast” across the larger array so that they have compatible shapes.</br>


```python
import numpy as np
eip = np.array([1.0, 2.0, 3.0])
mlblr = 2
eip*mlblr
```




    array([2., 4., 6.])




```python
eip/mlblr
```




    array([0.5, 1. , 1.5])



**SciPy**

<br>The SciPy library is one of the core packages that make up the SciPy stack. It provides many user-friendly and efficient numerical routines such as routines for numerical integration and optimization.</br>


**Requests**

Requests is an elegant and simple HTTP library for Python, built for human beings.


```python
import requests

epi = requests.get("https://www.epicurious.com/search/tofu%20chili")
epi.status_code
```




    200




```python
epi.encoding
```




    'utf-8'



**BeautifulSoup**

<br>Beautiful Soup is a Python library for pulling data out of HTML and XML files. It works with your favorite parser to provide idiomatic ways of navigating, searching, and modifying the parse tree. It commonly saves programmers hours or days of work.</br>


```python
from bs4 import BeautifulSoup
Keyword="Paneer"
def get_recipes(Keyword):
        recipe_list=list()
        url="https://www.epicurious.com/search/" + Keyword
        response=requests.get(url)
        result_page=BeautifulSoup(response.content,'lxml')

```

**wxpython**

<br>wxPython is a cross-platform GUI toolkit for the Python programming language. It allows Python programmers to create programs with a robust, highly functional graphical user interface, simply and easily. It is implemented as a set of Python extension modules that wrap the GUI components of the popular wxWidgets cross platform library, which is written in C++.</br>


```python
import wx
app = wx.App()
frm = wx.Frame(None, title="Hello World")
frm.Show()
app.MainLoop()
```
