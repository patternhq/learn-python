Boolean values can take one of two values.  They're called:

1. `True`
2. `False`

### Constructing a boolean

Booleans can be constructed using the `True` and `False` keywords<sup>1</sup>.
They can also be constructed using the `bool` builtin.  `bool` will work on
any object and it will always return either `True` or `False`.

Calling `bool` on a number will return `True` unless the number equals `0`.

```py
bool(1)    # True
bool(1.)   # True
bool(0)    # False
bool(0.0)  # False
```

Calling `bool` on a string will return `True` so long as the string is not empty.

```py
bool('Hello World')  # True
bool('')  # False
```

Obviously `bool(True)` and `bool(False)` just return `True` and `False` respectively.

The final common way to construct booleans is using comparison operators.

```py
1 > 0   # True (reads "one greater than zero?")
1 >= 1  # True (reads "one greater than or equal to zero?")
1 < 0   # False (reads "one less than zero?")
1 <= 0  # False (reads "one less than or equal to zero?")
1 == 0  # False (reads "one equal to zero?")
```

### Boolean operators

Python has 2 boolean operators.  They're called `and` and `or`.  Basic usage
with booleans is pretty intuitive.  `and` will return `True` if both operands
are `True`.  `or` will return `True` if at least one of the operands is `True`:

```py
True and True    # True
True and False   # False
False and True   # False
False and False  # False

True or True    # True
True or False   # True
False or True   # True
False or False  # False
```

The above description is correct, but it is an over-simplification.  Boolean
operators actually work even if you have non-boolean operands.  In general,
a boolean operator will call `bool` on each of the operands.  `and` will return
the first operand where `bool(operand)` is `False`.  If no operands have "falsy"
values, then the last operand is returned.  `or` will return the first operand
where `bool(operand)` is `True`.  If no operands have "truthy" values, the
last operand is returned.  (For anyone who knows Javascript, this is exactly how
`&&` and `||` work there).

```py
1 and 0   # `0` because `0` is the first falsy operand.
0 and 1   # `0` because `0` is the first falsy operand.
1 and 10  # `10` because no operands are falsy and `10` is the last operand.

1 or 0      # `1` because `1` is the first truthy operand.
0 or 1      # `1` because `1` is the first truthy operand.
0 or False  # `False` because no operands are truthy and `False` is the last operand.
```

----------
<sup><sup>1</sup>In python2.x, they were just pre-defined variables rather
than being first-class keywords.  If this doesn't mean anything to you now,
don't worry about it.  It might become more clear as we move forward in the
course.  If not, it's still not a big deal -- in practice the difference should only
matter if you're working with code where somebody did something really
shady.</sup>
