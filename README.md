# Treeart

Treeart lets you draw ASCII trees easily. These can contain nodes that span multiple lines, they will be correctly combined.

## Examples

```
>>> from treeart import *
>>> print(binary_edge(1, 2, 3))
╭─1─╮
2   3

>>> print(binary_edge(1, 2, binary_edge(3, 4, 5)))
╭──1──╮
2   ╭─3─╮
    4   5

>>> x, y = 'x', 'y'
for i in range(5):
    x, y = binary_edge(i, x, y), x
print(x)
                  ╭───────────4───────────╮
          ╭───────3──────╮           ╭────2───╮  
     ╭────2───╮       ╭──1──╮     ╭──1──╮   ╭─0─╮
  ╭──1──╮   ╭─0─╮   ╭─0─╮   x   ╭─0─╮   x   x   y
╭─0─╮   x   x   y   x   y       x   y            
x   y

>>> print(binary_edge('aa\nbb', 'c', 'eee\nfff'))
  aa
╭─bb─╮
c   eee
    fff
```



## Customization

You can specify three kinds of edges, which use more or less space, and might work better for different applications:

```
>>> print(binary_edge(111, 222, 333, align='upper'))
 ╭─111─╮
222   333

>>> print(binary_edge(111, 222, 333, align='center'))
   111
 ╭──┴──╮
222   333

>>> print(binary_edge(111, 222, 333, align='lower'))
   111
222─┴─333
```

You can also specify a gap on either side of the abutting edges:

```
>>> print(binary_edge(111, 222, 333, align='upper', gap=True))
 ╭─ 111 ─╮
222     333
```

