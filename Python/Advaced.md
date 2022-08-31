# Generator
```python
  
# Generators help you make lazy code.
def double_numbers(iterable):
    for i in iterable:
        yield i + i

# Generators are memory-efficient because they only load the data needed to
# process the next value in the iterable. This allows them to perform
# operations on otherwise prohibitively large value ranges.
# NOTE: `range` replaces `xrange` in Python 3.
for i in double_numbers(range(1, 900000000)):  # `range` is a generator.
    print(i)
    if i >= 30:
        break

# Just as you can create a list comprehension, you can create generator
# comprehensions as well.
values = (-x for x in [1,2,3,4,5])
for x in values:
    print(x)  # prints -1 -2 -3 -4 -5 to console/terminal

# You can also cast a generator comprehension directly to a list.
values = (-x for x in [1,2,3,4,5])
gen_to_list = list(values)
print(gen_to_list)  # => [-1, -2, -3, -4, -5]

```

# Yeild
To understand what `yield` does, you must understand what _generators_ are. And before you can understand generators, you must understand _iterables_.

## Iterables

When you create a list, you can read its items one by one. Reading its items one by one is called iteration:

```python
>>> mylist = [1, 2, 3]
>>> for i in mylist:
...    print(i)
1
2
3
```

`mylist` is an _iterable_. When you use a list comprehension, you create a list, and so an iterable:

```python
>>> mylist = [x*x for x in range(3)]
>>> for i in mylist:
...    print(i)
0
1
4
```

Everything you can use "`for... in...`" on is an iterable; `lists`, `strings`, files...

These iterables are handy because you can read them as much as you wish, but you store all the values in memory and this is not always what you want when you have a lot of values.

## Generators

Generators are iterators, a kind of iterable **you can only iterate over once**. Generators do not store all the values in memory, **they generate the values on the fly**:

```python
>>> mygenerator = (x*x for x in range(3))
>>> for i in mygenerator:
...    print(i)
0
1
4
```

It is just the same except you used `()` instead of `[]`. BUT, you **cannot** perform `for i in mygenerator` a second time since generators can only be used once: they calculate 0, then forget about it and calculate 1, and end calculating 4, one by one.

## Yield

`yield` is a keyword that is used like `return`, except the function will return a generator.

```python
>>> def create_generator():
...    mylist = range(3)
...    for i in mylist:
...        yield i*i
...
>>> mygenerator = create_generator() # create a generator
>>> print(mygenerator) # mygenerator is an object!
<generator object create_generator at 0xb7555c34>
>>> for i in mygenerator:
...     print(i)
0
1
4
```

Here it's a useless example, but it's handy when you know your function will return a huge set of values that you will only need to read once.

To master `yield`, you must understand that **when you call the function, the code you have written in the function body does not run.** The function only returns the generator object, this is a bit tricky.

Then, your code will continue from where it left off each time `for` uses the generator.



# Decorators
```python
# Decorators
# In this example `beg` wraps `say`. If say_please is True then it
# will change the returned message.
from functools import wraps

def beg(target_function):
    @wraps(target_function)
    def wrapper(*args, **kwargs):
        msg, say_please = target_function(*args, **kwargs)
        if say_please:
            return "{} {}".format(msg, "Please! I am poor :(")
        return msg

    return wrapper

@beg
def say(say_please=False):
    msg = "Can you buy me a beer?"
    return msg, say_please

print(say())                 # Can you buy me a beer?
print(say(say_please=True))  # Can you buy me a beer? Please! I am poor :(

```