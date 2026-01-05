# <font face="楷体" color=purple >Python Basic</font>

####  一、基本语句

-   输入函数: X=input('***')，引出eval函数,即转为对应数据类型
    >   x为字符串类型 ，变量=eval(input('xxx'))
    
- 注释：#             多行注释：'''    '''

- 复数数值类型：实数部分.real、虚数部分.imag

    >   x=123+456j

-   转义字符：\n、\t

-   布尔类型：True(1)、False(0)

    >   bool()、type()

-   算术运算符：//整除、%取余、**幂

-   逻辑运算符：and、or、not

-   位运算符：与&、或|、异或^、取反~

-   if语句

    ```python
    if 表达式:
    	pass
    else:
        pass
    ---------------------------
    if 表达式1:
        pass
    elif 表达式2:
        pass
    else:
        pass
    ```
    
- 模式匹配match（同c#中switch）

    ```python
    match score:
        case 'a':
            print('good')
        case 'b':
            print('ok')  
    ```

-   for循环
	- range()函数，产生一个[n,m)整数序列
    ```python
    for i in range(1,11):
        pass
    --------------------
    for i in range():
    	pass
    else:
        pass
    ```

-   whlie循环

    ```python
    while 表达式:
        pass
    else:
        pass
    ```

-   break、continue

-   **编码**
	
	- ASCII:127个字符，大小写英文字母、数字和一些符号
	
	- GB2313:中文可显示
	
	- UTF-8：整合
	
	- ```python
	    #!/usr/bin/env python3
	    # -*- coding: utf-8 -*-
	    ```
	
	    第一行注释是为了告诉Linux/OS X系统，这是一个Python可执行程序，Windows系统会忽略这个注释；
	
	    第二行注释是为了告诉Python解释器，按照UTF-8编码读取源代码，否则，你在源代码中写的中文输出可能会有乱码。

#### 二、组合数据类型

##### 1.序列

-   索引：N个元素，正向递增（0，N-1），反向递减（-N，-1）
-   切片：<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241020193030372.png" alt="image-20241020193030372" style="zoom: 50%;" />

>   eg:s1=[0,5,2]

-   序列函数操作：<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241020193350919.png" alt="image-20241020193350919" style="zoom: 67%;" />

##### 2.列表

-   定义：list1=[1,2,3.5,'hello']

-   list函数操作：<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241020193721892.png" alt="image-20241020193721892" style="zoom: 50%;" />

    -   遍历函数 **enumerate()**

        ```python
        for index,item in enumerate(lst,start=1) #start可删除，默认index从0开始
        	print(index,item)
        ```
        
        

-   生成式：lst=[expression **for** item **in** range **if** condition]

-   二维列表

    ```python
    lst=[
         ['a','b'],
         [1,2],
         [1.1,2.2]
        ]
    for row in lst:
        for item in row:
            pass
    ```

##### 3.元组

-   定义：tuple=(1,2,3)

##### 4.字典(键值对)

-   直接定义：dict={key1:value2,key2:value2}
-   映射定义：zip(lst1,lst2)

##### 5.集合

-   定义：set={1,2,3}
-   操作符类型：<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241020195451237.png" alt="image-20241020195451237" style="zoom:50%;" />

```python
A={1,2,3}
B={5,2,3}
print(A&B)
```

##### 6.总结

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241020195831010.png" alt="image-20241020195831010" style="zoom: 50%;" />

##### 7.切片

-   L[:3],L[1:5],L[1:],L[1:9:3]

#### 三、字符串操作

##### 1.常用函数

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241028200333579.png" alt="image-20241028200333579" style="zoom:50%;" />

##### 2.1格式化字符串

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241028200421674.png" alt="image-20241028200421674" style="zoom:50%;" />

```python
name=lg
age=21
score=99.9
print('姓名：%s,年龄:%d,成绩:%.1f' %(name,age,score))
print(f'姓名:{name},年龄:{age},成绩:{score}')
print('姓名:{0},年龄:{1},成绩:{2}'.format(name,age,score))
```

##### 2.2 格式化字符串详细形式

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241028200959860.png" alt="image-20241028200959860" style="zoom:50%;" />

```python
s='helloworld'
print('{0:*<20}'.format(S)) #字符串宽度20，左对齐，空白部分用*代替
print('{0:,}'.format(987654.321)) #千位分隔符
print('{0:.2f}'.format(3.1415926))
print('{0:.5}'.format('serious'))
print('{0:.2%}'.format(321.1))
print('hello,{0},score improve {1:.2f}'.format('gz',3.569))
```

##### 2.3 原始字符串`r`

