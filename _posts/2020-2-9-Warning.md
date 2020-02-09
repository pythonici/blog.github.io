---
layout: post
title: Waring
---
在数据分析的比赛过程中出现一条警告，只是当时没空理。

今天想起来就在stackoverflow搜索一下，高赞的回答太有趣了，这里分享一下：


FutureWarning: elementwise comparison failed;

returning scalar, but in the future will perform elementwise comparison

此FutureWarning不是来自Pandas，而是来自numpy，并且该错误也影响了matplotlib和其他漏洞。

这里发生了什么？ 当您将字符串与numpy的数字类型进行比较时，Numpy和本机python在应该发生的事情上存在分歧。

应该返回Python样式的标量还是Numpy样式的boolean布尔值？

Numpy说是布尔的ndarray，Pythonic开发人员不同意，经典的对峙。

如果您的代码或库使用in或==运算符将python字符串与numpy ndarrays比较，则它们不兼容。因此，当您尝试使用它时，它将返回标量，但仅在现在。警告表示将来这种行为可能会改变，Numpy和Python处于僵持状态，目前操作返回标量，但将来可能会改变。
 
 两种解决方法： 锁定您的python和numpy版本，忽略警告并期望行为不会改变。
 
 全局禁止警告：
 ```
import warnings
with warnings.catch_warnings():
    warnings.simplefilter(action='ignore', category=FutureWarning)
 ```
只需按名称抑制警告，然后在其旁边大声地提及python和numpy的当前版本，并说此代码很脆弱，需要这些版本。

TLDR： pandas是绝地武士；numpy是赫特人, 并且python是银河帝国。
 
 或者转换numpy类型或原始python数值类型的左和右操作数，使用in替换==
 
 
