## Operators

In the tables below we will list a number of operators in the Ruby language. Try them out in `irb` as you go along. 
We assume that `a` and  `b` are variables with the following values:

```
a = 10
b = 20
```

### Arithmetic Operators

Ruby provides a number of basic operators for performing arithmetic \(the method or process of computation with figures: the most elementary branch of mathematics\). These are as follows:

| Operator | Description | Example |
| :--- | :--- | :--- |
| + | Addition - Adds values on either side of the operator |  |



| Operator | Description | Example |
| :--- | :--- | :--- |
| + | **Addition** - Adds values on either side of the operator | `a + b = 30` |
| - | **Subtraction** - Subtracts right hand operand from left hand operand | `a - b = 10` |
| _    \| _**_Multiplication_**_ - Multiplies values on either side of the operator               \| \`a _ b = 200\` |
| \/ | **Division** - Divides left hand operand by right hand operand | `a / b = 2` |
| % | **Modulus** - Divides left hand operand by right hand operand and returns remainder | `a % b = 0` |
| **       \| **Exponent** - Performs exponential \(power\) calculation on operators                \| \`a**b = 10^20\` |

This is a good time to read about Simple Arithmetic in chapter 1 of [Chris Pine's, Learn to Program book ](https://pine.fm/LearnToProgram/chap_01.html) and go through the examples and exercises there.

### Comparison Operators

Comparison operators are used to check for equality between two values. Ruby provides a number of such operators:

| Operator | Description | Example |
| :--- | :--- | :--- |
| == | Checks if the value of two operands are equal or not, if yes then condition becomes true. | `a == b` returns `false` |
| != | Checks if the value of two operands are equal or not, if values are not equal then condition becomes true. | `a != b` returns `true` |
| &gt; | Checks if the value of left operand is greater than the value of right operand, if yes then condition becomes true. | `a > b` returns `false` |
| &lt; | Checks if the value of left operand is less than the value of right operand, if yes then condition becomes true. | ´a &lt; b`returns`true\` |
| &gt;= | Checks if the value of left operand is greater than or equal to the value of right operand, if yes then condition becomes true. | `a >= b` returns `false` |
| &lt;= | Checks if the value of left operand is less than or equal to the value of right operand, if yes then condition becomes true. | `a <= b` returns `true` |
| &lt;=&gt; | **Combined comparison operator** - Returns 0 if first operand equals second, 1 if first operand is greater than the second and -1 if first operand is less than the second. | `a <=> b`returns `-1` |
| === | Used to test equality within a when clause of a case statement. | `(1...10) === 5` returns `true` |
| .eql? | `true` if the receiver and argument have both the same type and equal values \(compare to `1 == 1.0` returns `true`\). | `1.eql?(1.0)` returns `false` |
| equal? | `true` if the receiver and argument have the same object id. | see below. |

if `aObj` is a duplicate of `bObj` then:

* `aObj == bObj` returns `true`
* `a.equal?bObj` returns `false` 
* `a.equal?aObj` returns `true`

### Assignment Operators

Assignment Operators allows us to assign the result of an expression to a variable.

| Operator | Description | Example |
| :--- | :--- | :--- |
| = | Simple assignment operator, Assigns values from right side operands to left side operand | `c = a + b` will assigne value of a + b into c |
| += | Add AND assignment operator, It adds right operand to the left operand and assign the result to left operand | `c += a` is equivalent to `c = c + a` |
| -= | Subtract AND assignment operator, It subtracts right operand from the left operand and assign the result to left operand | `c -= a` is equivalent to `c = c - a` |
| _=       \| Multiply AND assignment operator, It multiplies right operand with the left operand and assign the result to left operand    \| \`c _= a`is equivalent to`c = c \* a\` |
| \/= | Divide AND assignment operator, It divides left operand with the right operand and assign the result to left operand | `c /= a` is equivalent to `c = c / a` |
| %= | Modulus AND assignment operator, It takes modulus using two operands and assign the result to left operand | `c %= a` is equivalent to `c = c % a` |
| **=      \| Exponent AND assignment operator, Performs exponential \(power\) calculation on operators and assign value to the left operand \| \`c **= a`is equivalent to`c = c \*\* a\` |

### Logical Operators

| Operator | Description | Example |
| :--- | :--- | :--- |
| && | Logical **AND** operator. If both the operands are non zero, then the condition becomes true. | \[TBD\] |
| \|\| | Logical **OR** Operator. If any of the two operands are non zero, then the condition becomes true. | \[TBD\] |
| ! | Logical **NOT** Operator. Use to reverses the logical state of its operand. If a condition is true, then Logical NOT operator will make false. | \[TBD\] |
| and | Control flow **AND** modifier | \[TBD\] |
| or | Control flow **OR** modifier | \[TBD\] |
| not | Control flow **NOT** modifier | \[TBD\] |