-   `r` 前缀用于创建**原始字符串（Raw String）**。原始字符串的主要特性是，**它会忽略字符串中的转义字符**，即不会将反斜杠 `\` 作为转义符来处理，而是直接将其作为普通字符进行处理。
-   常用于*正则表达式*、文件路径

#### 四、Pycharm调试方法介绍

##### 1.常见错误类型

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241030165722985.png" alt="image-20241030165722985" style="zoom: 50%;" />

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241030165747478.png" alt="image-20241030165747478" style="zoom:50%;" />

##### 2.调试步骤

-   设置断点

-   点调试按钮进入Debug

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241030165912354.png" alt="image-20241030165912354" style="zoom: 67%;" />

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241030165935462.png" alt="image-20241030165935462" style="zoom: 67%;" />

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241030170001411.png" alt="image-20241030170001411" style="zoom:67%;" />

#### 五、函数

##### 1.定义与调用

-   使用关键词def

-   参数传递
	-    位置参数：顺序与定义的顺序相同
	
	-    关键字参数：使用“形参=值”传参，可顺序不同
	
	-    默认值参数
	
	- 	可变参数
		- 个数可变的**位置参数**：在参数前加**一颗星（*para）**，放到元组中
		
		- 个数可变的**关键字参数**：在参数前加**两颗星（\**para）**，放到字典中
		
		- ```python
		    def fun(*args):
		        print(type(para))
		        for i in para:
		            print(i)
		    
		    fun(1,2,3)
		    fun([1,3,5])
		    s=[6,7,8]
		    fun(*s)     #在参数前加一颗星，将列表进行解包
		    ```
		
		- ```python
		    def fun2(**kw):
		        print(type(kvpara))
		        for key,value in kvpara.items():
		            print(key,'----',value)
		    
		    fun2(name='rained',age=21,height=178)
		    d={'name':'rained','age':21,'height':178}
		    fun2(**d)
		    ```
		

-   返回值（return）用法

    ```python
    ###一个返回值
    def cal(a,b):
        s=a+b
        return s
    print('-'*10)
    gets=cal(1,2)
    print(gets)
    get2=cal(cal(1,2),3)
    print(get2)
    ```

    ```python
    ###多个返回值
    def get_sum(j):
        s=0
        odd_sum=0
        even_sum=0
        for i in range(1,j+1):
            if i%2==0:
                odd_sum+=i
            else:
                even_sum+=i
            s+=i
        return odd_sum,even_sum,s
    q,w,e=get_sum(10)
    print(q,'\n',w,'\n',e,sep='')
    ```

##### 2.作用域

-   全局变量：global关键字修饰
-   局部变量

##### 3.匿名与递归

-   匿名函数：lambda

```python
f=lambda a,b:a+b
print(type(f))
print(f(10,20))
```

-   递归：如斐波那契数列

##### 4.常见的内置函数

-   类型转换函数

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241030212442476.png" alt="image-20241030212442476" style="zoom:50%;" />

-   数学函数

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241030212505557.png" alt="image-20241030212505557" style="zoom:50%;" />

-   迭代器操作函数

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241030212551374.png" alt="image-20241030212551374" style="zoom:50%;" />

```python
###filter用法
def fun3(num3):
    return num3%2==1
obj=filter(fun3,range(10))
print(list(obj))
###map用法
def upper(x):
    return x.upper()
new_lst=['hello','world']
obj2=map(upper,new_lst)
print(list(obj2))
```

-   其他内置函数

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241030212708733.png" alt="image-20241030212708733" style="zoom:50%;" />

##### 5.函数式编程

###### i.高阶函数

-   `map`用于将一个函数作用于一个序列，以此得到另一个序列；

    `reduce`用于将一个函数依次作用于上次计算的结果和序列的下一个元素，以此得到最终结果。

- `filter()`的作用是从一个序列中筛出符合条件的元素。由于`filter()`使用了惰性计算，所以只有在取`filter()`结果的时候，才会真正筛选并每次返回下一个筛出的元素。

- `sorted()`也是一个高阶函数。用`sorted()`排序的关键在于实现一个映射函数。

#### 六、面向对象编程OOP

##### 1.过程与对象

-   面向过程：**功能**上的封装，如:C#
-   面向对象：**属性和行为**上的封装，如：Python，Java

##### 2.类和对象

-   类：**class** 类名():
-   对象：对象名=类名()

-   类的组成：属性就是变量，方法就是函数
	-   类属性
	-   实例属性
	-   实例方法
	-   静态方法：@staticmethod
	-   类方法：@classmethod
	-   动态绑定

```python
class Student:
    #类属性
    school='XDU'
    #初始方法
    def __init__(self,xm,age):  #xm,age是局部变量
        self.name=xm    #左侧是实例属性
        self.age=age
    #定义在类中的函数称方法
    def show(self):
        print(f'my name is {self.name},today {self.age}')
    #静态方法
    @staticmethod
    def sm():
        print('这是一个静态方法，不能调用实例属性和实例方法')
    @classmethod
    def cm(cls):
        print('这是一个类方法，不能调用实例属性和实例方法')

#创建类的对象
stu=Student('lg',21)
#实例属性，使用对象名打点调用
print(stu.name,stu.age)
#类属性，使用类名打点调用
print(Student.school)
#实例方法，使用对象名打点调用
stu.show()
#类放法，@classmethod修饰
Student.cm()
#静态放法，@staticmethod修饰
Student.sm()

#动态绑定属性和方法
stu.gender='female'
print(stu.gender)
def introduce():
    print('普通函数被动态绑定为stu对象的方法')
stu.fun=introduce

