###
#### Talking To JSS

First we get our JSS object

```
import jss
jss_prefs = jss.JSSPrefs()
j = jss.JSS(jss_prefs)
```

Get the computer list

```
j.Computer()
```

Notice that python-jss pretty prints the list. Note also
that it doesn't retrieve all the information, just the name
and id.

###

Put the result in a variable and
format it yourself.

```
computers = j.Computer()
for i in computers:
    print "id:"+str(i.id)+" name:"+i.name
```

Now get the record of one computer. Rhis will get **all** the record.

```
example = j.Computer(193)
example
```

###

We can view that with `less` using the `page` magic.

```
page example
```

Some information is easily retrieved

```
example.serial_number
example.mac_addresses
```

Other information requires some XML work. XML is a tree of nodes and
we have to work with those nodes.
 
###
Let's get a list of installed applications. `findall()` will return a list
of nodes that match our search string. `find()` returns a single child node that
matches.

```
x = example.findall('.//application')
for i in x:
    nm = i.find('name')
    ver = i.find('version')
    path = i.find('path')
    print nm.text, ver.text, path.text
```

Rather than print it let's gather the info.

```
o = []
for i in x:
    nm = i.find('name')
    ver = i.find('version')
    path = i.find('path')
    o.append(' '.join([nm.text, ver.text, path.text]))
o
```

### Further examples

```
model = comp.findall('.//hardware/model_identifier')
model[0].text
os = comp.findall('.//os_version')
os[0].text
```

all_computers = j.Computer().retrieve_all()








