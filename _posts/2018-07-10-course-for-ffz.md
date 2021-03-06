---
title:     Python Course
key:       2018-07-10
author:    villanelle
mathjax:   true
tags:
    - Python
    - Teaching
---

# Project 2

## 保留字符

保留字符就是python中不能被当作变量的字符，因为这些字符在python中已经被赋予了特殊的意义，例如：`and`是和的意思，`def`是定义函数的意思。

## 注释

#### 单行缩进

```python
a = 3 # 对a这个变量进行赋值
```

`#`后面的就是注释内容，注释内容不会对代码造成任何影像，完全是为了是的你的程序有更好的可读性，更容易让别人和自己理解，这点对于初学者来说，尤其重要。

#### 多行注释

```python
'''
how are you?
fine, thank you and you?
'''

"""
how are you?
fine, thank you and you?
"""
```

`'''`或`"""`，由三个单引或三个双引号号组成，将我们多行注释内容封装起来。

## 行和缩进

python对行和缩进有严格的要求，因为它不像其他语言一样，有`{}`这样的符号表示一段程序块，所以在python需要用缩进来表示代码与代码之间的层级关系。每个缩进需要用四个空格来表示，也可以用一个`tab`键来表示。例如

```python
if A is right:
    print("yes")
    if B is right:
        if C is not right:
            print("yes")
        else:
            print("no")
    
```

（以上代码是不能运行的，我们将在后续章节中解释，上述代码只是用来演示缩进）

## 多行语句

多行语句就是本来一个完整的句子太长，放在一行及不仅破坏了代码的美观性，还破坏了可读性。

整改前：
```python
if A is not handsome and B is not beautiful or A is handsome and B is not beautiful or A is not handsome and B is beautiful or A is handsome and B is beautiful:
```
多行整改后：
```python
if A is not handsome and B is not beautiful 
    or A is handsome and B is not beautiful 
    or A is not handsome and B is beautiful 
    or A is handsome and B is beautiful:
```
整改前：
```python
total = item_one + item_two + item_three
```
（这句话其实不算长，不用整改也行，只是举个例子）
整改后：
```python
total = item_one + \
	item_two + \
        item_three
```

## 引号

python中可以使用单引号`'`，双引号`"`，三引号`'''`或者`"""`，来表示字符串，其中三引号可以由多行组成。

```python
villanelle = "jinze"
ffz = "huminghui"
```

## 标识符

标识符有字母、数字、下划线组成，但是开头不能是数字，可以是下划线、字母，但是以下划线开头的表示符都有特殊的意义。
标识符对大小写敏感，例如`villanelle`和`Villanelle`是不同的标识符。

## 常量

例如自然底数$e$，圆周率$\pi$。

## 变量

变量存贮内存中的值，因此创建变量时，就会在内存中开辟一段内存空间，用来保存我们的值。

#### 变量赋值

```python
a = 100 # 这句话被执行之后，以后a就代表100了
name = "hmh" # 以后name这个变量名就表示hmh了
hmh = "huminghui" # 以后hmh这个变量名就表示huminghui了
```
那么上面的`hmh`和`name`有什么区别呢？
#### 多变量赋值

```python
a = b = c = 1 # 以后a,b,c都将表示1
```

## 标准数据类型

### 数字

- 整型`(int)`：顾名思义就是整数，可以表示的范围是：$[-2^{31} , 2^{31} -1]$
- 浮点数`(float)`：就是小数
- 长整型`(long)`：可以表示更大范围的整数
- 复数`(complex)`

### 字符串

```
"i'm string"
"我是字符串"
'我是常量，我和1、2、3这样的数字的地位是一样的'
'我可以被双引号、单引号包裹，之前讲过的哦'
```

现在你知道之前的`hmh`和`name`有什么区别了么？虽然`name`表示的是`"hmh"`看起来一样，但其实就是`"hmh"`和`hmh`之间的区别。一个是常量，一个是变量，`"hmh"`不能被赋值，而`hmh`可以被赋值。

#### 字符串的操作

- 索引：

  ```python
  >>> a = "abcdefg"
  >>> print(a[0])
  >>> print(a[-1])
  ```

  ```pythton
  a
  ```

- 分割：

  ```python
  >>> hmh = "abc def ghi jkl"
  >>> list1 = hmh.split() # 默认按空格分隔
  >>> print(list1)
  ```

  ```python
  ["abc", "def", "ghi", "jkl"]
  ```

- 合并：

  ```python
  >>> hmh = "hmh"
  >>> villanelle = "villanelle"
  >>> names = hmh + " and " + villanelle
  >>> print(names)
  ```

  ```
  hmh and villanelle
  ```

一个字符串的结构其实类似于一个列表结构，所有列表可以进行的操作，在字符串上基本上都可以进行。

### 列表

