# 3A - Java Relational and Logical Operators
- is something true, false? on or off?
- 2 main topics:
    java relational operators
    Java logical operators

## Java Relational Operators
Determine relation of one operand to another
Result is Boolean value (true/false)

- Equal to (==)
    Value of 2 operands are the same
    Ex numMonthsYear == 12
    Not same as (=) - that is assignment!
    Caution with float-point values:
        floating points can produce round-off errors
        Result may not be exactly what is expected
- Not equal to (!=)
    Inverse of equal (==)
    Same floating point caution as w/ equal
- Greater than (>)
- Less than (<)
- Greater than or equal (>=)
- Less than or equal (<=)

Boolean Logical Operators
- Compares two boolean operands (except NOT)
    Produce true/false result
    Some combine w/ assignment operation
- Operate on Boolean objects
- Used in comparison operations
- Bit-wise syntax used
    context important
    comparison logical vs arithmetic logical



## List
### Operator        Result
    &               Logical AND
    |               Logical OR
    ^               Logical Exclusive OR (XOR)
    ||              Logical OR (short-circuit)
    &&              Logical AND (short-circuit)
    !               Logical NOT
    &=              Logical AND with assignment
    |=              Logical OR with assignment
    ^=              Logical XOR with assignment
    ==              Equal to
    !=              Not equal to
    ?:              Ternary


##  Logical AND (&)
##  A       B       Result
    True    True    True
    True    False   False
    False   True    False
    False   False   False
--  Both operands must be TRUE for TRUE result

## Logical OR (|)
