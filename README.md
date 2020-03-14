# Python-for-day-1

## list set dict是什么

python中set代表集合，list代表列表,dict代表字典<br>
set和dict的区别在于，dict是存储key-value，每一个key都是唯一的，set相对于dict存储的是key，且key是唯一的,list除了变量外都可以存储<br>
dict={"a":1,"b":2,"c":3} --》这个就是一个json，长得很像。其中里面a是key，1是value。<br>
set={"a","b","c"}--》set里面存的是key，所以都是唯一的。<br>
list=["a","b,"c"]--》用方括号的就是list，除了变量之外都可以储存。变量的意思就是举个例子a=10，这样a就是一个变量。<br>

1.set用法<br>
python 集合的添加有两种常用方法，分别是add和update。<br>
add方法：是把要传入的元素做为一个整个添加到集合中，例如：<br>
```python
>>> a = set('boy')
>>> a.add('python')

>>> a
set(['y', 'python', 'b', 'o'])
# update方法：是把要传入的元素拆分，做为个体传入到集合中，例如：
>>> a = set('boy')
>>> a.update('python')
>>> a
set(['b', 'h', 'o', 'n', 'p', 't', 'y'])
# 集合删除操作方法：remove
set(['y', 'python', 'b', 'o'])
>>> a.remove('python')
>>> a
set(['y', 'b', 'o'])
```

2.set的高级用法，集合操作