```

##### 3.三大特征

-   **封装**：隐藏内部细节，权限控制
	- 单下划线开头：受保护可访问
	- 双下划线开头：私有
	- 首位双下划线：特殊方法，如：\__init__

```python
self._protect=xm #本类和子类访问
self.__private=age#类本身访问
def _fun1(self):
def __fun2(self):
#访问
stu._Student__private
stu._Student__fun2()
#属性设置
@property
def gender(self):
    return self.__gender
@property.setter
def gender(self,value):
    pass
```

-   **继承**：子类继承父类
	>   class 类名(父类1，父类2……)：
	- 单继承
	- 多继承
	- 方法重写

```python
#单继承
class Doctor(Student):
    #初始化
    def __init__(self,name,age,department):
        super().__init__(name,age) 	#使用super
        self.department=department
    #方法重写
    def show(self):
        super().show()
        print(f'我的部门是{self.department}')

doctor=Doctor('xxx',20,'EXTERN')
doctor.show()

#多继承MixIn
class Dog(Mammal, RunnableMixIn, CarnivorousMixIn):
    pass
class Son(FatherA,FatherB):
    def __init__(self,age,name,gender):
        FatherA.__init__(self,name)
        FatherB.__init__(self,age)
        self.gender=gender
```

-   **多态**：只关心对象的方法，即“多种形态”

```python
class Cat():
    def eat(self):
        print('like fish')
class Dog():
    def eat(self):
        print('like bone')
def fun(obj):
    obj.eat()
cat=Cat()
dog=Dog()
fun(cat)
fun(dog)
```

-   类的浅拷贝与深拷贝：改变对象与实例属性地址，了解

##### 4.面向对象高级编程

-   \__slots__
-   `@property`装饰器,负责把一个方法变成属性调用,其本身又创建了另一个装饰器`@score.setter`

#### 七、模块

##### 1.模块简介与导入

-   命名时要求全部小写，下划线分割，如：hello.py

-   导入两种方式
	- import name  (as 别名)
	- from name import 变量/函数/类

##### 2.包

-   含有\__init__.py文件的文件夹，导入包时会自动执行内部代码

-   调用方式

    ```python
    #admin为包，hello2为模块，info为模块中函数
    import admin.hello2 as h
    h.info()
    from admin import hello2 as k
    k.info()
    from admin.hello2 import info
    info()
    ```

##### 3.常用内置模块

###### i.random

-   用于产生随机数的标准库

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241104193812389.png" alt="image-20241104193812389" style="zoom:50%;" />

```python
import random
random.seed(10) #此行代码作用为生成同一个随机数，不添加此后每次运行结果随机
a=random.random()
print(random.randint(1,100))
```

###### ii. time

-   用于处理时间的标准库

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241104194705192.png" alt="image-20241104194705192" style="zoom:50%;" />

```python
import time
print(time.localtime())
print(time.ctime())
print(time.strftime('%Y-%m-%d',time.localtime()))
```

###### iii.datetime

-   显示日期和日期运算等操作

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241104195309434.png" alt="image-20241104195309434" style="zoom: 67%;" />

```python
from datetime import datetime
print('系统时间为：',datetime.now())
```

##### 4.第三方模块

###### i.安装

-   pycharm终端、cmd命令、pycharm设置三种安装方式

-   安装：pip install *name*

-   镜像源
	- **pip --default-timeout=100 install *模块名称* -i http://pypi.doubanio.com/simple/ --trusted-host pypi.doubanio.com**
	- 清华：https://pypi.tuna.tsinghua.edu.cn/simple
	- 阿里云：http://mirrors.aliyun.com/pypi/simple/
	- 中国科技大学：https://pypi.mirrors.ustc.edu.cn/simple/
	- 华中科技大学：http://pypi.hustunique.com/

-   卸载：pip uninstall *name*

-   **pip升级：python -m pip install --upgrade pip**

###### ii.requests

-   用于爬虫，处理HTTP请求，get()打开网页请求等

###### iii.openpyxl

-   用于处理Excel文件，对其数据进行写入读取等

###### iv.pdfplumber

-   用于从PDF读取内容

###### v.Numpy

-   用于数据分析，处理数组、矩阵等数据

###### vi. Pandas与Matplotlib

-   数据可视化

###### vii.PIL

-   安装pillow，用于图像处理
#### 八、文件

-   step
	- 变量名=open(filename,mode,encoding)
	- 变量名.read()/变量名.write(s)
	- 变量名.close()

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241105175008341.png" alt="image-20241105175008341" style="zoom:50%;" />

-   with语句：语句执行完毕后自动关闭已打开的文件

```python
f = open('/Users/michael/test.txt', 'r')
f.read()
f.close()
#等价于
with open(r'/path/to/file', 'r') as f:
    print(f.read())
