
###

#### Python as a calculator

The interpreter acts as a simple calculator: you can type an expression 
at it and it will write the value. Expression syntax is straightforward: 
the operators +, -, * and / work just like in most other languages 
(for example, Pascal or C); parentheses (()) can be used for grouping. 
For example:

``` python
>>> 2 + 2
4
>>> 50 - 5*6
20
>>> (50 - 5.0*6) / 4
5.0
>>> 8 / 5.0
1.6
```

###
The equal sign (=) is used to assign a value to a variable. Afterwards, no result is displayed before the next interactive prompt:

``` python
>>> width = 20
>>> height = 5 * 9
>>> width * height
900
```

If a variable is not “defined” (assigned a value), trying to use it will give you an error:

```
>>>
>>> n  # try to access an undefined variable
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'n' is not defined
```

###
There is full support for floating point; operators with mixed type operands convert the integer operand to floating point:

```
>>>
>>> 3 * 3.75 / 1.5
7.5
>>> 7.0 / 2
3.5
```

In interactive mode, the last printed expression is assigned to the variable _. This means that when you are using Python as a desk calculator, it is somewhat easier to continue calculations, for example:

```
>>>
>>> tax = 12.5 / 100
>>> price = 100.50
>>> price * tax
12.5625
>>> price + _
113.0625
>>> round(_, 2)
113.06
```

