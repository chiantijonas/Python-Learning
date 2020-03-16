# 20200315
## NumPy Ndarray 对象 

array(object, dtype=None, copy=True, order='K', subok=False, ndmin=0) <br>

object <br>
数组或嵌套的数列 <br>
dtype <br>
数组元素的数据类型，可选,数据类型例如str（字符，加引号的）、int（整数）、float（1.05） <br>
copy <br>
对象是否需要复制，可选 <br>
order <br>
创建数组的样式，C为行方向，F为列方向，A为任意方向（默认） <br>
subok <br>
默认返回一个与基类类型一致的数组 <br>
ndmin <br>
指定生成数组的最小维度 <br>


```python
import numpy as np 
a = np.array([[1,  2],  [3,  4]])  
print (a)
>>>
[[1 2]
 [3 4]]
这里就变成两行两列了，是二维了。

import numpy as np 
a = np.array([[[1,2,3,4,5],[6,7,8,9,0]],[[1,2,3,4,5],[6,7,8,9,0]]], ndmin = 3, dtype=int)  
print (a)
>>>
[[[1 2 3 4 5]
  [6 7 8 9 0]]

 [[1 2 3 4 5]
  [6 7 8 9 0]]]
a.shape
(2, 2, 5)三维，两个矩阵，两行五列
上面的这个就是个三位数组

```

## NumPy 数据类型
主要看下int、float、str、bool（True，False）

 
## NumPy 数组属性 

主要就是看下：shape、dtype

# 20200316 
## NumPy 创建数组 
创建一个有固定形状的随机数组
```python
import numpy as np 
np.empty([3,2],dtype = int)
>>>array([[ 0,  0],
       [ 0,  0],
       [ 0, 90]])
```

创建一个有固定形状的值都是0的数组
```python
np.zeros([2,3],dtype = int)
array([[0, 0, 0],
       [0, 0, 0]])
```
另外还有ones，原理同上,但是就可以用1乘以任何数得到其他值的结果
```python
a = np.ones([2,4],dtype = float)
a
>>>array([[1., 1., 1., 1.],
       [1., 1., 1., 1.]])
a*2
>>>array([[2., 2., 2., 2.],
       [2., 2., 2., 2.]])
```   
生成等差数列linspace
```python

np.linspace(2,10,3,dtype=int)
>>>array([ 2,  6, 10])
```


## NumPy 切片和索引
slice用法 
```python
a = np.arange(13,25)
>>>array([13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24])
s = slice(2,9,1)
a[s]
>>>array([15, 16, 17, 18, 19, 20, 21])（左闭右开）
```
但是实际应用的时候不一定会用slice，会同下面这样
```python
a = np.arange(13,25)
a
>>>array([13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24])
a[2:9:1]（这里和slice效果就是一样的，但是要注意这里是冒号！start:stop:step ）
>>>array([15, 16, 17, 18, 19, 20, 21])
```

如果要把索引后面的都拿出来，可以用一下这种方式
```python
a = np.arange(13,25)
a
>>>array([13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24])
a[3:]（这里就是把从第三个索引开始的后面都取出来）
>>>array([16, 17, 18, 19, 20, 21, 22, 23, 24])
```

# 下面还没定时间

## NumPy 字符串函数 

## NumPy 数学函数 

## NumPy 算术函数 

## NumPy 统计函数 

## NumPy 排序、条件刷选函数
