---
id: 14_keywords
title: Keywords
sidebar_label: Keywords
---

### print

To print a variable or a value to `stdout` simply use `print` keyword:

```
### print 77
77
### print "hello world"
hello world
### print 'hello world'
hello world
### str hello = "world"
### print hello
world
```

### del

`del` keyword deallocates the memory region that previously allocated for the given variable:

```
del var2
```

### exit

`exit` keyword terminates the program:

```
### exit
You have chosen the order!
```

### quit

`quit` alias of `exit`:

```
### quit
You have chosen the order!
```

### symbol_table

`symbol_table` command shows all of the variables currently being tracked by Symbol Table.
This keyword is only useful for the developers of language's itself:

```
[start] =>
	{name: (null), 2nd_name: param1, key: (null), scope: N/A, type: 0, 2nd_type: 0, value_type: 4, role: 1, param_of: f1} =>
	{name: (null), 2nd_name: param2, key: (null), scope: N/A, type: 1, 2nd_type: 0, value_type: 4, role: 1, param_of: f1} =>
	{name: (null), 2nd_name: param3, key: (null), scope: N/A, type: 2, 2nd_type: 0, value_type: 4, role: 1, param_of: f1} =>
	{name: hello, 2nd_name: (null), key: (null), scope: main, type: 2, 2nd_type: 0, value_type: 3, role: 0, param_of: } =>
	{name: pi, 2nd_name: (null), key: (null), scope: main, type: 1, 2nd_type: 0, value_type: 2, role: 0, param_of: } =>
[end]
```

### function_table

`function_table` command shows all of the functions currently parsed and stored in Function Table.
This keyword is only useful for the developers of language's itself:

```
[start] =>
	{name: a, type: 6, parameter_count: 0, decision_length: 0, context: tests/function.kaos, module: } =>
	{name: b, type: 6, parameter_count: 0, decision_length: 0, context: tests/function.kaos, module: } =>
	{name: f1, type: 6, parameter_count: 3, decision_length: 0, context: tests/function.kaos, module: } =>
	{name: f2, type: 4, parameter_count: 2, decision_length: 0, context: tests/function.kaos, module: } =>
	{name: f3, type: 5, parameter_count: 2, decision_length: 0, context: tests/function.kaos, module: } =>
	{name: add, type: 1, parameter_count: 2, decision_length: 0, context: tests/function.kaos, module: } =>
	{name: loopInside, type: 6, parameter_count: 0, decision_length: 0, context: tests/function.kaos, module: } =>
[end]
```