列表是一种数据结构，就像表格的某一列，我们告诉别人某个数据在表格的这一列的那个位置，通常都会告诉他，在这一列的第几行。列表也是一个道理。在python中列表的每一个位置的数据类型可以是任意数据类型，可以是整型，浮点型，字符串甚至是列表。我们看下面一个例子：

```python
list1 = ['villanelle', 1, 1.2222, ['hmh', 2]]
```

怎么访问列表中的数据呢？就像表格一样我们告诉程序我们访问的数据在那个位置：

```python
>>> list1[0]
villanelle
>>> list1[1]
1
```

记住，在任何编程语言中(打脸，这次实习用到的lua就不是），索引都是从$0$开始的。

你会发现`list1[2]`同样是一个列表啊，要怎么访问这个列表中的元素呢？看下面的操作：

```python
>>> list1[2]
['hmh', 2]
>>> list1[2][0]
hmh
>>> list1[2][1]
2
```

那我们怎么修改列表中的元素呢，比如我要把`list1[0]`变成`jinze`。我们执行以下操作：

```python
>>> list1[0] = 'jinze'
>>> list1[0]
jinze
```

### 元组

元组类似于列表，不同的地方元组的值不能被改变，也就是说，元组是一个只读的数据类型，一旦被创建就不会被修改。

元组的表示形式如下：

```python
tuple1 = ('villanelle', 1, 2, 2.33333, ['hmh', 1111], ('ppppp', 12312), 2222)
```

### 字典

我们想象一下，平时我们查字典的时候，是不是每个单词下面都有自己对应的解释？在程序中我们称前面的单词为：key，称其中的解释为：value。我们来看一个例子：

```python
dict1 = {'jinze' : 'villanelle', 'huminghui' : 'hmh'}
```

再比如：

```python
phone_book = {'jinze' : 156****9980, 'hmh' : 123*********}
```

怎么访问呢？

```python
>>> dict1['jinze']
villanelle
>>> dict1['huminghui']
hmh
```

这样我们的索引，和索引表示的内容都能有了特殊的意义，当然这还不是它主要的作用，他是一个集合类型，也就是说，元素之间会有互异性，只能有一个`jinze`也只能有一个`huminghui`，你会在以后的运用中，感受到字典的强大。

## 运算符

### 算数运算符

```python
>>> 1 + 2 
3
>>> 4 / 3
1.333333333333333
>>> 4 // 3
1
>>> 4 % 3
1
```

就是不同的加减乘除，余数，注意看上面`/`，和`//`的区别，后者是向下取整。

### 比较运算符

| 运算符 | 描述                             | 实例                              |
| ------ | -------------------------------- | --------------------------------- |
| `==`   | 判等符：比较两个对象是不是相等的 | `'villanelle' == 'hmh'`，返回`False` |
| `!=`   | 比较两个对象是不是不相等         | `'villanelle' != 'hmh'`，返回`True`  |
| `>`    | 大于                             | `2 > 1`，返回`True`               |
| `<`    | 小于                             | `1 < 0`，返回`False`              |
| `<=`   | 小于等于                         | `2 <= 2`， 返回`True`             |
| `>=`   | 大于等于                         | `1 >= 2`，返回`False`             |

不用在这纠结什么是返回`True`,`False`。

### 赋值运算符

| 运算符 | 描述             | 实例                                  |
| ------ | ---------------- | ------------------------------------- |
| `=`    | 简单的赋值运算符 | c = a + b 将 a + b 的运算结果赋值为 c |
| `+=`   | 加法赋值运算符   | c += a 等效于 c = c + a               |
| `-=`   | 减法赋值运算符   | c -= a 等效于 c = c - a               |
| `*=`   | 乘法赋值运算符   | c *= a 等效于 c = c * a               |
| `/=`   | 除法赋值运算符   | c /= a 等效于 c = c / a               |
| `%=`   | 取模赋值运算符   | c %= a 等效于 c = c % a               |
| `**=`  | 幂赋值运算符     | c \**= a 等效于 c = c\*\* a           |
| `//=`  | 取整除赋值运算符 | c //= a 等效于 c = c // a             |

### 逻辑运算符

Python语言支持逻辑运算符，以下假设变量 a 为 10, b为 20;

| 运算符 | 逻辑表达式 | 描述                                                         | 实例                      |
| ------ | ---------- | ------------------------------------------------------------ | ------------------------- |
| `and`  | `x and y`  | 布尔"与" - 如果 x 为 False，x and y 返回 False，否则它返回 y 的计算值。 | (a and b) 返回 20。       |
| `or`   | `x or y`   | 布尔"或"	- 如果 x 是非 0，它返回 x 的值，否则它返回 y 的计算值。 | (a or b) 返回 10。        |
| `not`  | `not x`    | 布尔"非" - 如果 x 为 True，返回 False 。如果 x 为 False，它返回 True。 | not(a and b) 返回 `False` |

### 成员运算符

| 运算符   | 描述                                                    | 实例                                                |
| -------- | ------------------------------------------------------- | --------------------------------------------------- |
| `in`     | 如果在指定的序列中找到值返回 True，否则返回 False。     | x 在 y 序列中 , 如果 x 在 y 序列中返回 `True`。     |
| `not in` | 如果在指定的序列中没有找到值返回 True，否则返回 False。 | x 不在 y 序列中 , 如果 x 不在 y 序列中返回 `True`。 |

### 身份运算符

| 运算符   | 描述                                        | 实例                                                         |
| -------- | ------------------------------------------- | ------------------------------------------------------------ |
| `is`     | is 是判断两个标识符是不是引用自一个对象     | **x is y**, 类似 **id(x) == id(y)** , 如果引用的是同一个对象则返回 True，否则返回 `False` |
| `is not` | is not 是判断两个标识符是不是引用自不同对象 | **x is not y** ， 类似 **id(a) != id(b)**。如果引用的不是同一个对象则返回结果 `True`，否则返回 `False`。 |

### 运算符优先级

| 运算符                     | 描述                                                   |
| -------------------------- | ------------------------------------------------------ |
| `**`                       | 指数 (最高优先级)                                      |
| `~ + -`                    | 按位翻转, 一元加号和减号 (最后两个的方法名为 +@ 和 -@) |
| `* / % //`                 | 乘，除，取模和取整除                                   |
| `+ -`                      | 加法减法                                               |
| `>> <<`                    | 右移，左移运算符                                       |
| `&`                        | 位 'AND'                                               |
| `^ |`                      | 位运算符                                               |
| `<= < > >=`                | 比较运算符                                             |
| `<> == !=`                 | 等于运算符                                             |
| `= %= /= //= -= += *= **=` | 赋值运算符                                             |
| `is is not`                | 身份运算符                                             |
| `in not in`                | 成员运算符                                             |
| `not or and`               | 逻辑运算符                                             |

# Project 3

## 认识语法

### 输入输出

```python
n = input()
print(n)
```

运行后的效果是：

```python
>>> 10
10
```

```python
>>> hmh
hmh
```

---

```python
input_ = input("请输入内容:")
print(input_)
```

运行后的效果是：

```python
>>> 请输入内容:你好吗?
你好吗?
```

上面两者的区别就是，我们调用`input()`方法时，有没有给这个方法传参数，比如第一个没有传参数，运行时就没有提示信息，但是第二个我们传入了”请输入内容“的参数，就会在程序运行后先出现”请输入内容“这样的提示。

关于输出我们只要调用一下`print()`方法就可以了，参入的参数就是我们要输出的内容。

那我们要怎么格式化输出我们的东西的呢？比如我们先输入一个数字3并保存在n这个变量中，我们要输出的内容是：hmh比villanelle小n天。我们可以用下面的输出方式:

```python
n = int(input())
print("hmh比villanelle小%d天" % n)
print("hmh比villanelle小" + str(n) + "天")
```

这里有三个小问题留给你：

- 为什么我要使用`int(input())`而不是`input()`？
- `%d`是什么意思？为什么不会输出"hmh比villanelle小%d天"，而是输出了"hmh比villanelle小15天"？
- 为什么第二种输出方式`n`要用`str(n)`的形式？

请通过微信或者微信语音聊天的方式告诉我你的答案或者疑问。

#### 小练习

[实验任务1-1~1-4](https://admin.buaacoding.cn/problem/index)

## 条件语句

条件语句，顾名思义就是：如果怎么样就会怎么样，如果是另外怎么样，就会怎么样，否则就会怎么样。

在python中的结构就是：

```python
if 怎么样:
    就会怎么样
elif 怎么样：
    就会怎么样
elif 怎么样：
    就会怎么样
...
else:
    就会怎么样
```

我们来看一个具体的例子：

```python
a = 10
b = 10
if a == 10:
    print("a + 1 = %d" %(a + 1))
elif b == 10:
    print("b = %d" %b)
else:
    print("others")
```

执行后的结果应该是：

```python
a + 1 = 11
```

#### 问题

为什么第二个条件同样满足却不会被执行呢？

我们再看：

```python
a = 10
b = 10
if a == 10:
    print("a == %d" %a)
if b == 10:
    print("b == %d" %b)
```

运行后会是什么样的结果？你自己运行试一下，并解释为什么包括上一个问题。

#### 小练习

在三个数求最大数值的案例中，还要输出是哪个数最大，应该如何设计算法？ 请给出代码。

## 循环语句

### `while`循环

`while`循环语句的结构是这样的：

```python
a = 0
while a != 10:
    a += 1
```

什么意思呢？就是`while`后面的条件`a != 10`成立时，就执行下面的语句`a += 1`，直到`a`被加到了10这个循环就会被终止。

### `for`循环

`for`循环语句的结构是这样的：

```python
for i in range(0, 11):
	print(i)
```

这句话等价与c语言中的如下`for`循环：

```c
int i;
for(i = 0; i < 11; i ++){
    printf("%d", i);
}
```

也就是我们现在有一个变量`i`（你可以叫变量`j,k,blaba`随便什么不是保留字的就行），要用这个`i`遍历范围$[0,11)$，左闭右开，每次执行完一次循环体里面的语句，就会执行此`i += 1`操作，这在c语言里面是显示的，但是在python中以迭代的方式进行。

#### 小练习

- 完成1-1000的加法

### 嵌套循环

我们看下面几个简单的嵌套循环：

```python
for i in range(0, 11):
	for j in range(0, 11):
        print(i + j)
```

```python
for i in range(0, 11):
    j = 0
    while j != 11:
        j += 1
        print(i + j)
```

```python
i = 0
while i != 11:
    i += 1
    for j in range(0, 11):
        print(i + j)
```

上述三种嵌套循环的输出是一样的吗？如果一样为什么？如果不一样为什么？

#### 小练习

用两层循环打印出一个形如下的$3*3$的坐标矩阵

```python
(1,1) (1,2) (1,3)
(2,1) (2,2) (2,3)
(3,1) (3,2) (3,3)
```

**Hint**：`print`函数输出时是默认会换行的比如：

```python
print("hmh")
print("villanelle")
```

输出为：

```python
hmh
villanelle
```

那要怎么使它不换行呢？就用如下方式：

```python
print("hmh", end="")
print("villanelle", end="")
```

输出为：

```python
hmhvillanelle
```

这里面`end`是给`print`这个方法传的另一个参数，表示以什么作为结尾。

### 循环控制语句

#### `break`

`break`命令一执行就会**跳出循环**，我们看下面几个例子：

```python
a = 0
while True: # True 是python中的保留字 while True，则condition永远为True，所以我们得在内部停止它
    if a == 10:
        break
	a += 1
```

```python
n = int(input())
for i in range(2, n):
    if n % i == 0:
        print("%d is not a Prime Number." %n)
        break
```

```python
n = int(input())
for i in range(0, n):
    m = int(input())
    for j in range(0, m):
        if j % 7 == 0:
            break
```

#### 问题

在第三个样例中，`break`结束的是哪个循环？

##### `continue`

`continue`比较简单，就是什么都不做，继续循环体下一步：

```python
for i in range(0, 101):
    if i % 2 != 0:
        continue
    print(i)
```

虽然上述可以被简化成：

```python
for i in range(0, 101):
    if i % 2 == 0:
        print(i)
```

但我只是作为一个例子，我们再看下面的一个例子：

```python
for i in range(0, 101):
    if i % 2 == 0:
        continue
        print(i)
    print(i)
```

上面这个例子程序会输出什么呢？

#### `pass`

和`continue`类似，所用在写完一个函数的定义或者循环体之后，内容没写，可以先用这个填充

```python
def hmh: # 定义一个函数
    pass # 啥都没干，先pass一下，可以过编译
```
#### 小练习

[实验任务2-1~2-5](https://admin.buaacoding.cn/problem/index)

## 列表操作

我们知道列表的结构:

```python
list1 = ["A", "B", 111, 222, 1.11, "hmh", [1111, 2222], (1,2)]
```

我们现在有一个空的列表：

```python
list1 = []
```

### 加入元素

现在我们要按照我们自己的想法往列表里面加入元素，比如我们要把0-10中所有偶数加到列表中，我们使用我们调用列表在python中给我提供的方法`append`，如下：

```python
for i in range(0, 11):
    if i % 2 == 0:
        list1.append(i)
print(list1)
```

```python
[0, 2, 4, 6, 8, 10]
```

### 更新元素

我们想把第二个偶数换成3：

```python
list1[1] = 3
print(list1)
```

```python
[0, 3, 4, 6, 8, 10]
```

### 删除列标元素

我们把3这个不是偶数的数删去

```python
del(list1[2])
print(list1)
```

```python
[0, 4, 6, 8, 10]
```

### 列表的排序

我们现在有一个纯数字的列表：

```python
list1 = [2, 3, 1, 4, 24, 5, 56]
```

然后我们对其升序排序：

```python
list1.sort()
pritn(list1)
```

就可以得到：

```python
[1, 2, 3, 4, 5, 24, 56]
```

---

如果我们这样：

```python
list1.sort(reverse=True)
print(list1)
```

就会得到：

```python
[56, 24, 5, 4, 3, 2, 1]
```

降序输出。

### 列表脚本操作符

列表对 + 和 * 的操作符与字符串相似。+ 号用于组合列表，* 号用于重复列表。

如下所示：

| Python 表达式                           | 结果                         | 描述                 |
| --------------------------------------- | ---------------------------- | -------------------- |
| `len([1, 2, 3])`                        | 3                            | 长度                 |
| `[1, 2, 3] + [4, 5, 6]`                 | [1, 2, 3, 4, 5, 6]           | 组合                 |
| `['Hi!'] * 4`                           | ['Hi!', 'Hi!', 'Hi!', 'Hi!'] | 重复                 |
| `3 in [1, 2, 3]`                        | True                         | 元素是否存在于列表中 |
| `for x in [1, 2, 3]: print(x, end=" ")` | 1 2 3                        | 迭代                 |

### 列表截取与拼接

列表截取与字符串操作类型，如下所示：

```python
L=['Google', 'Runoob', 'Taobao']
```

操作：

| Python 表达式 | 结果                 | 描述                                               |
| ------------- | -------------------- | -------------------------------------------------- |
| `L[2]`        | 'Taobao'             | 读取第三个元素                                     |
| `L[-2]`       | 'Runoob'             | 从右侧开始读取倒数第二个元素: count from the right |
| `L[1:]`       | ['Runoob', 'Taobao'] | 输出从第二个元素开始后的所有元素                   |

列表还支持拼接操作：

```python
>>> squares = [1, 4, 9, 16, 25]
>>> squares += [36, 49, 64, 81, 100]
>>> squares
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

### 列表函数&方法

| 序号 | 函数                           |
| ---- | ------------------------------ |
| 1    | `len(list)`列表元素个数        |
| 2    | `max(list)` 返回列表元素最大值 |
| 3    | `min(list)`返回列表元素最小值  |
| 4    | `list(seq)` 将元组转换为列表   |

| 序号 | 方法                                                         |
| ---- | ------------------------------------------------------------ |
| 1    | `list.append(obj)` 在列表末尾添加新的对象                    |
| 2    | `list.count(obj)`统计某个元素在列表中出现的次数              |
| 3    | `list.extend(seq)` 在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表） |
| 4    | `list.index(obj)`从列表中找出某个值第一个匹配项的索引位置    |
| 5    | `list.insert(index, obj)` 将对象插入列表                     |
| 6    | `list.pop([index=-1\]])`移除列表中的一个元素（默认最后一个元素），并且返回该元素的值 |
| 7    | `list.remove(obj)` 移除列表中某个值的第一个匹配项            |
| 8    | `list.reverse()`反向列表中元素                               |
| 9    | `list.sort(cmp=None, key=None, reverse=False)` 对原列表进行排序 |
| 10   | `list.clear()` 清空列表                                      |
| 11   | `list.copy()` 复制列表                                       |

## 字典操作

### 字典的访问

```python
dict = {'Alice': '2341', 'Beth': '9102', 'Cecil': '3258'}
```

```python
>>> dict['Alice']
'2341'
>>> dict['Cecil']
'3248'
```

### 字典的修改

```python
dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'};
dict['Age'] = 8 # modify the Age
dict['School'] = 'DPF School' # Add new entry
```

### 删除字典元素

```python
dict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'};
del dict['Name'] # 删除一个条目
dict.clear() # 清空整个字典，但是dict这个字典还在，只是里面什么都没有了
del dict # 删除这个字典
```

### 字典内置函数方法

| 序号 | 函数及描述                                                   |
| ---- | ------------------------------------------------------------ |
| 1    | `cmp(dict1, dict2)` 比较两个字典元素。                       |
| 2    | `len(dict)` 计算字典元素个数，即键的总数。                   |
| 3    | `str(dict)` 输出字典可打印的字符串表示。                     |
| 4    | `type(variable)` 返回输入的变量类型，如果变量是字典就返回字典类型。 |

| 序号 | 函数及描述                                                   |
| ---- | ------------------------------------------------------------ |
| 1    | `dict.clear()`删除字典内所有元素                             |
| 2    | `dict.copy()`返回一个字典的浅复制                            |
| 3    | `dict.fromkeys(seq[, val\])`创建一个新字典，以序列 seq 中元素做字典的键，`val` 为字典所有键对应的初始值 |
| 4    | `dict.get(key, default=None)` 返回指定键的值，如果值不在字典中返回default值 |
| 5    | ~~`dict.has_key(key)` 如果键在字典dict里返回`True`，否则返回`False`~~(python2用法，我们是python3)，可以用`key in dict.keys()`来表示 |
| 6    | `dict.items()`以列表返回可遍历的(键, 值) 元组数组            |
| 7    | `dict.keys()`以列表返回一个字典所有的键                      |
| 8    | `dict.setdefault(key, default=None)` 和`get()`类似, 但如果键不存在于字典中，将会添加键并将值设为default |
| 9    | `dict.update(dict2)` 把字典dict2的键/值对更新到dict里        |
| 10   | `dict.values()` 以列表返回字典中的所有值                     |
| 11   | `pop(key[,default\])` 删除字典给定键 `key` 所对应的值，返回值为被删除的值。key值必须给出。 否则，返回`default`值。 |
| 12   | `popitem()` 随机返回并删除字典中的一对键和值。               |

#### 小练习

[知难而上](https://admin.buaacoding.cn/problem/1326/index)

## Project 4

### 函数

#### 函数的定义

- 函数代码块以单词`define`的缩写`def`开头，`def`是一个关键字，即保留字；
- `def`后接函数的名字，也就是你给这个函数取的名字，名字后**紧**跟的是`()`；
- `()`内是我们传入的参数，`()`之后紧跟的就是`:`；
- 注意函数块内的缩进，块内代码首先是从属于上面函数的定义的，其他缩进规则个之前所说一样；

```python
def get_sum(n):
    sum = 0
    for i in range(1, n + 1):
        sum += i
    print(sum)
```

上面这个函数的作用就是计算$1$到$n$的值，然后打印出来，因此我们传入的参数就是$n$。

我们要怎么使用这个函数呢？

```python
def get_sum(n):
    sum = 0
    for i in range(1, n + 1):
        sum += i
    print(sum)
    
# 直接传入一个具体的参数    
get_sum(10000)
# 可以传入我们定义的变量
n = int(input())
get_sum(n)
```

#### 变量的生命周期

##### 全局变量

全局变量就是在整个代码的任意地方都可以被调用的变量。

##### 私有变量

只能被定义它的代码块内部访问，其他地方均不能访问。

##### 实例

```python
a = 99
def print_some():
    b = 100
    print(a)
    print(b)
print_some()
print(b)
```

运行后：

```python
99
100
-----------------------------------------------------------------------
NameError                             Traceback (most recent call last)
<ipython-input-11-6fad8591f56a> in <module>()
      5     print(b)
      6 print_some()
----> 7 print(b)

NameError: name 'b' is not defined
```

`NameError`那一行就很明确的指出了你的`b`没有被定义，因为`b`的生命周期就只有一个函数那么短，它只在函数中定义了，并在函数结束时，结束了生命，因此其它地方会认为`b`这个名字并没有被定义。

#### 参数

```python
def sum1(a, b):
    print("%d + %d = %d" %(a ,b ,a + b))
    
sum1(1, 2)
```

我们为函数`sum1`设置了两个参数`a,b`，我们按顺序将`1,2`传入函数。

输出就是：

```python
1 + 2 = 3
```

我们调换以下传入参数`1,2`的顺序就是：

```python
2 + 1 = 3
```

我们换一种方式：

```python
def sum1(a, b):
    print("%d + %d = %d" %(a ,b ,a + b))
    
sum1(b=2, a=1)
```

输出就是：

```python
1 + 2 = 3
```

这里的意思就是我们指定了哪个参数的是什么。

#### 函数的返回值

`return`表示退出函数，可以带参数，这个参数同样可以是任意类型的。没有带参数的表示返回`None`。

```python
def sum_(a, b):
    total = a + b
    print("1.a + b = " + str(total))
    return total
total = sum_(10, 20)
print("2.a + b = " + str(total)
```

运行结果是：

```
1.a + b = 30
2.a + b = 30
```

函数外的`total`接收到的值是函数**返回**给它的。

另外一个例子，稍难一点的：

```python
n = 10
def dig(depth):
    if depth == n:
        return
    print(depth)
   	dig(depth + 1)
dig(10)
```

输出:

```python
0
1
2
3
4
5
6
7
8
9
```

你看这个`dig`函数像不像在打洞在挖掘，往下挖到$10$时，不挖了，**直接`return`退出**，因此就不会执行后面的代码了（这里涉及到的思想是**递归**）。

再看，求费波纳列数列第$n$个数：

```python
def fib(n):
    if n == 1 or n == 2:
        return 1
    return fib(n - 1) + fib(n - 2)
print(fib(10))
```

输出：

```
55
```

### 模块

我们有时写了一些方法，具有普适作用，比如我们想要求斐波那契额第$n$个数时，我们就可以调用上面的方法，我们可以把这个函数复制粘贴到我们的新程序中，但是有时候我们写的方法很长很复杂， 有很多的依赖关系，我们直接复制粘贴进我们的新程序中总不是一个好的方法，这时候我们就需要用到模块这个概念。

模块非常重要，为什么重要，就是因为，在python中，有很多大牛，很多科学家，写了成千上万的方法，这些方法，自己去实现非常复杂，因此我们通过引用这些大牛或者某个机构或者python内置的模块来调用这些方法，就可以减轻我们的工作量。python也正是因为这成千上万的模块而变得非常强大。

#### 模块的引入

**第一种**

比如我们要引入python中的`math`库

```python
import math
print(math.e)
print(math.pi)
```

输出是：

```
2.718281828459045
3.141592653589793
```

也就是python中默认的自然底数和圆周率。从这里你也就看到了，想要引用模块中的内容就是：模块名 + 点 + 内容。我们再看引用模块中的方法，比如我们要求两个数之间的最大公因数：

```python
import math
print(math.gcd(55, 30))
```

```
5
```

其中我们就是通过`math.gcd()`来调用该方法的。

我们通过`import math as m`来给`math`简称`m`，这里`math`模块名字还是比较简短的，简不简称无所谓。

但像`tensorflow`这样的名字稍长的我们就最好简称一下`import tensorflow as tf`，`import numpy as np`。

在以后的高阶内容的学习中你可能会经常碰见`panda`,`numpy`,`scipy`等等模块，没有这些模块，你学了python也没有用。

**第二种**

有些模块非常庞大，里面有许多小模块，我们每次都把整个大模块全都引用进来显然不是什么聪明的做法。例如我们要画一张图表：

```
from matplotlib import pyplot as plt
import numpy as np

np.random.seed(19680801)
data = np.random.randn(2, 100)

fig, axs = plt.subplots(2, 2, figsize=(5, 5))
axs[0, 0].hist(data[0])
axs[1, 0].scatter(data[0], data[1])
axs[0, 1].plot(data[0], data[1])
axs[1, 1].hist2d(data[0], data[1])

plt.show()
```

就可以得到：

![1532692392570](https://github.com/paradoxtown/old_blog/blob/master/img/1532692392570.png?raw=true)

`from matplotlib import pyplot as plt`的意思就是从`matplotlib`这个模块中调用`pyplot`并将其简称为`plt`。怎么样看到这段短短的代码画出了四幅图是不是开始觉得python酷炫了起来。

#### 模块的安装

我们安装的python并不是一开始就有那么多模块的，如果我们的python一开始装了那么多模块，我们的python就会变得非常巨大，而且模块是取之不尽用之不竭的，时时刻刻就会有新的模块产生，而且我们自己就可以为python写模块。

因此我们只是在需要哪个模块的时候安装上就是了。

- 检查是否安装`pip`
- 用`pip install module_name`来安装库
- `pip`会从某几个指定的模块库里面下载我们想要的模块
- 很多模块之间又相互依赖关系，我们想要下某个模块的时候，往往要下载另一个模块，`Anaconda`很好的为我们解决了这个问题
- 很多模块库都是国外的，因此有时下载非常慢，或者根本就不能下载，国内的清华镜像就给我提供了好东西

执行：

```
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package
```

清华镜像每5分钟同步一次，基本能保持最新版本。

# Project 5

## I/O操作

### 文件的读取

我们要读取文件内容，用下面的这条代码，`file`是我们的变量名，这个变量的类型是文件类型对象，具体一个文件类型的对象有什么属性我们会在后面讲。

```python
file = open("./hello.txt", "r")
```

我们解析上面的代码：

```python
var_name = open(file_path, access_mode, buffering)
```

`open`就是打开文件的意思，`file_path`意思就是我们的文件的路径是什么，`access_mode`是我们的操作模式，这里我们读取文件内容，我们用`"r"`，`buffering`如果buffering的值被设为0，就不会有寄存。如果buffering的值取1，访问文件时会寄存行。如果将buffering的值设为大于1的整数，表明了这就是的寄存区的缓冲大小。如果取负值，寄存区的缓冲大小则为系统默认，暂时用不到。

```python
text = file.read()
```

上面这行代码我们将文件所有内容都读了进来，并保存在`text`这个变量中，此时`text`是一个字符串类型的变量。

```python
text_lines = file.readlines()
file.close()
```

按行读取文件所有的文件内容，此时`text_lines`为所有元素为字符串类型的列表。

其他的`access_mode`:

| 模式 | 描述                                                         |
| ---- | ------------------------------------------------------------ |
| `r`  | 以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。 |
| `rb` | 以二进制格式打开一个文件用于只读。文件指针将会放在文件的开头。这是默认模式。一般用于非文本文件如图片等。 |
| `r+` | 打开一个文件用于读写。文件指针将会放在文件的开头。           |

### 文件的写入

和读取类似，我们换一种`access_mode`:

```python
file = open("./test.txt", "w")
```

如果该路径没有该文件，那么程序就会自动在那个位置创建一个文件。`"w"`就是`write`的缩写，意思就是我们要对这个文件进行写的操作。

```python
file.write("hello hmh.\n")
file.write("nice to meet you!\n")
file.close()
```

前两句的意思呢就是，我们调用了文件这个对象的`write`方法，并传了一个字符串参数，这个参数就会被写进文件里面。最后一句`file.close`意思就是，我们处理完了，我们要关闭这个文件。

| 模式  | 描述                                                         |
| ----- | ------------------------------------------------------------ |
| `w`   | 打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。 |
| `wb`  | 以二进制格式打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。一般用于非文本文件如图片等。 |
| `w+`  | 打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。 |
| `wb+` | 以二进制格式打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。一般用于非文本文件如图片等。 |
| `a`   | 打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。 |
| `ab`  | 以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。 |
| `a+`  | 打开一个文件用于读写。如果该文件已存在，文件指针将会放在文件的结尾。文件打开时会是追加模式。如果该文件不存在，创建新文件用于读写。 |
| `ab+` | 以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。如果该文件不存在，创建新文件用于读写。 |

### `File`对象属性

| 属性             | 描述                                                         |
| ---------------- | ------------------------------------------------------------ |
| `file.closed`    | 返回true如果文件已被关闭，否则返回false。                    |
| `file.mode`      | 返回被打开文件的访问模式。                                   |
| `file.name`      | 返回文件的名称。                                             |
| `file.softspace` | 如果用print输出后，必须跟一个空格符，则返回false。否则返回true。 |

### `os`模块

我们简单介绍几种常用的`os`方法，`os`应该在今后你处理数据的时候会经常用到（反正我处理数据的时候经常用到，就不用`os`模块进行文件读写，也会用其他库来进行读写，总之就是数据处理离不开文件读写）。

首先我们引入模块`os`

```python
import os
```

获取某个目录文件下所有文件的文件名：

```python
path = "E:/NELIST-PROJECT/project/data/text_data/abbey"
files = os.listdir(path)
for file in files:
    print(file)
```

输出就是：

```python
clipart_000000004246.npy
clipart_000000004247.npy
clipart_000000004248.npy
clipart_000000004249.npy
clipart_000000004250.npy
clipart_000000004251.npy
clipart_000000004252.npy
clipart_000000004253.npy
clipart_000000004254.npy
clipart_000000004255.npy
clipart_000000004256.npy
clipart_000000004257.npy
clipart_000000004258.npy
clipart_000000004259.npy
clipart_000000004260.npy
clipart_000000004261.npy
clipart_000000004262.npy
......
```

创建文件夹：

```python
os.mkdir("./dir")
```

重命名文件：

```python
os.rename("./test.txt", "./test2.txt")
```

删除文件：

```python
os.remove("./test2.txt")
```

递归删除文件夹：

```python
os.removedirs("./dir")
```

目前就以上的模块内函数比较有用。在python中一个模块的函数就可能有无数个，我们不可能全都记住，所以在我们需要什么方法的时候，我们再去查找有没有可以完成我们想要的方法的模块。当然常用的库，我们要很熟才行，就像我之前说的`pandas`，`numpy`，`matplotlib`。

### `Excel`操作

[资料](https://github.com/villanelletown/documents/blob/master/%E3%80%8A%E5%A4%A7%E5%AD%A6%E8%AE%A1%E7%AE%97%E6%9C%BA%E5%9F%BA%E7%A1%80%E3%80%8B%E7%AC%AC9%E6%AC%A1%E8%AF%BE%E4%BB%B6_0507.pdf)

# Project 6



---

*基础部分完结*

---

#  Project 7

## 练习题

- [够了够了](https://admin.buaacoding.cn/problem/1383/index)

- **全排列**

  全排列的意思就是将$1-n$这$n$个数的所有排列情况按照一定的顺序表示出来，例如$1-3$的全排列：

  ```
  1 2 3
  1 3 2
  2 1 3
  2 3 1
  3 1 2
  3 2 1
  ```

  以上是按照字典序的顺序表示的。

  现在要你写一个程序，输入是一个数$n$，输出是$1-n$的按字典序排列的全排列。

  ```python
  n = int(input())
  a = [0] * (n + 1)
  b = [0] * (n + 1)
  
  def permutation(m):
      if m == n + 1:
          for i in range(1, n + 1):
              print(a[i], end="")
          print()
          return
      for i in range(1, n + 1):
          if b[i] == 0:
              b[i] = 1
              a[m] = i
              permutation(m + 1)
              b[i] = 0
  
  permutation(1)
  ```

  理解一下递归的思想，不过不懂也没有关系。

- [实验4-3](https://admin.buaacoding.cn/problem/1231/index)

- [实验4-4](https://admin.buaacoding.cn/problem/1232/index)双列表

- [实验5-1](https://admin.buaacoding.cn/problem/1259/index)字典

- [实验5-3](https://admin.buaacoding.cn/problem/1261/index)字典