```

-   内置模块os，用于文件相关操作

#### 九、进程和线程

-   对于操作系统来说，一个任务就是一个进程（Process），把进程内的这些“子任务”称为线程（Thread）

-   多任务的实现有3种方式
	- 多进程模式
	- 多线程模式
	- 多进程+多线程模式

#### 十、正则表达式

-   正则表达式是用来匹配字符串。它的设计思想是用一种描述性的语言来给字符串定义一个规则，凡是符合规则的字符串，我们就认为它“匹配”了，否则，该字符串就是不合法的。

-   **元字符**：即为有特定含义的字符

    | 代码 |                        说明                         |
    | :--- | :-------------------------------------------------: |
    | .    | 匹配除换行符以外的**任意字符**，如1，n，*，+，- ,等 |
    | \w   |         匹配**字母或数字**，或下划线或汉字          |
    | \s   |                 匹配任意的**空格**                  |
    | \d   |                    匹配**数字**                     |
    | \b   |                匹配单词的开始或结束                 |
    | ^    |                匹配字符串的**开始**                 |
    | $    |                匹配字符串的**结束**                 |

-   **反义字符**：多用于查找除某个字符以外其他任意字符均可以的情况

|   代码   |                    说明                    |
| :------: | :----------------------------------------: |
|    \W    | 匹配任意不是字母，数字，下划线，汉字的字符 |
|    \S    |          匹配任意不是空白符的字符          |
|    \D    |            匹配任意非数字的字符            |
|    \B    |        匹配不是单词开头或结束的位置        |
|   [^x]   |          匹配除了x以外的任意字符           |
| [^aeiou] |   匹配除了aeiou这几个字母以外的任意字符    |

-   **限定字符**：多用于重复匹配次数

| 代码  |      说明       |
| :---: | :-------------: |
|   *   |  重复0或更多次  |
|   +   |  重复1或更多次  |
|   ?   |    重复0或1     |
|  {n}  |     重复n次     |
| {n,}  | 重复n次或更多次 |
| {n,m} |   重复n到m次    |
|分组()|m.group(n),group(0)是与整个正则表达式相匹配的字符串，group(1)、group(2)表示第1、2个|

-   **常用的实用正则表达式**

	只能输入数字：^[0-9]*$。

　　只能输入n位的数字：^\d{n}$。

　　只能输入至少n位的数字：^d{n,}$。

　　只能输入m~n位的数字：^d{m,n}$

　　只能输入零和非零开头的数字：^(0|[1-9][0-9]*)$

　　只能输入有两位小数的正实数：^[0-9]+(.[0-9]{2})?$

　　只能输入有1~3位小数的正实数：^[0-9]+(.[0-9]{1,3})?$

　　只能输入非零的正整数：^+?[1-9][0-9]*$

　　只能输入非零的负整数：^-[1-9][]0-9*$

　　只能输入汉字：^["u4e00-"u9fa5]{0,}$

-   内置模块`re`
	
	|           函数           |             说明             |
	| :----------------------: | :--------------------------: |
	| re.match(pattern,string) | 从起始位置匹配符合的第一个值 |
	|      re.search(p,s)      |      搜索第一个匹配的值      |
	|          re.sub          |             替换             |
	|         re.split         |             分割             |

```python
import re
test = '用户输入的字符串'
if re.match(r'正则表达式', test):
    print('ok')
    a=match.group(0)
else:
    print('failed')
