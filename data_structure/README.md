# Python-for-20200314
## 基础三部曲<br>

#1. int float str bool<br>
1, 1.03, 'hello', True<br>
#2. list set dict<br>
[] {} {k:v}<br>
#3. numpy pandas<br>


## 一些对字符串的操作<br>
add()
对两个数组的逐个字符串元素进行连接<br>
multiply()
返回按元素多重连接后的字符串<br>
center() 
居中字符串<br>
capitalize() 
将字符串第一个字母转换为大写<br>
title() 
将字符串的每个单词的第一个字母转换为大写<br>
lower() 
数组元素转换为小写<br>
upper() 
数组元素转换为大写<br>
split() 
指定分隔符对字符串进行分割，并返回数组列表<br>
splitlines() 
返回元素中的行列表，以换行符分割<br>
strip() 
移除元素开头或者结尾处的特定字符<br>
join() 
通过指定分隔符来连接数组中的元素<br>
replace() 
使用新字符串替换字符串中的所有子字符串<br>
decode() 
数组元素依次调用str.decode<br>
encode() 
数组元素依次调用str.encode<br>


## list set dict是什么

python中set代表集合，list代表列表,dict代表字典<br>
set和dict的区别在于，dict是存储key-value，每一个key都是唯一的，set相对于dict存储的是key，且key是唯一的,list除了变量外都可以存储<br>
<br>
dict: X={"a":1,"b":2,"c":3} --》这个就是一个json，长得很像。其中里面a是key，1是value。<br>
set: X={"a","b","c"}--》set里面存的是key，所以都是唯一的。<br>
list: X=["a","b,"c"]--》用方括号的就是list，除了变量之外都可以储存。变量的意思就是举个例子a=10，这样a就是一个变量,10这个变量的值是可以展示的。<br>

### 1.set用法<br>
python 集合的添加有两种常用方法，分别是add和update。<br>
add方法：是把要传入的元素做为一个整个添加到集合中，例如：<br>
```python
a = set('boy')#如果是这个样子写的话，那得到的结果就是下面这个样子。因为set是把字符串都拆开来
{'b', 'o', 'y'}
但是呢，如果输入的是：
a = set(['boy','girl'])#这样子得到的结果就是下面这样了，因为set里面传入的是一个列表,列表是在方括号[]里面的
{'boy', 'girl'}

有一个极好的例子再来加深一下set 和list的区别
set('boyy')
{'b', 'o', 'y'}这个不能有重复的

list('boyy')
['b', 'o', 'y', 'y']这个就可以有重复的了



a=set('boy')
a.add('python')
>>> a
得到{'b', 'o', 'python', 'y'}
上面这个例子有两个点，1、add是add整个元素，不会单独再拆成每个字符；2、顺序是随机的，不同电脑都不一样



# update方法：是把要传入的元素拆分，做为个体传入到集合中，例如：
>>> a = set('boy')
>>> a.update('python')
>>> a
{'b', 'h', 'n', 'o', 'p', 't', 'y'}
上面这个例子也是两个点，1、update是拆分每个字符串加进去，2、顺序是随机的



# 集合删除操作方法：remove
set(['y', 'python', 'b', 'o'])
>>> a.remove('python')
>>> a
{'b', 'o', 'y'}
这里要注意remove是整体的，是add的逆向，都是对整体操作。然后就是没有update的逆向

```


# Python-for-20200315

### 2.list用法
列表的添加可以用 append(e)，追加到底部

```python

lst = [1,2,3,4]
lst.append(5)
print(lst)
[1, 2, 3, 4, 5]
list后面是方括号[]，方括号里面可以直接加有引号的和没引号的都行


lst = ['1','2','3','4']
lst.append(5)
print(lst)
['1', '2', '3', '4', 5]
上面这个例子就可以看出来append里面加的就会直接加到list后面，例如上面就没有加引号。
其中有引号的是字符串，没有引号的数值int


下面这个例子就是在list里面放一个list，在用dataframe的时候会涉及
lst1 = []
lst2 = ['1','2','3','4','5']
lst3 = ['7','9','10','0','19']
lst1.append(lst2)
lst1.append(lst3)
print(lst1)
[['1', '2', '3', '4', '5'], ['7', '9', '10', '0', '19']]


另外还有个重要的场景就是append加上的不是把内容复制一边，而是指针指向同一个内存
lst1 = []
lst2 = ['1','2','3','4','5']
lst1.append(lst2)
lst1
>>>[['1', '2', '3', '4', '5']]
lst2.pop(2)
lst2
>>>['1', '2', '4', '5']
lst1
>>>[['1', '2', '4', '5']]
上面就是pop掉的虽然是list2里面的一个值，但是list1也会同步变化。因为append不是单纯的复制。

如果是用户只是想删除list2里面的值，要保留list1里面的值，就可以通过一个deepcopy的包来实现：

from copy import deepcopy
lst1 = []
lst2 = ['1','2','3','4','5']
lst1.append(deepcopy(lst2))
lst2.pop(2)
lst2
>>>['1', '2', '4', '5']
lst1
>>>[['1', '2', '3', '4', '5']]
这样list1就不变了


```

列表的删除pop(index i)，删除索引所在的元素

```python
list = [1,2,3,4,5]
list.pop(2)
print(list)
[1, 2, 4, 5]
上面这个例子pop掉的是索引的那一列，索引列是从0开始的。我上面pop后面括号是2，所以删除了第三列。
要注意python的索引是从0开始的！

list = ['1','2','3','4','5']
list.pop(2)
print(list)
['1', '2', '4', '5']

```

pop对应的还有insert功能，可以拆入一列索引。

```python
lst = ['1','2','3','4','5']
lst.insert(2, '100')
print(lst)
['1', '2', '100', '3', '4', '5']

这里需要注意一点，上面好多地方还没改。变量命名的时候最好不要和方法名重名，比如这里想说这个是list，那就要lst，或者直接用a\b啥的。
```

列表的删除Remove(e)方法，删除元素e

```python
list = ['1','2','3','4','5']
list.remove('2')
print(list)
['1', '3', '4', '5']
注意一下remove里面的东西是要list里面有的元素，如果上面的remove里面没有加引号，就会报错了。

list = [1,2,3,4,5]
list.remove(2)
print(list)
[1, 3, 4, 5]


```

列表的高级用法list.extend(list2)或者用+，求两个列表相加起来后组成的集合
区别:
extend()是往list中添加list2的元素，不会生成新的元素
+是会生成一个新的list

```python
list1 = [1,2,2]
list2 = [3,4,5]
list1.extend(list2)
print(list1)
[1, 2, 2, 3, 4, 5]


list1 = [1,2,2]
list2 = [3,4,5]
list1 = list1+list2
print(list1)
[1, 2, 2, 3, 4, 5]

上面两个看起来是得到的结果一样，但是实际上第二种用+的实际上生成了一个新的元素。可以叫做list1，也可以更名为别的，存储位置和list1不一样。
存储位置不一样的例子：
list1 = [1,2,2]
print(id(list1))
list2 = [3,4,5]
list1 = list1+list2
print(id(list1))

1838314031944
1838315919112

```
list中reverse的用法，就是把list倒过来

```python
lst = ['1','2','3','4','5']
lst.reverse()
print(lst)
```


### 3.dict词典用法

添加元素dict[' ']=''<br>

```python
dict={"a":1,"b":2,"c":3}
dict['d']=4这里要注意一下，给dict加字段的时候，用的是方框括号[],然后等于的值在后面。如果原本就有d，那会更新d对应的value
print(dict)
>>>{'a': 1, 'b': 2, 'c': 3, 'd': 4}


```

删除元素pop

```python
dict={'a':1,'b':2,'c':3}
dict.pop('c')注意一下这里pop是方法，所以用的是小括号()，dict只能对key操作，所以只能pop掉c，而不能像list一样按照索引pop
print(dict)
>>>{'a': 1, 'b': 2}
```

4.list和set互相转换

```python
lst = [1,2,3,4,5]
a = set(lst)
print(a)
>>>
{1, 2, 3, 4, 5}

b=list(a)
print(b)
>>>[1, 2, 3, 4, 5]
```
