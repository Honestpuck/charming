###
#### More with lists

Let's start with a list of files.

``` python
cd /Applications/Utilities
utils = !ls
``

We now have an Slist. Have a look at it.

```
utils.p
utils.n
utils.s
```

What's the problem with `utils.s`?

###
#### Fixing the spaces

We're going to use `map`

``` python
def quote(str):
    return '"' + str + '"'

new = map(quote, utils)
them = ' '.join(new)
them
```

#### List comprehension instead

List comprehensions are a neat trick

``` python
u = ['"' + i +'"' for i in utils]
u
```

#### 