```

# <font face="楷体" color=purple >Python数据分析</font>

#### 一、NumPy基础

-   处理**数组**等运算`import numpy as np`

-   ndarray其元素类型相同，可通过`a.shape`和`a.dtype`查看**维度**和**数据类型**，`a.astype`将数组转为对应数据类型

-   | 代码                                     |                             说明                             |
    | :--------------------------------------- | :----------------------------------------------------------: |
    | np.array(object, dtype=None, copy=True)  |                     将对象转为NumPy数组                      |
    | **np.arange(start, stop, step, dtype=None)** | 返回一个范围从 `start` 到 `stop`（不包括 `stop`）的数组，步长为 `step` |
    | **np.arange(x).reshape(d0,d1...)** | 按几行几列生成 |
    | np.ones(shape, dtype=None)               |         创建一个填充了 `1` 的数组,eg:np.ones((2, 3))         |
    | np.full(shape, fill_value, dtype=None)   |  np.full((2, 3), 7)  # 输出：array([[7, 7, 7], [7, 7, 7]])   |
    |np.where(condition, x, y)|根据 `condition`，选择(替换原数组)输出 `x` 或 `y` 中的值。若条件为真，则取 `x` 的值，否则取 `y` 的值|
    |np.sign(x)|返回数组中每个元素的符号，>0则返回 1，=0则返回 0，<0则返回 -1|
-   <img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241112212157797.png" alt="image-20241112212157797" style="zoom:67%;" />

-   <img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241112212631387.png" alt="image-20241112212631387" style="zoom:67%;" />

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241112212724594.png" alt="image-20241112212724594" style="zoom:67%;" />

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241112212851044.png" alt="image-20241112212851044" style="zoom:67%;" />

-   两种用法如：`arr.mean()`等价于`np.mean(arr)`

-   <img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241112213259578.png" alt="image-20241112213259578" style="zoom:67%;" />

-   <img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241112213616863.png" alt="image-20241112213616863" style="zoom:67%;" />

-   数组文件输入输出：`np.save`、`np.load`、`np.savez`

-   <img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241112214001352.png" alt="image-20241112214001352" style="zoom:67%;" />

-   | 代码 np.random.x                                  |                             说明                             |
    | :------------------------------------------------ | :----------------------------------------------------------: |
    | seed(seed)                                        |     设置随机数生成器的种子，确保每次生成的随机数序列相同     |
    | shuffle(x)                                        |               将输入数组 `x` 进行原地随机打乱                |
    | ==randint(low, high=None, size=None, dtype=int)== | 从指定的**整数**区间 `[low, high)` 中生成,如果 `size` 被指定，返回一个具有该形状的数组，如果不提供 `high`，那么它生成 `[0, low)` 之间的随机整数 |
    | ==randn(d0, d1, ..., dn)/rand()#均匀分布==        | 从标准**正态分布**（均值为 0，标准差为 1）中随机抽取，eg：randn(2, 3)\# 生成一个 2x3 的数组 |
    | normal(loc=0.0, scale=1.0, size=None)             | 从正态分布（高斯分布）中生成随机数,`loc` 是分布的均值，`scale` 是标准差 |

#### 二、pandas基础

-   两个主要数据结构
    -   **Series**：由一组数据（NumPy数据类型）以及一组与之相关的数据标签（即索引）组成
    -   **DataFrame**：表格型的数据结构,行和列都有标签,最常用的一种是直接传入一个由等长列表或NumPy数组组成的字典

-   **NaN**：即“非数字”（not a number）

-   
    | 代码                                            | 说明                                                         |
    | :---------------------------------------------- | :----------------------------------------------------------- |
    | pd.Series(data, index, name)                    | **data**：数据，接受列表、字典、NumPy 数组等;**index**：指定索引标签 |
    | pd.DataFrame(data, index, columns, dtype, copy) | **index**：指定**行**索引标签,默认是0,1,2;**columns**：指定**列**标签，会自动从字典的键推断 |
    | x.loc(row,col,axis)                             | 标签索引的访问器,标签列表切片等，axis默认为1                 |
    | x.iloc(row,col)                                 | 位置索引的访问器，整数列表切片等                             |
    | obj.reindex(labels,axis,method,fill_value)      | **labels**：新的索引标签;**axis**默认为 0;**method**：处理缺失值的方式,可选‘ffill’向前填充（使用前一个有效值填充）、‘bfill’向后填充、‘None’不填充；**fill_value**：指定填充缺失值时使用的值，默认 NaN |
    | obj.drop(labels,axis,inplace)                   | 用于删除指定行或列的函数,axis默认为0                         |
    | obj.sort_index(axis,ascending)                  | 用于按索引排序,**ascending**：指定排序顺序。默认值为 True，表示升序 |

```python
#Series
ser = pd.Series([10, 20, 30], index=['a', 'b', 'c'])
#DataFrame
df = pd.DataFrame({'Name': ['Alice', 'Bob', 'Charlie'], 'Age': [25, 30, 35]}, index=['a', 'b', 'c'])
#loc
df.loc['b','Age'] 	#30
#iloc
df.iloc[1,1]  #30
#axis
arr = np.array([[1, 2, 3],
                [4, 5, 6],
                [7, 8, 9]])
