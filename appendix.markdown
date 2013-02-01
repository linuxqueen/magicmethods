##<a id="appendix1" href="#appendix1">附录A：如何调用Magic Methods</a>##

Python的magic method有些是直接映射成内置函数，这些方法的调用方式很容易明白。不过，其他方法的调用方式就不那么容易直接了。本附录将着重介绍这些调用的语法。

Magic Method                       |  何时被调用（例子）                    | 说明
----------------------             | ----------------------------------     | --------------------------------------------
`__new__(cls [,...])`              |  `instance = MyClass(arg1, arg2)`      |  实例创建时`__new__`被调用
`__init__(self [,...])`            |  `instance = MyClass(arg1, arg2)`      |  实例创建时`__init__`被调用
`__cmp__(self, other)`             |  `self == other`, `self > other`, 等等 |  比较时被调用
`__pos__(self)`                    |  `+self`                               |  一元加符号
`__neg__(self)`                    |  `-self`                               |  一元减符号
`__invert__(self)`                 |  `~self`                               |  按位取反
`__index__(self)`                  |  `x[self]`                             |  对象用来做索引时进行转换
`__nonzero__(self)`                |  `bool(self)`                          |  对象转换成bool值
`__getattr__(self, name)`          |  `self.name` # name不存在              |  访问不存在的属性
`__setattr__(self, name, val)`     |  `self.name = val`                     |  Assigning to an attribute
`__delattr__(self, name)`          |  `del self.name`                       |  Deleting an attribute
`__getattribute__(self, name)`     |  `self.name`                           |  Accessing any attribute
`__getitem__(self, key)`           |  `self[key]`                           |  Accessing an item using an index
`__setitem__(self, key, val)`      |  `self[key] = val`                     |  Assigning to an item using an index
`__delitem__(self, key)`           |  `del self[key]`                       |  Deleting an item using an index
`__iter__(self)`                   |  `for x in self`                       |  Iteration
`__contains__(self, value)`        |  `value in self`, `value not in self`  |  Membership tests using `in`
`__call__(self [,...])`            |  `self(args)`                          |  "Calling" an instance
`__enter__(self)`                  |  `with self as x:`                     |  `with` statement context managers
`__exit__(self, exc, val, trace)`  |  `with self as x:`                     |  `with` statement context managers
`__getstate__(self)`               |  `pickle.dump(pkl_file, self)`         |  Pickling
`__setstate__(self)`               |  `data = pickle.load(pkl_file)`        |  Pickling

Hopefully, this table should have cleared up any questions you might have had about what syntax invokes which magic method.

##<a id="appendix2" href="#appendix2">Appendix 2: Changes in Python 3</a>##

Here, we document a few major places where Python 3 differs from 2.x in terms of its object model:

 - Since the distinction between string and unicode has been done away with in Python 3, `__unicode__` is gone and `__bytes__` (which behaves similarly to `__str__` and `__unicode__` in 2.7) exists for a new built-in for constructing byte arrays.
 - Since division defaults to true division in Python 3, `__div__` is gone in Python 3
 - `__coerce__` is gone due to redundancy with other magic methods and confusing behavior
 - `__cmp__` is gone due to redundancy with other magic methods
 - `__nonzero__` has been renamed to `__bool__`
