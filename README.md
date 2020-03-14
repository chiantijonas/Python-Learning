# Python-for-day-1

## list set dict是什么

python中set代表集合，list代表列表,dict代表字典<br>
set和dict的区别在于，dict是存储key-value，每一个key都是唯一的，set相对于dict存储的是key，且key是唯一的,list除了变量外都可以存储<br>
<br>
dict: X={"a":1,"b":2,"c":3} --》这个就是一个json，长得很像。其中里面a是key，1是value。<br>
set: X={"a","b","c"}--》set里面存的是key，所以都是唯一的。<br>
list: X=["a","b,"c"]--》用方括号的就是list，除了变量之外都可以储存。变量的意思就是举个例子a=10，这样a就是一个变量。<br>

1.set用法<br>
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

-------------------------------------------分割线以上为20200314<br>
2.list用法
列表的添加 append(e)，追加到底部

列表的删除pop(index i)，删除索引所在的元素

列表的删除Remove(e)方法，删除元素e

列表的高级用法list.extend(list2)或者用+，求两个列表相加起来后组成的集合
区别:extend()是往list中添加list2的元素，不会生成新的元素
+是会生成一个新的list

 
3.dict词典用法
添加元素dict[' ']=''

删除元素pop

 
4.list和set互相转换

 