np.sum(arr, axis=0)  #array([12, 15, 18])
np.sum(arr, axis=1)  #array([6, 15, 24])
#reindex
result = ser.reindex(['a', 'b', 'd'], fill_value=0) #10，20，0
```

-   关于**axis**：轴/维度
    -   axis=0 代表**沿着行的方向**操作，也就是按列来进行操作**（垂直方向）**
    -   axis=1代表 **沿着列的方向**操作，也就是按行来进行操作**（水平方向）**

-   <img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241113211252716.png" alt="image-20241113211252716" style="zoom: 67%;" />

#### 三、数据访问

-   **pd.read_csv、pd.read_table**:从文件、URL等加载数据，常用参数如下
    
	-   **file**:文件路径或类文件对象
		
		> df=pd.read_csv('data.csv')
		
	-   **sep**:分隔符，默认为逗号
		
		>  df=pd.read_csv('data.csv',sep='\t')
	
	-   **header**:指定列名的行，默认为0
	
	    > df=pd.read_csv('data.csv',header=1)
	
	
	-   **index_col**：将指定的列设置为索引
	
	    >  df=pd.read_csv('data.csv',index_col=0)
	
	-   **usecols**：选择需要读取的列
	
	    > df=pd.read_csv('data.csv',usecols=['col1', 'col3'])
	
	
	-   **dtype**：指定列的数据类型
	
	    >  df=pd.read_csv('data.csv',dtype={'col1': float, 'col2': int})
	
	-   **skiprows**：跳过指定的行数
	
	    > df=pd.read_csv('data.csv',skiprows=2) #调过前两行
	
	
	-   **nrows**：读取指定的前n行
	
	    >  df=pd.read_csv('data.csv',nrows=100)

-   **JSON数据**：结构是基于两种基本数据类型的组合，即键值对，使用python进行数据解析

    ```python
    import json
    json_data = 
    {
      "name": "John Doe",
      "age": 30,
      "is_student": false,
      "courses": ["Math", "Science", "History"]
    }
    # 解析 JSON 数据,转为python形式
    data = json.loads(json_data)
    #转为JSON
    asjson = json.dumps(data)
    ```

-   **XML与HTML**：可扩展标记语言与超文本标记语言

    -   pd.read_html函数(需要按照`lxml`库)自动将HTML文件中的表格解析为DataFrame对象
    -   getroot得到该XML文件

-   二进制数据格式、HDF5格式、读取Excel文件

#### 四、数据清洗

-   | 代码                | 说明                                                         |
    | :------------------ | :----------------------------------------------------------- |
    | x.isnull()          | 返回一个布尔型的 DataFrame 或 Series，表示原数据中每个元素是否为 `NaN` |
    | x.dropna()          | 删除包含 `NaN` 的行或列                                      |
    | x.fillna(value,)    | 用指定的值填充 `NaN`                                         |
    | x.drop_duplicates() | 去除重复的元素/行                                            |
    | x.map(arg)          | 对 Series 中的每个元素进行映射（通常用字典或函数）,`arg`：字典、Series 或函数 |
    | x.describe()        | 输出统计摘要                                                 |

-   **离散化和面元划分函数**

    | 代码                                  | 说明                                                         |
    | :------------------------------------ | :----------------------------------------------------------- |
    | pd.cut(x,bins,right,labels,precision) | 将数据分配到指定的区间中,`x`: 输入的数据;`bins`: 定义区间的数量或者区间的边界。可以是整数（指定分成的区间数）或者是一个数组（指定区间的边界）;`right`: 布尔值，是否包含区间的右边界，默认为 `True`，即右边界闭区间;`labels`: 用于为每个区间指定标签;`precision`: 用于定义边界值的小数精度 |
    | pd.value_counts(x)                    | 返回一个序列，表示每个唯一值的出现次数                       |
    | pd.qcut(x,q,labels,precison)          | 将数据分为**等频**区间，每个区间包含相同数量的数据;`q`: 区间数或者区间的分位数列表。可以指定分为多少个区间，或者是一个数组，表示各个分位点 |

-   **计算指标矩阵**

	| 函数                        | 说明                                                         |
| :-------------------------- | :----------------------------------------------------------- |
| pd.get_dummies(data,prefix) | 将一个类别型的变量转换为虚拟变量（也称为独热编码），适用于将分类数据转换为数值数据的情况，通常用于机器学习模型中的数据预处理;`prefix`：用于新列的前缀，默认会使用列名 |

#### 五、数据规整

-   **层次化索引**：使能在一个轴上拥有多个（两个以上）索引级别

-   `unstack()` 方法将 `Series` 对象的内层索引转为列，外层索引保持不变

-   **`swaplevel()`**: 用于交换 MultiIndex 的层级。
-   **`unstack()`**: 用于将 DataFrame 的行索引转换为列索引。
-   **`merge()`**: 类似于 SQL 中的 JOIN 操作，将两个 DataFrame 根据某一列进行合并。
    -   pandas.merge(left, right, how='inner', on=None, left_on=None, right_on=None, left_index=False, right_index=False, sort=True, suffixes=('_x', '_y'), copy=True, indicator=False)
    -   `'inner'`：默认，表示只保留两个表中都有的行（交集）。
    -   `'outer'`：保留两个表中的所有行（并集），缺失的地方填充 NaN。
    -   `'left'`：保留左表的所有行，右表中没有匹配的行会用 NaN 填充。
    -   `'right'`：保留右表的所有行，左表中没有匹配的行会用 NaN 填充。
-   **`concat()`**: 用于沿某一轴（行或列）连接多个 DataFrame。
-   **`stack()`**: 用于将 DataFrame 的列索引转换为行索引。

-   多层索引的原则: 一定要从最外层索引往内层走,多层索引建议括号括起来
-   行索引推荐使用`loc()`函数

####  六、Matplotlib绘图

-   `plot([x], y, [fmt], [x2], y2, [fmt2], …, **kwargs)`

    -   **[fmt] = \[color]\[marker][linestyle]**,即颜色(color)、点型(marker)、线型(linestyle)

    -   ***\*kwargs参数**
        -   x: x轴数据
        -   y: y轴数据
        -   linewidth: 线宽
        -   color:线条颜色
        -   lable：图例

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241119195313940.png" alt="image-20241119195313940" style="zoom:67%;" />

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241119195335594.png" alt="image-20241119195335594" style="zoom:67%;" />

<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241119195403008.png" alt="image-20241119195403008" style="zoom:67%;" />

-   **给一些特殊点加注释**`scatter(x, y, s=None, c=None, marker=None, cmap=None, norm=None, vmin=None, vmax=None, alpha=None, linewidths=None, verts=None, edgecolors=None, hold=None, data=None, **kwargs)`


-   | 方法                      | 意义                                                         |
    | ------------------------- | ------------------------------------------------------------ |
    | plt.xlim()/plt.ylim()     | x,y轴刻度取值范围(输入两个数值或者一些常用函数如max(x))      |
    | plt.xticks()/plt.yticks() | x,y轴刻度的标签值(输入两个列表，分别对应默认标签名称和更改后的标签名称) |
    | plt.xlabel()/plt.ylabel() | x,y轴的标题                                                  |
    | plt.title()               | 整个图表的标题(可以传入参数fontsize改变标题字体大小)         |
    | plt.legend()              | 设置图例(必须传入参数loc=’best‘或者其他位置来设置图例放置的位置，前提是在plt.plot()中设置了标签(label=)才可以使用) |
    | plt.grid()                | 设置网格线，输入一个布尔型的值，默认为False                  |
    | plt.savefig()             | 将图片保存到路径；fomat：png,pdf,svg...                      |

    | 方法                                      | 意义                                                         |
    | ----------------------------------------- | ------------------------------------------------------------ |
    | ax.set_xlim()/ax.set_ylim()               | x,y轴刻度取值范围(输入两个数值或者一些常用函数如max(x))      |
    | ax.set_xticklabels()/ax.set_yticklabels() | x,y轴刻度的标签值(输入两个列表，分别对应默认标签名称和更改后的标签名称,还可以输入参数rotation改变标签角度) |
    | ax.set_xlabel()/ax.set_ylabel()           | x,y轴的标题                                                  |
    | ax.set_title()                            | 整个图表的标题(可以传入参数fontsize改变标题字体大小)         |
    | ax.legend()                               | 设置图例(必须传入参数loc=’best‘或者其他位置来设置图例放置的位置，前提是在ax.plot()中设置了标签(label=)才可以使用) |
    | ax.grid()                                 | 设置网格线，输入一个布尔型的值，默认为False                  |

```python
import numpy as np
import matplotlib.pyplot as plt
# from pylab import *
# plt.rcParams['font.sans-serif'] = ['SimHei'] #网上搜索可以设置中文编码的方法，但不成功
# plt.rcParams['axes.unicode_minus'] = False

