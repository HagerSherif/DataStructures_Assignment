# POSSIBLE USAGES OF `const` KEYWORD
1.When object declared as `const`, programmer cannot modify it after declaration , if programmer tries to do so there will be a `compile_time error`. Therefore it needs to be initialized at time of declaration by constructor.


**Syntax**: 
```C++
const Class_Name Object_name;
```

2.When function declared as `const` it is not allowed to modify the object on which they are called whether they are constant or not. 
 The `const` keyword is required in both the declaration and the definition of the function.
 constant object can only call constant functions.
 `const` can be used in function parameters and return type as well

**Example**:
```C++
int getValue() const
    {
        return value;
    }
 ```





3.When a pointer is declared `const` , there are **three** ways to do it, each with different meaning.

**First syntax**:
```C++
const data_type* var_name;
```
**we cannot modify values stored in location through the pointer itself.**

example 1 _(gives Error)_:
```C++
int main()
{
int x{ 10 };
char y{ 'M' };

int z{ 13 };
char f{ 'R' };


const int* i = &x;
const char* j = &y;
     *i= 9;
    *j= 'A';
}
```
**But we can modify the locations that are pointed out by the pointer variables.**: (_gives no error_)

```C++
    i = &z;
    j = &f;
```



**Second syntax:**
```C++
data_type* const var_name;
```
**we cannot modify the locations that are pointed out by const-pointer variables**

example 2 _(gives error)_:

```C++
int main()
{
int x{ 10 };
char y{ 'M' };

int z{ 13 };
char f{ 'R' };


int* const i = &x;
char* const j = &y;
     i= &z;
    j= &f;
}
```

**But we can modify values stored in location through the pointer itself**:(_gives no error_)


```C++
    *i = 9;
    *j = 'A';
```


**Third Syntax:**

```C++
const data_type* const var_name;
```

**Here we cannot modify values stored in location through the pointer nor the locations that are pointed out by const-pointer variables**

# POSSIBLE USAGES OF `&` OPERATOR
1.The `&` (bitwise AND) C++ takes two numbers as operands and does AND on every bit of two numbers. The result of AND is 1 only if both bits are 1. 

**Example:**
```C++
int main() {
      // a = (00000111), b = (00001001)
    int a = 7, b = 9;
  
    // The result is 00000001
    cout<<"a = " << a <<","<< " b = " << b <<endl;
    cout << "a & b = " << (a & b) << endl;
}
```

**Output:**

`a = 7, b = 9`
`a&b = 1 `




2.In the following example, by putting `&` in the declaration before the variable `ref` it is declared as a reference for variable `x` which is similar to pointers but once a reference is assigned to a value this value cannot be updated. 
```C++
int main()
{
  int x = 10;
  
  // ref is a reference to x.
  int& ref = x;
  
  // Value of x is now changed to 20
  ref = 20;
  cout << "x = " << x << endl ;
  
  // Value of x is now changed to 30
  x = 30;
  cout << "ref = " << ref << endl ;
  
  return 0;
}
```


 
**Output:**

` x = 20`
`ref = 30`

(Here, when reassigning the reference it is the same like reassigning the value of x and vice versa.)



**some applications of references:**

1- Avoiding copying of large structures in loops and instead taking reference.

2 - modifying the actual parameters passed to a function.
