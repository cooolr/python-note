
### 0、标准序列操作（适用于字符串）
```
a. 索引            
>>>a=[1,2,3,4,5,6]
>>>a[3]
4
b. 分片            
>>>a=[1,2,3,4,5,6]
>>>a[1:4]
[2,3,4]
>>>a[:3]
[1,2,3]
>>>a[2:]
[3,4,5,6]
>>>a[:]
[1,2,3,4,5,6]
步长
>>>a[::2]
[1, 3, 5]
>>>a[::-2]
[6,4,2]
c. 乘法            
>>>a=[1,2,3]
>>>a*3
[1, 2, 3, 1, 2, 3, 1, 2, 3]
d. 判断成员资格     
>>>a=[1,2,3,4,5,6]
>>>5 in a
True
e. 求长度           
>>>a=[1,2,3,4,5,6]
>>>len(a)
6
f. 求最小值         
>>>a=[1,2,3,4,5,6]
>>>min(a)
1
g. 求最大值          
>>>a=[1,2,3,4,5,6]
>>>max(a)
6
```

### 基本的列表操作
```
分片赋值
>>>name=list('Perl')
>>>name[1:]=list('ython')
>>>''.join(name)
Python
>>>number=[1,5]
>>>number[1:1]=[2,3,4]
>>>number
[1,2,3,4,5]
```

### 1、列表的方法
```
append    #在列表末尾追加新的对象

count     #统计某个元素在列表中出现的次数

extend    #在列表末尾追加另一个列表的所有值
>>>a=[1,2,3]
>>>b=[4,5,6]
>>>a.extend(b)
>>>a
[1,2,3,4,5,6]

index     #从列表中找到某个值第一个匹配项的索引位置

insert    #将对象插入列表中
>>>a=[1,2,3,4,5,6]
>>>a.insert(3,'hello')
>>>a
[1,2,3,'hello',4,5,6]

pop       #移除列表中的一个元素，默认最后一个，并返回元素值
>>>a=[1,2,3,4,5,6]
>>>a.pop()
6
>>>a
[1,2,3,4,5]

remove    #移除列表中某个值的第一个匹配项
>>>a=['to','be','a','stupid','a']
>>>a.remove('a')
>>>a
['to','be','stupid','a']

reverse   #将列表中的元素反向存放
>>>a=[1,2,3,4,5,6]
>>>a.reverse()
>>>a
[6,5,4,3,2,1]

sort      #在原位置对列表进行排序
>>>a=[1,3，6，4，2，5]
>>>a.sort()
>>>a
[1,2,3,4,5,6]

sorted   #对列表排序产生新的列表(不是列表的方法，是内建函数)
>>>a=[1,3，6，4，2，5]
>>>b=sorted(a)
>>>a
[1,3，6，4，2，5]
>>>b
[1,2，3，4，5，6]

sort和sorted的区别

sort是列表的方法，sorted是内建函数
>>>a=[1,3，6，4，2，5]
>>>b=[1,3，6，4，2，5]
>>>x=a.sort()
>>>a
[1，2，3，4，5，6]
>>>x
None
>>>y=sorted(b)
>>>b
[1,3，6，4，2，5]
>>>x
[1，2，3，4，5，6]

高级排序  #元素按特定方式进行排序
可选参数：key和reverse
>>>a=['a','aaaa','aaa','aa']
>>>b=['a','aaaa','aaa','aa']
>>>a.sort(key=len)
>>>a
['a','aa','aaa','aaaa']
>>>b.sort(reverse=True)
>>>b
['aaaa', 'aaa', 'aa', 'a']

```

### 2、字符串格式化
```
格式化str
>>>a='hello %s'%'world'
格式化int
>>>a='number is %d'%20
格式化float
>>>a='number is %f'%20.1
格式化多个
>>>a='%s is %s'%('lr','cool')
字典格式化字符串
>>>a='%(name)s age is %(age)d'%{'name':'lr','age':18}

常用方式
>>>cu.execute("insert into test values(%s,%d)"%('lr',1234))
```

