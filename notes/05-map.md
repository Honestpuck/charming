#### map and list comprehensions

cd /Applications/Utilities

utils = !ls

utils.p

utils.n

utils.s

def quote(str):
    return '"' + str + '"'

new = map(quote, utils)

them = ' '.join(new)

them

u = ['"' + i +'"' for i in utils]

u

#### 