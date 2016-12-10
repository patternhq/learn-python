Python has 3 built-in number types:

* int  (short for "integer")
* float
* complex

Unless you're doing hard-core math or scientific computing, you probably won't
need `complex` numbers.  Numbers can be constructed by writing them directly:

```py
1         # an integer with the value of 1.
1.0       # a float with the value of 1.
1.0e0     # A float with the value of 1.  (scientific notation).
1.0 + 0j  # A complex number with the value of 1.
```

You can also construct numbers from strings or other numbers using the
`float` and `int` built-ins:

```py
int('1')     # an integer with the value of 1
int(1.8)     # an integer with the value of 1 (`int` always truncates toward 0).
int(-1.8)    # an integer with the value of 1 (`int` always truncates toward 0).
int('1.8')   # This is an error and won't work unlike other languages.

float('1.')  # a float with the value of 1.
float(1)     # a float with the value of 1.
```

Most of the operators in python work the way you would expect them to:

```py
1 + 1   # addition --> 2
1 - 1   # addition --> 0
10 * 2  # multiplication --> 20
10 ** 2 # exponentiation --> 100
10 / 2  # division --> 2.0  (Note the result is a float!  This is a change in behavior from python2.x)
10 % 3  # Modulo division (i.e. the "remainder") --> 1
```

For the most part, equations with all integers will produce an integer result
(Aside from division as noted above).  If there is a float anywhere in
an equation, the result will be a float.  After you work with this for a while,
it'll become second nature and you probably won't even think about it.

Unlike some languages (e.g. `C`, `Fortran`), python integers can be arbitrarily
big (`C` and `Fortran` cap out at `2**32`) and python integers are always
"signed" (they can be either positive or negative).

```py
>>> 10**72
1000000000000000000000000000000000000000000000000000000000000000000000000
```

Floats however do have a maximum value.  If you try to make a number that is
bigger than the biggest allowed float, python will give you `inf` (which is
short for "infinity").  This is known as "Overflow":

```py
>>> 1e308
1e+308
>>> 1e309
inf
```

`inf` is still a `float`, it just happens to be a very special float value.
Another special float value is `nan` ("Not A Number").  It comes up in places
where you do funky things (like subtracting `inf` from `inf`):

```py
>>> 1e309 - 1e309
nan
```


### Quiz

What is the type of the result of the following _expressions_:

1.  `1. + 2.`
2.  `1. + 2`
3.  `1 + 2`
4.  `1 + 3.`
