###

#### Starting IPython
* `ipython` - run IPython.
* `ipython qtconsole` - runs ipython in QT window.
* `ipython qtconsole --matplotlib=inline` - runs ipython in QT window with inline plotting
* `ipython notebook` - runs the IPython notebook server
* `ipython --help | less` - IPython man page
* `ipython --help-all | less` - IPython man page with *all* command line options.

#### The four most helpful commands

The four most helpful commands, as well as their brief description, is shown to you in a banner, every time you start IPython:

| command	| description                                               |
|:----------|:----------------------------------------------------------| 
| ?	        | Introduction and overview of IPython’s features.          |
| %quickref	| Quick reference.                                          |
| help	    | Python’s own help system.                                 |
| object?	| Details about ‘object’, use ‘object??’ for extra details. |

###
#### Tab completion
Tab completion, especially for attributes, is a convenient way to explore the structure of any object you’re dealing with. Simply type `object_name.<TAB>` to view the object’s attributes. Besides Python objects and keywords, tab completion also works on file and directory names.

#### Exploring your objects
Typing `object_name?` will print all sorts of details about any object, including docstrings, function definition lines (for call arguments) and constructor details for classes. To get specific information on an object, you can use the magic commands %pdoc, %pdef, %psource and %pfile

###
#### Magic functions
IPython has a set of predefined ‘magic functions’ that you can call with a command line style syntax. There are two kinds of magics, line-oriented and cell-oriented. Line magics are prefixed with the % character and work much like OS command-line calls: they get as an argument the rest of the line, where arguments are passed without parentheses or quotes. Cell magics are prefixed with a double %%, and they are functions that get as an argument not only the rest of the line, but also the lines below it in a separate argument.

The following examples show how to call the builtin %timeit magic, both in line and cell mode:
```
In [1]: %timeit range(1000)
100000 loops, best of 3: 7.76 us per loop

In [2]: %%timeit x = range(10000)
   ...: max(x)
   ...:
1000 loops, best of 3: 223 us per loop
```

###
**The builtin magics include:**

 * **Functions that work with code:** %run, %edit, %save, %macro, %recall, etc.
 * **Functions which affect the shell:** %colors, %xmode, %autoindent, %automagic, etc.
 * **Other functions such as** %reset, %timeit, %%writefile, %load, or %paste.

You can always call them using the % prefix, and if you’re calling a line magic on a line by itself, you can omit even that:
```
run thescript.py
```
You can toggle this behavior by running the %automagic magic. Cell magics must always have the %% prefix.

A more detailed explanation of the magic system can be obtained by calling %magic, and for more details on any magic function, call %somemagic? to read its docstring. To see all the available magic functions, call %lsmagic.

###
#### History
IPython stores both the commands you enter, and the results it produces. You can easily go through previous commands with the up- and down-arrow keys, or access your history in more sophisticated ways.

Input and output history are kept in variables called In and Out, keyed by the prompt numbers, e.g. In[4]. The last three objects in output history are also kept in variables named _, __ and ___.

You can use the %history magic function to examine past input and output. Input history from previous sessions is saved in a database, and IPython can be configured to save output history.

Several other magic functions can use your input history, including %edit, %rerun, %recall, %macro, %save and %pastebin. You can use a standard format to refer to lines:

```
%pastebin 3 18-20 ~1/1-5
```
This will take line 3 and lines 18 to 20 from the current session, and lines 1-5 from the previous session.

###
#### Explore The Magic Functions

##### %bookmark

`bookmark` is a directory bookmarking system.

| command               | description                 |
|:----------------------|:----------------------------|
| bookmark <name>       | set bookmark to current dir |
| bookmark <name> <dir> | set bookmark to <dir>       |
| bookmark -l           | list all bookmarks          |
| bookmark -d <name>    | remove bookmark             |
| bookmark -r           | remove all bookmarks        |

Then `cd -b <name>` or just `cd <name>` if there is no directory called <name> AND
there is such a bookmark defined. (The latter is why I usually use two or three letter
bookmark names.)

##### %cd

The `cd` magic is necessary (and nicely enhanced) as the system `cd` won't work. It keeps a history
of the directories visited.

| command      | description                                        |
|:-------------|:---------------------------------------------------|
| cd           | changes to ~                                       |
| cd 'dir'     | changes to directory 'dir'                         |
| cd -         | changes to previous directory                      |
| cd -<n>      | changes to directory <n> in directory history      |
| cd --foo     | changes to directory that matches 'foo' in history | 
| cd -b <name> | jump to bookmark <name>                            |

%dhist prints the directory history and %dhist <n> prints the last <n> entries.
    
##### The directory stack

As well as a history of directories IPython also has a directory stack.

| command      | description                                      |
|:-------------|:-------------------------------------------------|
| dirs         | list directory stack                             |
| pushd        | push the current directory onto the stack        |
| pushd <dir>  | push the current directory and cd to <dir>       |
| popd         | pop the top directory off the stack and cd to it |

##### %edit

`edit` opens things in the editor you have defined in your $EDITOR environment
variable. 