### 3、字段宽度和精度，符号、对齐和用0填充
```
转换说明符可以包括字段宽度和精度。
字段宽度是转换后的值所保留的最小字符个数，精度则是结构中应该包含的小数位数。
>>>'%10f'%3.14151111      #字段宽10
'    3.1415'
>>>'%10.2f'%3.1415    #字段宽10，精度2
'       3.14'
>>>'%.2f'%3.1415      #精度2
'3.14'

在字段宽度和精度值之前还可以放置一个“标志”，该标志可以使零、加号、减号或空格，零表示数字将会用0进行填充。
>>>'%010.2f'%3.1415   #字段宽10，精度2，不足10位用0补够
'0000003.14'
>>>'%-10.2f'%3.1415   #字段宽10，精度2，左对齐
'3.14      '

减号(-)用来左对齐
空白(' ')在正数前加上空格
加号(+)标识出正负符号

可以使用*作为字段宽度或者精度，数值会从元组参数中读出
>>>'%.*s'%(5,'Guido van Rossum')
```

### 4、字符串方法
```
find     #在一个较长的字符串中查找子串，返回子串所在位置的最左端索引
>>>a='hello world,haha python'
>>>a.find('haha')
12

join     #非常重要的字符串方法，split的逆方法，用来连接序列中的元素
>>>a=['1','2','3','4','5']
>>>'+'.join(a)
1+2+3+4+5
>>>b=['.','usr','bin','env']
>>>'/'.join(b)
'./usr/bin/env'

lower    #返回字符串的小写字母版
>>>'Hello World'.lower()
'hello world'

replace  #返回某字符串的所有匹配项均被替换后得到字符串
>>>'hello world'.replace('world','lr')
'hello lr'

split    #非常重要的字符串方法，join的逆方法，将字符串分割成序列
>>>'1+2+3+4+5'.split('+')
[1,2,3,4,5]

strip    #返回去除两侧（不包括内部）空格的字符串
>>>'      hello   world   '.strip()
'hello   world'

也可以指定需要去除的字符，将他们列为参数即可
>>>'***hello *** world!!! ***'.strip('*!')
'hello *** world'
```

### 字典
```
创建字典
>>>world={'lr':'cool'}
>>>items=[('name','Gumby'),('age',42)]
>>>dict(items)
{'age':42,'name':'Gumby'}
>>>dict(name='Gumby',age=42)  关键字参数

基本字典操作
len(d)   返回d中项（键-值对）的数量
d[k]     返回关联到键k上的值
d[k]=v   将值v关联到键k上
del d[k] 删除键为k的项
k in d   检查d中是否有含有键为k的项

字典方法
clear    清除字典中所有的项，原地操作
>>>x={1:1}
>>>x.clear()
>>>x
{}
copy     浅复制字典
>>>x={1:1}
>>>y=x.copy()

延伸深复制
>>>from copy import deepcopy
>>>y=deepcopy(x)

fromkeys  使用给定的键建立新的字典，每个键对应值默认none
>>>{}.fromkeys(['name','age'])
{'age':None,'name':None}
>>>dict.fromkeys(['name','age'])
{'age':None,'name':None}
```

### 5、断言
```
与其让程序在晚些时候崩溃，不如在错误条件出现的时候直接让他崩溃。
>>>a=3
>>>assert a == 3,'this is error'
```

### 6、列表推导式
```
>>>[i+1=2 for i in range(5)]
[0,1,2,3,4]
>>>[i+1 for i in range(5)]
[1,2,3,4,5]
>>>[i for i in range(5) if i < 3]
for i in range(5):
    if i<3:
         li.append(i)
>>>[0, 1, 2]
```

### 7、break、continue、pass
```
break : 立即跳出循环结构，转而执行该结构后面的语句
continue : 立即结束本次循环，重新开始下一轮循环
pass : 该语句什么也不做，也就是说它是一个空操作
```

