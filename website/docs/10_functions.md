---
id: 10_functions
title: Functions
sidebar_label: Functions
---

The keyword for declaring functions is: `def`:

```chaos
kaos> void def hello_world()
....      print "hello world"
....  end
kaos> hello_world()
hello world
```

## Declaration Order

There is no need for forward declaration because the Chaos language looks ahead:

```chaos
void def a()
    print "inside function a"
    num val1 = 5
    print val1
end

print "first print this"

a()
b()

void def b()
    print "inside function b"
    num val2 = 8
    print val2
end
```

Gives you this output:

```text
first print this
inside function a
5
inside function b
8
```

## Type Safety

All of the functions in Chaos Language are forced to have one of these keywords to
determine the return type: `bool`, `num`, `str`, `list`, `dict`.

If you try to return an incorrect data type from a function an error will be thrown:

```chaos
kaos> str def errorTest()
....      num a = 32
....      return a
....  end
kaos> errorTest()
  Chaos Error:
    Module: /home/mertyildiran/Documents/chaos/__interactive__.kaos
    Line: 4
    Illegal variable type: Number for function: errorTest
    Absorbed by Interactive Shell
```

You can even return a typed list:

```chaos
kaos> str list def typedList()
....      str list a = ['foo', 'bar', 'baz']
....      return a
....  end
kaos> str list b = typedList()
kaos> b
['foo', 'bar', 'baz']
```

or a typed dictionary:

```chaos
kaos> num dict def typedDict()
....      num dict a = {'a': 1, 'b': 2, 'c': 3}
....      return a
....  end
kaos> num dict b = typedDict()
kaos> b
{'a': 1, 'b': 2, 'c': 3}
```

## Immutability

The parameters supplied to a function in Chaos will be deep cloned.  Changing a
parameter's value inside a function never updates the original variable:

```chaos
kaos> str hello = 'hello world'
kaos> str def f1(str param1)
....      param1 = 'hello my friend'
....      return param1
....  end
kaos> str hello_new = f1(hello)
kaos> print hello_new
hello my friend
kaos> print hello
hello world
```

## Optional Parameters

Chaos language also supports optional function parameters:

```chaos
kaos> void def f2(str param1, str param2 = 'bar')
....      print param1
....      print param2
....  end
kaos> f2('foo')
foo
bar
kaos> f2('foo', 'baz')
foo
baz
```

## Example Functions

### Print a Dictionary with a Title

```chaos
kaos> dict d = {'a': 'foo', 'b': 'bar', 'c': 'baz'}
kaos> dict def f3(str param1, dict param2)
....      print param1
....      return param2
....  end
kaos> print f3('Dictionary:', d)
Dictionary:
{'a': 'foo', 'b': 'bar', 'c': 'baz'}
```

### Add Two Numbers Together

```chaos
kaos> num def add(num x, num y)
....      num result = x + y
....      return result
....  end
kaos> num z = 3
kaos> z = add(z, 5)
kaos> print z
8
```
