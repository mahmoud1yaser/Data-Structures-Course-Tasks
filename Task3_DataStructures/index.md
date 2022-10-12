# The "const" keyword and ampersand uses
## The “const” word uses in programming
The various functions of the const keyword which is found in C++ are discussed. Whenever const keyword is attached with `any method()`, `variable`, `pointer variable`, and with `the object of a class`. __It prevents that specific object/method()/variable to modify its data items value.__
From the contents that we will talk about are
- Constant Variables
- Const Keyword With Pointer Variables
    - Const pointer variable point to the value
    - Const pointer pointing to a const variable
    - The pointer variable point to a const value

### Constant Variables
- General rules of declaration
    - The const variable cannot be left un-initialized at the time of the assignment
    - It cannot be assigned value anywhere in the program
    - Explicit value needed to be provided to the constant variable at the time of declaration of the constant variable

> Code (Input)

```
// C++ program to demonstrate the
// the above concept
#include <iostream>
using namespace std;

// Driver Code
int main()
{

    // const int x;  CTE error
    // x = 9;   CTE error
    const int y = 10;
    cout << y;

    return 0;
}
```

> Output

```
10
```
 Explanation:
The error faced for faulty declaration: If you try to initialize the const variable without assigning an explicit value then a compile-time error (CTE) is generated.

### The pointer variable point to a const value

> Syntax:

```
const data_type* var_name;
```

> Code (Input)

```
// C++ program to demonstrate the
// above concept
#include <iostream>
using namespace std;
// Driver Code
int main()
{
    int x{ 10 };
    char y{ 'M' };

    const int* i = &x;
    const char* j = &y;

    // Value of x and y can be altered,
    // they are not constant variables
    x = 9;
    y = 'A';

    // Change of constant values because,
    // i and j are pointing to const-int
    // & const-char type value
    // *i = 6;
    // *j = 7;

    cout << *i << " " << *j;
}
```

> Output

```
9 A
```
Explanation:
Here in the above case, i and j are two pointer variables that are pointing to a memory location const int-type and char-type, but the value stored at these corresponding locations can be changed as we have done above.
Otherwise, the following error will appear: If we try to modify the value of the const variable.

### Const pointer variable point to the value

> Syntax:

```
data_type* const var_name;
```

> Code (Input)

```
// C++ program to demonstrate the
// above concept
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // x and z non-const var
    int x = 5;
    int z = 6;

    // y and p non-const var
    char y = 'A';
    char p = 'C';

    // const pointer(i) pointing
    // to the var x's location
    int* const i = &x;

    // const pointer(j) pointing
    // to the var y's location
    char* const j = &y;


    // The values that is stored at the memory location can modified
    // even if we modify it through the pointer itself
    // No CTE error
    *i = 10;
    *j = 'D';

    // CTE because pointer variable
    // is const type so the address
    // pointed by the pointer variables
    // can't be changed
    // *i = &z;
    // *j = &p;

    cout << *i << " and " << *j
        << endl;
    cout << i << " and " << j;

    return 0;
}
```

> Output

```
9 and M
0x7ffd1ff8f830 and MC
```
Explanation:
The values that are stored in the corresponding pointer variable i and j are modifiable, but the locations that are pointed out by const-pointer variables where the corresponding values of x and y are stored aren’t modifiable.
Otherwise, the following error will appear: The pointer variables are const and pointing to the locations where the x and y are stored if we try to change the address location then we’ll face the error.

### Const pointer pointing to a const variable

> Syntax:

```
const data_type* const var_name;
```

> Code (Input)

```
// C++ program to demonstrate
// the above concept
#include <iostream>
using namespace std;
// Driver code
int main()
{
    int x{ 9 };

    const int* const i = &x;

    // *i=10;
    // The above statement will give CTE
    // Once Ptr(*i) value is
    // assigned, later it can't
    // be modified(Error)

    char y{ 'A' };

    const char* const j = &y;

    // *j='B';
    // The above statement will give CTE
    // Once Ptr(*j) value is
    // assigned, later it can't
    // be modified(Error)

    cout << *i << " and " << *j;

    return 0;
}
```

> Output

```
9 and A
```
Explanation:
Here, the const pointer variable points to the const variable. So, you are neither allowed to change the const pointer variable(*P) nor the value stored at the location pointed by that pointer variable(*P).
Otherwise, the following error will appear: Here both pointer variable and the locations pointed by the pointer variable are const so if any of them is modified.

## The ampersand (&) uses in programming
-  **The ampersand is used as a code to precede an underlined character.**
    1.  *A double ampersand* is used **to represent the Boolean AND operator**`(x >= 50 && x <= 100)`.
    2.  *Single ampersand* is used **to represent the address operator**`var1 = var2;`
        - This code places the contents of VAR2 into VAR1. However, an ampersand in front of the variable name (var1 = &var;) places the address of VAR2, not the data, into VAR1.