### 8、阻塞和非阻塞、同步和异步
```
1. 阻塞和非阻塞是相对的。

1个程序单元来说，这一步要等待上一步执行完才能执行，这就是阻塞。而多个程序单元并发执行，就是非阻塞。
阻塞和非阻塞是相对不同单元、不同线程来说的。

2. 同步和异步是对做同一件事(IO)做比较的。

比如写100m文件进磁盘，cpu输出只要0.01s，但硬盘接收要10s，如果cpu干等处理完再运行下面的代码，就是同步。如果cpu不等待，直接执行下一步，就是异步，真正的异步几乎没有的。

阻塞和非阻塞是自身的状态，而同步和异步是与别人的关系。

常见设计模型有：
同步阻塞IO:最常见
同步非阻塞IO:并发
异步阻塞IO:没意义
异步非阻塞IO:很难，要借助第3方
```

### 9、关于python内存
```
>>>a=[1,2,3]
最常见的赋值，a是一个变量，一个名字，内存中的列表绑定到这个名字。
>>>a=123
当我重新对a赋值的时候，[1,2,3]这个列表就“漂”在内存里了，
Python解释器就会以他无穷的智慧直接删除了这个列表。
这种行为叫做垃圾收集。

还可以用del语句
>>>a=[1,2,3]
>>>del a
del会移除对一个对象（列表）的引用，并且会移除名字本身。
事实上，del只是删除了a这个名字，无法删除[1,2,3]这个列表，它会被python自动回收。
所以说，不需要过多考虑删除值的问题，python是没有办法删除值的，Python解释器会负责内存的回收。


>>>a=[1,2,3]
>>>b=a
>>>b.reverse()
>>>b
[3,2,1]
>>>a
[3,2,1]
是否会觉得奇怪，把a赋给b以后，修改了b，a也跟着变化了。
前面说了，a和b只是变量，绑定了内存里的[1,2,3]，
把a和[1,2,3]的绑定关系也赋给了b，那任意一个对[1,2,3]的操作都会指向变量。
>>>hex(id(a))
'0x269b548L'
>>>hex(id(b))
'0x269b548L'
对比一下a和b的内存地址都是一样的，都指向了内存中同一个列表

解决方法就是用切片新建一个副本
>>>a=[1,2,3]
>>>c=a[:]
>>>hex(id(a))
'0x269b548L'
>>>hex(id(c))
'0x2681048L'
```

### 10、命名空间、局部变量与全局变量
```
“黑暗魔法”：exec语句：执行字符串代码
>>>exec "print 'hello world'"
'hello world'
某些时候需要动态创建Python代码，然后将其作为语句执行或作为表达式计算，这可能近似于“黑暗魔法”------在此之前，一定要慎之又慎，仔细考虑。
因为无法确定栋其他地方获取的字符串代码是否安全。
一旦出错，整个程序都会崩溃。

所以要引入命名空间，又叫作用域，命名空间是一个不可见的字典。
>>>space={}
>>>a=[1,2,3]
>>>exec "a=[1,2,3,4,5]" in space
>>>space['a']
[1,2,3,4,5]
>>>a
[1,2,3]

作用域可以看成一个独立的封闭空间，潜在的破坏性代码在里面运行并不会覆盖外面的变量，exec赋值的变量a只在他的作用域内有效。

每个函数调用时都会创建一个新的作用域，函数的语句只在内部作用域内有效，这就是局部变量的由来。

全局变量就是在全局作用域下。
```

### 11、参数魔法
```
调用函数时传参数有两种方式。
第一种叫位置参数
>>>def test(a,b,c):print a,b,c
>>>test(1,2,3)
1,2,3
传递参数按在函数定义的位置一个接着一个来，位置比名字重要

第二种叫关键字参数
>>>def test(a,b,c):print a,b,c
>>>test(a=1,b=2,c=3)
1,2,3
关键字参数在很多参数时就非常有用了。程序规模越大，它的作用就越大

函数还可以设置参数默认值
>>>def test(a=None,b=None,c=None):print a,b,c
>>>test(1,2,3)
123
>>>def test(a,b=None,c=None):print a,b,c
位置参数还可以和关键字参数一起来用，位置参数在前就行了
```