# 定义数据部分
x = np.arange(0.0, 10, 0.2) #设置一个从0到10，每隔0.2取一个数的array
y1 = np.cos(x)
y2 = np.sin(x)
y3 = np.sqrt(x)

# 绘制基本曲线(color为曲线颜色，linewidth为曲线宽度，linestyle为曲线样式（详见line_style.png），
# marker为曲线里面每一个数据点的样式（详见marks.png），label为该曲线的标签（声明之后在下面设置图例里面引用）)
plt.plot(x, y1, color='red', linewidth=1.5, linestyle='-', marker='.',label='cos(x)')
plt.plot(x, y2, color='blue', linewidth=1.5, linestyle='--', marker='.',label='sin(x)')
plt.plot(x, y3, color='green', linewidth=1.5, linestyle='-.', marker='.',label='sqrt(x)')

# 设置x，y轴的刻度取值范围
plt.xlim(-1, x.max() * 1.1)
plt.ylim(-1.5,4.0)
#设置x，y轴的刻度标签值
plt.xticks([0,2,4,6,8,10],['0',r'two',r'four',r'six',r'eight',r'ten'])
plt.yticks([-1,0,1,2,3,4,5],[r'-one',r'zero',r'one',r'two',r'three',r'four',r'five'])
#设置标题
plt.title('function of cos(),sin(),sqrt()',fontsize=19)#fontsize为标题大小
plt.xlabel('x')
plt.ylabel('y=f(x)')
#设置图例
plt.legend(loc='best')#前提是在plt.plot函数中指明了标签(label=)才可以使用
#设置网格线
plt.grid(True)#默认为无
#保存为图片
# plt.savefig('./data/image.png',dpi=120)#dpi为图片像素

