1、元组：可由不同元素组成，每个元组可为不同数据类型，元组一旦被创建就不可被修改。变量名 = (元素1,元素2,...)

元组[m:n],表示读取第m+1到第n个元素
```python
a = (1,"d",(1,"cc"))
print (a[0])  #打印元组第一个元素 
>>>1
print (a[-1]) #打印倒数第一个元组
>>>(1,"cc")
print (a[2])  #打印第三个元组
>>>(1,"cc")
print (a[-1][-1]) #打印倒数第一个元素元组中倒数第一个元素
>>>"cc"
print (a[2][0])  #打印第三个元素元组中的第一个元素
>>>1
print (a[1:3])  #打印第二到第三个元素
>>>"d",(1,"cc")
print (a[0:-1]) #打印第一个到倒数第二个元素
>>>1,"d"
```
2、列表：可以增删改。变量名 = [元素1,元素2,...]

list.append(元素)：调用列表的添加方法加入元素，并将元素添加到列表最后

list.insert(索引位置,元素)：调用列表的插入方法加入元素到指定的索引位置，之后的元素依次后移

list.remove(元素)：调用列表的移除方法删除元素，之后的元素依次前移

list[n] = 元素(新)：读取列表中的某个元素并重新赋值

list1.extend(list2)：调用列表1的扩展方法加入列表2，并将列表2的元素放到列表1元素后.list1 = list1 + list2
```python
a = [1,"d",(1,"cc")]
b = [1,"aha"]
a.append("x")
print (a)
>>>[1,"d",(1,"cc"),"x"]
a.insert(3,"c")
print (a)
>>>[1,"d",(1,"cc"),"c","x"]
a.remove("d")
print (a)
>>>[1,(1,"cc"),"c","x"]
a[-2] = 3
print (a)
>>>[1,(1,"cc"),3,"x"]
a.extend(b)
print (a)
>>>[1,(1,"cc"),3,"x",1,"aha"]
```
3、字典：由一系列“键-值”成对组成，每一组可以理解为元组和列表的一个元素，并通过{}包含起来。通过键来作为索引。

dic = {键1:值1,键2:值2,...}

字典的合并：如果有重复的键，就会被新的键对应的值所取代。但列表可以合并重复数据且不被替代。

dict1.update(dict2)
```python
d = {"a":1,"b":2,"c":"haha"}
f = {"a":8,"y":"OK"}
d["a"] = "a"
print (d)
>>>{"a":"a","b":2,"c":"haha"}
d["c"] = "hi"
print (d)
>>>{"a":"a","b":2,"c":"hi"}
del(d["b"])
print (d)
>>>{"a":"a","c":"hi"}
d.update(f)
print (d)
>>>{"a":8,"c":"hi","y":"OK"}
```
4、字符串处理

(1)字符串的转换：s = str(任意类型数据)

(2)字符串的合并：通过“+”，不同类型的数据无法合并，可先转化再合并
```python
a = 1
a = str(a)
b = "sss"
print (a + b)
>>>1sss
```
(3)字符串的截取，split(字符/字符串,分割次数)
```python
a = "a=abc,b=123,ccc,(1,2)"
print (a.split(","))
>>>['a=abc','b=123','ccc','(1','2)']
print (type(a.split(",")))
>>><class 'list'>
print (a.split(",")[2])
>>>'ccc'
print (a.split(",",2))
>>>['a=abc','b=123','ccc','(1,2)']
print (a.split(",")[0].split("=")[1])
>>>abc
print (a[3])
>>>b
```
(4)字符串的替换：replace(原字符串,替换的字符串,替换次数)
```python
a = "a=abc,b=123,ccc,(1,2)"
print (a.replace(',','and'))
>>>a=abcandb=123andcccand(1and2)
print (a.replace(',','and',2))
>>>a=abcandb=123andccc,(1,2)
```

