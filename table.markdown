#Python的Magic Methods手册#

###Rafe Kettler，翻译：Alex Xiang###

Copyright &copy; 2012 Rafe Kettler

Version 1.17

本手册的PDF版本可以到原作者的[网站](http://www.rafekettler.com/magicmethods.pdf) 或者 [Github](https://github.com/RafeKettler/magicmethods/raw/master/magicmethods.pdf)获取。本手册的github仓库在[http://www.github.com/RafeKettler/magicmethods](http://www.github.com/RafeKettler/magicmethods)。如有问题可以在那里报告，也可以评论，甚至提交贡献。

**<a id="table" href="#table">目录</a>**


 1. [简介](#intro)
 2. [构造和初始化](#construction)
 3. [Making Operators Work on Custom Classes](#operators)
    - [Comparison magic methods](#comparisons)
    - [Numeric magic methods](#numeric)
 4. [Representing your Classes](#representations)
 5. [Controlling Attribute Access](#access)
 6. [Making Custom Sequences](#sequence)
 7. [Reflection](#reflection)
 8. [Abstract Base Classes](#abcs) 
 9. [Callable Objects](#callable)
 10. [Context Managers](#context)
 11. [Building Descriptor Objects](#descriptor)
 12. [复制](#copying)
 13. [Pickling your Objects](#pickling)
 14. [总结](#conclusion)
 15. [附录A: 如何调用Magic Method](#appendix1)
 16. [附录B: Python 3中的改动](#appendix2)