#显示统计图
plt.show()
```

-   ```python
    #开始作图
    fig = plt.figure(figsize=(12,8))#创建figure对象,可以设置显示的图框的长宽
    ax1 = fig.add_subplot(1,2,1)#添加子图，按一行两列显示，第三个参数为放置位置
    ax2 = fig.add_subplot(1,2,2)
    
    ax1.plot(data['dteday'],data['temp'],color = 'black',label='y=f(x)')
    ax1.set_xticklabels(data['dteday'],rotation=45) #设置x轴的标签值，角度为45度
    ax1.set_xlabel('day')
    ax1.set_ylabel('temp')
    ax1.set_title('About day and temp 1')
    ax1.legend(loc='best')
    ax1.grid(True)
    
    ax2.plot(data['dteday'],data['temp'],color = 'black',label='y=f(x)')
    # ax2.set_xlim(min(data['dteday'])*2,max(data['dteday'])*2) #日期不能使用max和min函数
    ax2.set_ylim(min(data['temp'])-0.5,max(data['temp'])+0.5)
    ax2.set_xticklabels(data['dteday'],rotation=45)
    ax2.set_xlabel('day')
    ax2.set_ylabel('temp')
    ax2.set_title('About day and temp 2')
    ax2.legend(loc='best')
    ```

-   常用图形函数

    -   **ax.scatter()散点图**	
    -   **plot.bar()和plot.barh()分别绘制水平和垂直的柱状图**
    -   **plot.hist()直方图**
    -   **plot.density()密度图**


<img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20241119203130222.png" alt="image-20241119203130222" style="zoom:67%;" />

```python
#创建图
fig = plt.figure()  # an empty figure with no Axes
fig, ax = plt.subplots()  # a figure with a single Axes
fig, axs = plt.subplots(2, 2)  # a figure with a 2x2 grid of Axes
```

-   [快速入门指南_Matplotlib 中文网](https://www.matplotlib.net/stable/tutorials/introductory/quick_start.html)

#### 七、数据聚合与分组

-   `groupby` 主要有三个步骤：
    1.  **分组**：根据某些列对数据进行分组。
    2.  **应用**：对每个分组进行操作，例如聚合、变换或过滤。
    3.  **合并**：将操作后的结果合并回一个新的 `DataFrame` 或 `Series`。

-   **在groupby之后的一系列操作（如agg、apply等），均是基于子DataFrame的操作**

-   **groupby分组形式**

    -   ```python
        DataFrame.groupby(by=None, axis=0, level=None, as_index=True, sort=True, group_keys=True, squeeze=False, observed=False, dropna=True)
        
        by：用于分组的列名或函数，可以是一个列名，一个函数，一个列表或一个字典。
        axis：分组轴，如果axis=0(默认值)，则沿着行方向分组；如果axis=1，则沿着列方向分组。
        level：在多层索引的情况下，用于指定分组的级别。
        as_index：是否将分组键作为索引返回，如果as_index=True(默认值)，则返回一个带有分组键作为索引的对象，否则返回一个不带索引的对象。
        sort：是否对分组进行排序，如果sort=True（默认值），则对分组键进行排序，否则不排序。
        group_keys：是否在结果中包含分组键，如果group_keys=True（默认值），则结果中包含分组键，否则不包含。
        squeeze：是否压缩返回结果，如果squeeze=True，则尝试压缩返回结果；否则不压缩。
        observed：是否仅使用观察到的类别进行分组，仅适用于类别类型数据。
        dropna：是否删除包含缺失值的行，如果dropna=True（默认值），则删除包含缺失值的行；否则保留。
        ```

-   **groupby分组运算**

    -   ```python
        函数	作用  #聚合操作
        min	最小值
        max	最大值
        sum	求和
        mean	均值
        median	中位数
        std	标准差
        var	方差
        count	计数
        ```

    -    **agg 聚合**操作：可以针对不同列选择不同聚合方法
    
    -    **transform**
    
    -    **apply**

# 机器学习过程概述

#### 数据探索

-   加载数据，变量分析，缺失值处理，数据清洗，数据可视化，统计分析

#### 特征工程

-   特征处理，归一化等，特征相关性分析，特征降维，PCA处理

#### 模型训练

-   训练集与测试集划分，模型选择拟合

#### 模型验证

-   欠拟合与过拟合、正则化、交叉验证

-   模型调参、网格搜索、学习与验证曲线

#### 模型融合

-   模型优化与融合，投票法、加权平均法、Stacking、Boosting、Bagging等方法

## NLP知识-新闻文本分类demo

-   One-hot 编码（独热编码）

-   词袋模型（Bag of Words, **BoW**）

    >   **不考虑单词顺序**，只关注单词在文本中出现的次数。适用于文本分类（如垃圾邮件识别），但容易丢失句子结构信息

-   N-gram（n元模型）

    >   通过 **滑动窗口** 方式，将单词组合成 **n 个单词的短语**，保留单词顺序信息。适用于希望保留文本结构的任务，如情感分析或机器翻译

-   TF-IDF（词频-逆文档频率）

    >   适用于文本分类、信息检索，如 **Google 搜索引擎**。过滤掉常见词（如 "the", "and"）。
    >
    >   依赖统计特性，**不理解词的实际意义**（无法判断 "great" 和 "good" 语义接近）。不能处理同义词（如 "big" 和 "large" 被视为不同的词）。

    <img src="C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\image-20250310165916036.png" alt="image-20250310165916036" style="zoom: 67%;" />

-   FastText

-   word2vec

    >   通过单词和上下文彼此预测，对应的两个算法分别为：
    >
    >   -   Skip-grams (SG)：预测上下文
    >   -   Continuous Bag of Words (CBOW)：预测目标单词
    >       Continuous Bag of Words （CBOW）：预测目标单词

## LLM大模型

-   将给大模型的输入称为 Prompt，将大模型返回的输出称为 Completion

-   使用分隔符`\```，"""，< >，<tag> </tag>，:`,防止**提示词注入（Prompt Rejection）**

-   **Huggingface下载模型**

    ```python
    pip install transformers 
    pip install huggingface_hub
    huggingface-cli download wdndev/tiny_llm_sft_92m --local-dir E:\PyCharm\tiny_llm_92m
    pip install -r E:\PyCharm\tiny_llm_92m\requirements.txt
    streamlit run E:\PyCharm\project_learn\chestnut\llm92m.py
    streamlit run E:\PyCharm\project_learn\PythonNLP\LLM3.py
    import warnings
    warnings.filterwarnings("ignore")
    
    streamlit run LLMdata_test.py
    
    #只能提问一次，不按关键词提问回答差不多，优化模型角色扮演一下
    ```

## AICG降重策略

-   删除连接词 
-   调整文章结构（ai写的一般为总分总结构） 
-   降低内容的可预测性 
-   对于将动词名词化的句子，改成主动句，加入主观的判断
-   打乱句子排列，改变语序
