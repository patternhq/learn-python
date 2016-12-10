Now that we've talked about booleans, we're in position to start adding
logic to our scripts.  In particular, python has the ability to execute
code based on "conditions".  This is accomplished via an `if` "block".  The
basic syntax is:

```py
if expression:
    <code to execute if bool(expression) is True>
elif expression:
    <code to execute if bool(expression) is True>
else:
    <code to execute if none of the conditions were True>
```

You can have an arbitrary number of `elif` statements (or none at all).  You
can also leave off the `else` statement.

The indentation is important.  In general, any "block" in python requires the
code inside it to be indented (the code inside a block is called a "suite").
The indentation must be consistent and convention is to use 4 spaces for
indenting a suite.

The logic is pretty simple -- Python will read the `if` block from top to bottom.
It will evaluate the expression that is associated with the `if` first.
If that expression has a "truthy" result, then the suite directly below the `if`
will be executed and then the rest of the block will be skipped.  Otherwise, the
same process will be repeated for each of the `elif` statements in order.  If
none of the expressions provided in `if` and `elif` were "truthy", then the
`else` suite will execute (if present).

Each of the following code snippets will print `'See this'` exactly once.

```py
if True:
    print('See this')
```

```py
if 1:  # Python calls `bool` on `1` for us!
    print('See this')
```

```py
if True:
    print('See this')
else:
    print('Do not see this')
```

```py
if False:
    print('Do not see this')
elif True:
    print('See this')
```

```py
if False:
    print('Do not see this')
elif True:
    print('See this')
elif True:
    print('See this')  # Just kidding!
```

```py
if False:
    print('Do not see this')
elif False:
    print('Do not see this')
else:
    print('See this')
```

```py
if False:
    print('Do not see this')
elif False:
    print('Do not see this')
elif True:
    print('See this')
```

Awesome, now we can look at our [first program](buggy_if.py) that has some logic.
We haven't talked about the `input` function, but it just gets input from the
in the terminal as a string.  We also haven't talked about how equality for
strings works, but it should be straight forward to figure out.  The "bug" will
show up if you try to input `15` as a floating number (e.g. if you type `15.0`)

> python buggy_if.py
> Give me a number! 15.0
> Nice try.  Next time, give me 15

Can you fix this bug?
