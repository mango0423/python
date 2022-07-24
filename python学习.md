

# 5-26（day1~4）

<img src="C:\Users\胡洪铭\AppData\Roaming\Typora\typora-user-images\image-20220530222303671.png" alt="image-20220530222303671" style="zoom:50%;" />

<img src="C:\Users\胡洪铭\AppData\Roaming\Typora\typora-user-images\image-20220530222332692.png" alt="image-20220530222332692" style="zoom:50%;" />

%06d，表示输出的整数显示位数，不⾜以0补全，超出当前位数则原样输出
%.2f，表示⼩数点后显示的⼩数位数

格式化字符串除了%s，还可以写为 f'{表达式}'

```
# 我的名字是TOM，明年19岁了
print('我的名字是%s，明年%d岁了' % (name, age + 1))
# 我的名字是TOM，明年19岁了
print(f'我的名字是{name}, 明年{age + 1}岁了')
```

\n ：换⾏。
\t ：制表符，⼀个tab键（4个空格）的距离



当程序执⾏到 input ，等待⽤户输⼊，输⼊完成之后才继续向下执⾏。
在Python中， input 接收⽤户输⼊后

，⼀般存储到变量，⽅便使⽤。
在Python中， input 会把接收到的任意⽤户输⼊的数据都当做字符串处理(换成整型要强制转换)

```
password = input('请输⼊您的密码：')
print(f'您输⼊的密码是{password}')
# <class 'str'>
print(type(password))
```

<img src="C:\Users\胡洪铭\AppData\Roaming\Typora\typora-user-images\image-20220530223821324.png" alt="image-20220530223821324" style="zoom:50%;" />

<img src="C:\Users\胡洪铭\AppData\Roaming\Typora\typora-user-images\image-20220530223900125.png" alt="image-20220530223900125" style="zoom:50%;" />

<img src="C:\Users\胡洪铭\AppData\Roaming\Typora\typora-user-images\image-20220530223921022.png" alt="image-20220530223921022" style="zoom:50%;" />

### 比较运算符

<img src="C:\Users\胡洪铭\AppData\Roaming\Typora\typora-user-images\image-20220530223935653.png" alt="image-20220530223935653" style="zoom:50%;" />

### 逻辑运算符

<img src="C:\Users\胡洪铭\AppData\Roaming\Typora\typora-user-images\image-20220530224021386.png" alt="image-20220530224021386" style="zoom:50%;" />

**and  两边都对，返回y**

**or 两边都对，返回x**

## if语句

```
if 条件1:
 条件1成⽴执⾏的代码1
 条件1成⽴执⾏的代码2
 ......
elif 条件2：
 条件2成⽴执⾏的代码1
 条件2成⽴执⾏的代码2
 ......
......
else:
 以上条件都不成⽴执⾏执⾏的代码
```

三目运算符

条件成⽴执⾏的表达式 if 条件 else 条件不成⽴执⾏的表达式

```
a = 1
b = 2
c = a if a > b else b
print(c)
```

## while语句

```
while 条件:
 条件成⽴重复执⾏的代码1
 条件成⽴重复执⾏的代码2
 ......
```

## break语句

结束该循环

## continue语句

结束本次循环，进行下次循环

# 5-27（day5）

## 常⽤操作⽅法

### 一：查找

**find()与rfind()**：检测某个⼦串是否包含在这个字符串中，如果在返回这个⼦串开始的位置下标，否则则返
回-1。

```
字符串序列.find(⼦串, 开始位置下标, 结束位置下标)
mystr = "hello world and itcast and itheima and Python"
print(mystr.find('and')) # 12
print(mystr.find('and', 15, 30)) # 23
print(mystr.find('ands')) # -1
```

**index()**：检测某个⼦串是否包含在这个字符串中，如果在返回这个⼦串开始的位置下标，否则则
报异常

```
字符串序列.index(⼦串, 开始位置下标, 结束位置下标)
mystr = "hello world and itcast and itheima and Python"
print(mystr.index('and')) # 12
print(mystr.index('and', 15, 30)) # 23
print(mystr.index('ands')) # 报错
```

count()：返回某个⼦串在字符串中出现的次数

```
字符串序列.count(⼦串, 开始位置下标, 结束位置下标)
```

### 二：修改

replace()：替换

```
字符串序列.replace(旧⼦串, 新⼦串, 替换次数)
# 结果：hello world he itcast he itheima he Python
print(mystr.replace('and', 'he'))
```

split()：按照指定字符分割字符串

```
字符串序列.split(分割字符, num)
# 结果：['hello world ', ' itcast ', ' itheima ', ' Python']
print(mystr.split('and'))
```

join()：⽤⼀个字符或⼦串合并字符串，即是将多个字符串合并为⼀个新的字符串。

```
字符或⼦串.join(多字符串组成的序列)
list1 = ['chuan', 'zhi', 'bo', 'ke']
t1 = ('aa', 'b', 'cc', 'ddd')
# 结果：chuan_zhi_bo_ke
print('_'.join(list1))
# 结果：aa...b...cc...ddd
print('...'.join(t1))
```

capitalize()：将字符串第⼀个字符转换成⼤写

title()：将字符串每个单词⾸字⺟转换成⼤写

upper()：将字符串中⼩写转⼤写。	

lower()：将字符串中⼤写转⼩写

lstrip()：删除字符串左侧空⽩字符

rstrip()：删除字符串右侧空⽩字符

strip()：删除字符串两侧空⽩字符

ljust()：返回⼀个原字符串左对⻬,并使⽤指定字符(默认空格)填充⾄对应⻓度 的新字符串

```
字符串序列.ljust(⻓度, 填充字符)
```



### 三：判断

startswith()：检查字符串是否是以指定⼦串开头，是则返回 True，否则返回 False。如果设置开
始和结束位置下标，则在指定范围内检查

endswith()：：检查字符串是否是以指定⼦串结尾，是则返回 True，否则返回 False。如果设置开
始和结束位置下标，则在指定范围内检查

isalpha()：如果字符串⾄少有⼀个字符并且所有字符都是字⺟则返回 True, 否则返回 False

isdigit()：如果字符串只包含数字则返回 True 否则返回 False

isalnum()：如果字符串⾄少有⼀个字符并且所有字符都是字⺟或数字则返 回 True,否则返回
False

isspace()：如果字符串中只包含空⽩，则返回 True，否则返回 False

# 5-28（day6）

# 列表

列表可以⼀次性存储多个数据，且可以为不同数据类型

### 列表的常⽤操作 

#### 1、查找

index()：返回指定数据所在位置的下标

```
列表序列.index(数据, 开始位置下标, 结束位置下标)
name_list = ['Tom', 'Lily', 'Rose']
print(name_list.index('Lily', 0, 2)) # 1
```

count()：统计指定数据在当前列表中出现的次数

len()：访问列表⻓度，即列表中数据的个数

in：判断指定数据在某个列表序列，如果在返回True，否则返回False

```
name_list = ['Tom', 'Lily', 'Rose']
# 结果：True
print('Lily' in name_list)
# 结果：False
print('Lilys' in name_list)
```

not in：判断指定数据不在某个列表序列，如果不在返回True，否则返回False

#### 2、增加

append()：列表结尾追加数据

```
name_list = ['Tom', 'Lily', 'Rose']
name_list.append('xiaoming')
# 结果：['Tom', 'Lily', 'Rose', 'xiaoming']
print(name_list)
```

如果append()追加的数据是⼀个序列，则追加整个序列到列表

```
name_list = ['Tom', 'Lily', 'Rose']
name_list.append(['xiaoming', 'xiaohong'])
# 结果：['Tom', 'Lily', 'Rose', ['xiaoming', 'xiaohong']]
print(name_list)
```

extend()：列表结尾追加数据，如果数据是⼀个序列，则将这个序列的数据逐⼀添加到列表

**添加单个数据**

```
name_list = ['Tom', 'Lily', 'Rose']
name_list.extend('xiaoming')
# 结果：['Tom', 'Lily', 'Rose', 'x', 'i', 'a', 'o', 'm', 'i', 'n', 'g']
print(name_list)
```

**添加序列**

```
name_list = ['Tom', 'Lily', 'Rose']
name_list.extend(['xiaoming', 'xiaohong'])
# 结果：['Tom', 'Lily', 'Rose', 'xiaoming', 'xiaohong']
print(name_list)
```

insert()：指定位置新增数据

```
列表序列.insert(位置下标, 数据)
name_list = ['Tom', 'Lily', 'Rose']
name_list.insert(1, 'xiaoming')
# 结果：['Tom', 'xiaoming', 'Lily', 'Rose']
print(name_list)
```

#### 3、删除

del：删除列表，删除指定数据

```
name_list = ['Tom', 'Lily', 'Rose']
# 结果：报错提示：name 'name_list' is not defined
del name_list
print(name_list)

name_list = ['Tom', 'Lily', 'Rose']
del name_list[0]
# 结果：['Lily', 'Rose']
print(name_list)
```

pop()：删除指定下标的数据(默认为最后⼀个)，并返回该数据。

```
列表序列.pop(下标)

name_list = ['Tom', 'Lily', 'Rose']
del_name = name_list.pop(1)
# 结果：Lily
print(del_name)
# 结果：['Tom', 'Rose']
print(name_list)
```

remove()：移除列表中某个数据的第⼀个匹配项。

```
列表序列.remove(数据)
name_list = ['Tom', 'Lily', 'Rose']
name_list.remove('Rose')
# 结果：['Tom', 'Lily']
print(name_list)
```

clear()：清空列表

```
name_list = ['Tom', 'Lily', 'Rose']
name_list.clear()
print(name_list) # 结果： []
```

#### 4、修改

修改指定下标的数据

```
name_list = ['Tom', 'Lily', 'Rose']
name_list[0] = 'aaa'
# 结果：['aaa', 'Lily', 'Rose']
print(name_list)
```

逆置：reverse()

排序：sort()

```
列表序列.sort( key=None, reverse=False)
#reverse表示排序规则，true为降序，false为升序（默认）
```

#### 5、复制

copy()

```
name_list = ['Tom', 'Lily', 'Rose']
name_li2 = name_list.copy()
# 结果：['Tom', 'Lily', 'Rose']
print(name_li2)das
```

## 列表的循环遍历

while()

```
name_list = ['Tom', 'Lily', 'Rose']
i = 0
while i < len(name_list):
 print(name_list[i])
 i += 1
```

for()

```
name_list = ['TOM', 'Lily', 'ROSE']

for i in name_list:
    # 遍历序列中的数据
    print(i)
```

## 列表的嵌套

```
name_list = [['⼩明', '⼩红', '⼩绿'], ['Tom', 'Lily', 'Rose'], ['张三', '李四', 
'王五']]
# 第⼀步：按下标查找到李四所在的列表
print(name_list[2])
# 第⼆步：从李四所在的列表⾥⾯，再按下标找到数据李四
print(name_list[2][1])
```

# 元组

⼀个元组可以存储多个数据，元组内的数据是不能修改的，只支持查找

**元组特点：**定义元组使⽤⼩括号，且逗号隔开各个数据，数据可以是不同的数据类型

```
t2 = (10,)
print(type(t2)) # tuple
t3 = (20)
print(type(t3)) # int
t4 = ('hello')
print(type(t4)) # str

注意：如果定义的元组只有⼀个数据，那么这个数据后⾯也好添加逗号，否则数据类型为唯⼀的
这个数据的数据类型
元组内的直接数据如果修改则⽴即报错，但是如果元组⾥⾯有列表，修改列表⾥⾯的数据则是⽀持的

tuple2 = (10, 20, ['aa', 'bb', 'cc'], 50, 30)
print(tuple2[2]) # 访问到列表
# 结果：(10, 20, ['aaaaa', 'bb', 'cc'], 50, 30)
tuple2[2][0] = 'aaaaa'
print(tuple2)
```

按下标查找数据

index()：查找某个数据，如果数据存在返回对应的下标，否则报错，语法和列表、字符串的index
⽅法相同

count()：统计某个数据在当前元组出现的次数

len()：统计元组中数据的个数

# 5-29（day7）

# 集合

创建集合使⽤ {} 或 set() ， 但是如果要创建空集合只能使⽤ set() ，**因为 {} ⽤来创建空字典**

**特点：**

1. 集合可以去掉重复数据；

2. 集合数据是⽆序的，故不⽀持下标

```
s1 = {10, 20, 30, 40, 50}
print(s1)
s2 = {10, 30, 20, 10, 30, 40, 30, 50}
print(s2)
s3 = set('abcdefg')
print(s3)
s4 = set()
print(type(s4)) # set
s5 = {}
print(type(s5)) # dict
```

add()

```
s1 = {10, 20}
s1.add(100)
s1.add(10)
print(s1) # {100, 10, 20}
因为集合有去重功能，所以，当向集合内追加的数据是当前集合已有数据的话，则不进⾏任何操
作
```

update(), 追加的数据是序列

```
s1 = {10, 20}
# s1.update(100) # 报错
s1.update([100, 200])
s1.update('abc')
print(s1)
```

remove()，删除集合中的指定数据，如果数据不存在则报错

discard()，删除集合中的指定数据，如果数据不存在也不会报错

pop()，随机删除集合中的某个数据，并返回这个数据

in：判断数据在集合序列
not in：判断数据不在集合序列

```
s1 = {10, 20, 30, 40, 50}

# in 或not in 判断数据10是否存在
#true
print(10 in s1)

#false
print(10 not in s1)
```



# 字典

字典⾥⾯的数据是以键值对形式出现，字典数据和数据顺序没有关系，即字典不⽀持下标，
后期⽆论数据如何变化，只需要按照对应的键的名字查找数据即可

**特点：**

符号为⼤括号
数据为键值对形式出现
各个键值对之间⽤逗号隔开

```
# 有数据字典
dict1 = {'name': 'Tom', 'age': 20, 'gender': '男'}
# 空字典
dict2 = {}
dict3 = dict()
注意：⼀般称冒号前⾯的为键(key)，简称k；冒号后⾯的为值(value)，简称v
```

## 增/改

```
dict1 = {'name': 'Tom', 'age': 20, 'gender': '男'}
dict1['name'] = 'Rose'
# 结果：{'name': 'Rose', 'age': 20, 'gender': '男'}
print(dict1)
dict1['id'] = 110
# {'name': 'Rose', 'age': 20, 'gender': '男', 'id': 110}
print(dict1)
注意：如果key存在则修改这个key对应的值；如果key不存在则新增此键值对
```

## 删

del() / del：删除字典或删除字典中指定键值对

clear()：清空字典

## 查

### key值查找

```
dict1 = {'name': 'Tom', 'age': 20, 'gender': '男'}
print(dict1['name']) # Tom
print(dict1['id']) # 报错
如果当前查找的key存在，则返回对应的值；否则则报错
```

### get()

```
dict1 = {'name': 'Tom', 'age': 20, 'gender': '男'}
print(dict1.get('name')) # Tom
print(dict1.get('id', 110)) # 110
print(dict1.get('id')) # None
字典序列.get(key, 默认值)
注意：如果当前查找的key不存在则返回第⼆个参数(默认值)，如果省略第⼆个参数，则返回
None
```

### keys() 

返回key的值

### values()

返回value的值

### items()

返回整个键值对

```
dict1 = {'name': 'Tom', 'age': 20, 'gender': '男'}
print(dict1.items()) # dict_items([('name', 'Tom'), ('age', 20), ('gender', 
'男')])
```

# 公共操作

<img src="C:\Users\胡洪铭\AppData\Roaming\Typora\typora-user-images\image-20220529190217974.png" alt="image-20220529190217974" style="zoom:50%;" />

字符串，列表，元组都支持

<img src="C:\Users\胡洪铭\AppData\Roaming\Typora\typora-user-images\image-20220529190353628.png" alt="image-20220529190353628" style="zoom: 50%;" />

range()

<img src="C:\Users\胡洪铭\AppData\Roaming\Typora\typora-user-images\image-20220530192920880.png" alt="image-20220530192920880" style="zoom:50%;" />

注意：range()⽣成的序列不包含end数字

```
enumerate(可遍历对象, start=0)
list1 = ['a', 'b', 'c', 'd', 'e']
for i in enumerate(list1):
 print(i)
for index, char in enumerate(list1, start=1):
 print(f'下标是{index}, 对应的字符是{char}')
 注意：start参数⽤来设置遍历数据的下标的起始值，默认为0
```

**tuple()** 
作⽤：将某个序列转换成元组()

(在 [Python](http://c.biancheng.net/python/) 中，序列类型包括字符串、列表、元组、集合和字典)

**list()**

作⽤：将某个序列转换成列表[]

**set()**

作⽤：将某个序列转换成集合{}

# 5-30（day8）

## 列表推导式(用于简化代码)

```
# 需求：0-10偶数数据的列表
# 1. 简单列表推导式 range步长
list1 = [i for i in range(0, 10, 2)]
print(list1)

# 2. for循环加if 创建有规律的列表
list2 = []
for i in range(10):
    if i % 2 == 0:
        list2.append(i)

print(list2)

# 3. 把for循环配合if的代码 改写 带if的列表推导式
list3 = [i for i in range(10) if i % 2 == 0]
print(list3)

```

```
需求：创建列表如下：
[(1, 0), (1, 1), (1, 2), (2, 0), (2, 1), (2, 2)]
list1 = [(i, j) for i in range(1, 3) for j in range(3)]
print(list1)
```

**[表达式 for 变量 in 列表]** 
[out_exp_res for out_exp in input_list]

- **out_exp_res：列表生成元素表达式，可以是有返回值的函数。**
- **for out_exp in input_list：迭代 input_list 将 out_exp 传入到 out_exp_res 表达式中。**
- **if condition：条件语句，可以过滤列表中不符合条件的值**

# 函数

## 定义函数

```
def 函数名(参数):
 代码1
 代码2
 ......
```

## 调用函数

```
函数名(参数)
#在Python中，函数必须先定义后使⽤
```

#### 函数的返回值作⽤ 

```
def buy():
 return '烟'

#使⽤变量保存函数返回值
goods = buy()
print(goods)
```

#### 定义函数的说明⽂档

```
def 函数名(参数):
 """ 说明⽂档的位置 """
 代码
 ......
```

```
help(函数名)
def sum_num(a, b):
 """ 求和函数 """
 return a + b
 
help(sum_num)
```

变量作⽤域指的是变量⽣效的范围，主要分为两类：局部变量和全局变量

**局部变量**：所谓局部变量是定义在函数体内部的变量，即只在函数体内部⽣效

**全局变量**：所谓全局变量，指的是在函数体内、外都能⽣效的变量

思考：如何在函数体内部修改全局变量？

```
a = 100

def testA():
 print(a)
 
def testB():
 # global 关键字声明a是全局变量
 global a
 a = 200
 print(a)
 
testA() # 100
testB() # 200
print(f'全局变量a = {a}') # 全局变量a = 200
```

函数的返回值

**如果⼀个函数如些两个return (如下所示)，程序如何执⾏？**

```
def return_num():
 return 1
 return 2
result = return_num()
print(result) # 1
答：只执⾏了第⼀个return，原因是因为return可以退出当前函数，导致return下⽅的代码不执⾏
```

**如果⼀个函数要有多个返回值，该如何书写代码？**

```
def return_num():
 return 1, 2
result = return_num()
print(result) # (1, 2)

注意：
1. return a, b 写法，返回多个数据的时候，默认是元组类型。
2. return后⾯可以连接列表、元组或字典，以返回多个值
```

函数的参数

1、位置参数，调⽤函数时根据函数定义的参数位置来传递参数

```
def user_info(name, age, gender):
 print(f'您的名字是{name}, 年龄是{age}, 性别是{gender}')
 
user_info('TOM', 20, '男')
```

2、关键字参数，通过“键=值”形式加以指定

```
def user_info(name, age, gender):
 print(f'您的名字是{name}, 年龄是{age}, 性别是{gender}')
 
user_info('Rose', age=20, gender='⼥')
user_info('⼩明', gender='男', age=16)
```

###### 注意：函数调⽤时，如果有位置参数时，**位置参数**必须在**关键字参数**的前⾯，但关键字参数之间不存在

**先后顺序**

3、缺省参数也叫默认参数，⽤于定义函数，为参数提供默认值，调⽤函数时可不传该默认参数的值（注
意：所有位置参数必须出现在默认参数前，包括函数定义和调⽤）

```
def user_info(name, age, gender='男'):
 print(f'您的名字是{name}, 年龄是{age}, 性别是{gender}')
 
user_info('TOM', 20)
user_info('Rose', 18, '⼥')
注意：函数调⽤时，如果为缺省参数传值则修改默认参数值；否则使⽤这个默认值
```

4 、**不定⻓参数**也叫**可变参数**。⽤于不确定调⽤的时候会传递多少个参数(不传参也可以)的场景

```
def user_info(*args):
 print(args)
 
# ('TOM',)
user_info('TOM')
# ('TOM', 18)
user_info('TOM', 18)
注意：传进的所有参数都会被args变量收集，它会根据传进参数的位置合并为⼀个元组(tuple)，
args是元组类型，这就是包裹位置传递
```

```
def user_info(**kwargs):
 print(kwargs)
 
# {'name': 'TOM', 'age': 18, 'id': 110}
user_info(name='TOM', age=18, id=110)
综上：⽆论是包裹位置传递还是包裹关键字传递，都是⼀个组包的过程。
```

# 拆包和交换变量值 

元组

```
def return_num():
 return 100, 200
  
num1, num2 = return_num()
print(num1) # 100
print(num2) # 200
```

字典

```
dict1 = {'name': 'TOM', 'age': 18}
a, b = dict1

# 对字典进⾏拆包，取出来的是字典的key
print(a) # name
print(b) # age

print(dict1[a]) # TOM
print(dict1[b]) # 18
```

## 交换变量的值

```
a, b = 1, 2
a, b = b, a
print(a) # 2
print(b) # 1
```

# 5-31（day9-11）

## 引用

我们可以⽤ id() 来判断两个变量是否为同⼀个值的引⽤

```
# 1. int类型
a = 1
b = a

print(b) # 1
print(id(a)) # 140708464157520
print(id(b)) # 140708464157520

a = 2
print(b) # 1,说明int类型为不可变类型 

print(id(a)) # 140708464157552，此时得到是的数据2的内存地址
print(id(b)) # 140708464157520


# 2. 列表
aa = [10, 20]
bb = aa

print(id(aa)) # 2325297783432
print(id(bb)) # 2325297783432

aa.append(30)
print(bb) # [10, 20, 30], 列表为可变类型
print(id(aa)) # 2325297783432
print(id(bb)) # 2325297783432
```

所谓可变类型与不可变类型是指：数据能够直接进⾏修改，如果能直接修改那么就是可变，否则是不可
变 	

### 可变类型（原数据可直接修改）指在原地址

列表
字典
集合

### 不可变类型（原数据不可修改）在新的地址

整型
浮点型
字符串
元组

# 函数加强

## 如果⼀个函数有⼀个返回值，并且只有⼀句代码，可以使⽤ lambda简化

```
 # 函数
def fn1():
 return 200
print(fn1)
print(fn1())

# lambda表达式
fn2 = lambda: 100
print(fn2)      #注意：直接打印lambda表达式，输出的是此lambda的内存地址
print(fn2())    #100
lambda表达式的参数可有可⽆，函数的参数在lambda表达式中完全适⽤。
lambda函数能接收任何数量的参数但只能返回⼀个表达式的值
```

```
def add(a, b):
 return a + b
result = add(1, 2)
print(result)

print((lambda a, b: a + b)(1, 2))
 lambda 参数列表 ： 表达式
```

```
print((lambda: 100)())                                     #无参数
print((lambda a: a)('hello world'))                        #一个参数
print((lambda a, b, c=100: a + b + c)(10, 20))             #默认参数
print((lambda *args: args)(10, 20, 30))                    #可变参数：*args 
print((lambda **kwargs: kwargs)(name='python', age=20))    #可变参数：**kwargs 
```

## lambda的应⽤ 

```
print((lambda a, b: a if a > b else b)(1000, 500))
```

### 列表数据按字典key的值排序

```
students = [
 {'name': 'TOM', 'age': 20},
 {'name': 'ROSE', 'age': 19},
 {'name': 'Jack', 'age': 22}
]

# 按name值升序排列
students.sort(key=lambda x: x['name'])
print(students)

# 按name值降序排列
students.sort(key=lambda x: x['name'], reverse=True)
print(students)

# 按age值升序排列
students.sort(key=lambda x: x['age'])
print(students)
```



# 6-4（day12）

 **abs()** 函数可以完成对数字求绝对值计算

```
def add_num(a, b):
 return abs(a) + abs(b)
result = add_num(-1, 2)
print(result) # 3

#第二种方法更简洁
def sum_num(a, b, f):
 return f(a) + f(b)
result = sum_num(-1, 2, abs)
print(result) # 3

```

**map(func, lst)**，将传⼊的函数变量func作⽤到lst变量的每个元素中，并将结果组成新的列表(Python2)/
迭代器(Python3)返回

```
list1 = [1, 2, 3, 4, 5]

def func(x):
 return x ** 2
 
result = map(func, list1)   #map(函数，列表)
print(result) # <map object at 0x0000013769653198>
print(list(result)) # [1, 4, 9, 16, 25]

```

**reduce(func(x,y)，lst)**，其中func必须有两个参数。每次func计算的结果继续和序列的下⼀个元素做累
积计算

```
import functools

list1 = [1, 2, 3, 4, 5]

def func(a, b):
 return a + b
 
result = functools.reduce(func, list1)
print(result) # 15

注意：reduce()传⼊的参数func必须接受2个参数
```

**filter(func, lst)**函数⽤于过滤序列, 过滤掉不符合条件的元素, 返回⼀个 filter 对象,。如果要转换为列表,
可以使⽤ list() 来转换

```
list1 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

def func(x):
 return x % 2 == 0
 
result = filter(func, list1)
print(result) # <filter object at 0x0000017AF9DC3198>
print(list(result)) # [2, 4, 6, 8, 10]
```

iambda语法

lambda 参数列表: 表达式

⽆参数

```
lambda: 表达式
```

⼀个参数

```
lambda 参数: 表达式
```

默认参数

```
lambda key=value: 表达式
```

不定⻓位置参数

```
 lambda *args: 表达式
```

不定⻓关键字参数

```
 lambda **kwargs: 表达式
```

# 6-8(day13)

## 文件

总结：⽂件操作的作⽤就是把⼀些内容(数据)存储存放起来，可以让程序下⼀次执⾏的时候直接使
⽤，⽽不必重新制作⼀份，省时省⼒

**open(name, mode)**

name：是要打开的⽬标⽂件名的字符串(可以包含⽂件所在的具体路径)。
mode：设置打开⽂件的模式(访问模式)：只读、写⼊、追加等。

<img src="C:\Users\胡洪铭\AppData\Roaming\Typora\typora-user-images\image-20220608102818866.png" alt="image-20220608102818866" style="zoom:50%;" />

```
f = open('test.txt', 'w')
注意：此时的 f 是 open 函数的⽂件对象
```

## 写

```
对象对象.write('内容')

 1. 打开⽂件
f = open('test.txt', 'w')
# 2.⽂件写⼊
f.write('hello world')
# 3. 关闭⽂件
f.close()

1. w 和 a 模式：如果⽂件不存在则创建该⽂件；如果⽂件存在， w 模式先清空再写⼊， a 模式
直接末尾追加。
2. r 模式：如果⽂件不存在则报错。
```

## 读

**read()**

```
⽂件对象.read(num)
```

num表示要从⽂件中读取的数据的⻓度（单位是字节），如果没有传⼊num，那么就表示读取⽂
件中所有的数据。

**readlines()**

readlines可以按照⾏的⽅式把整个⽂件中的内容进⾏⼀次性读取，并且返回的是⼀个列表，其中每⼀⾏
的数据为⼀个元素

```
f = open('test.txt')
content = f.readlines()

# ['hello world\n', 'abcdefg\n', 'aaa\n', 'bbb\n', 'ccc']
print(content)

# 关闭⽂件
f.close()
```

**readline()**
readline()⼀次读取⼀⾏内容

```
f = open('test.txt')

content = f.readline()
print(f'第⼀⾏：{content}')

content = f.readline()
print(f'第⼆⾏：{content}')

# 关闭⽂件
f.close()
```

**seek()** 
作⽤：⽤来移动⽂件指针

```
⽂件对象.seek(偏移量, 起始位置)
起始位置：
0：⽂件开头
1：当前位置
2：⽂件结尾
```

## 文件备份

步骤 
1. 接收⽤户输⼊的⽂件名

   ```
   old_name = input('请输⼊您要备份的⽂件名：')
   ```

2. 规划备份⽂件名

   2.1 提取⽬标⽂件后缀
   2.2 组织备份的⽂件名，xx[备份]后缀

   ```
   # 2.1 提取⽂件后缀点的下标
   index = old_name.rfind('.')
   #rfind()返回字符串最后一次出现的位置，如果没有匹配项则返回 -1
   
   # print(index) # 后缀中.的下标
   # print(old_name[:index]) # 源⽂件名（⽆后缀）
   
   # 2.2 组织新⽂件名 旧⽂件名 + [备份] + 后缀
   new_name = old_name[:index] + '[备份]' + old_name[index:]
   
   # 打印新⽂件名（带后缀）
   # print(new_name)
   ```

   <img src="C:\Users\胡洪铭\AppData\Roaming\Typora\typora-user-images\image-20220609155619696.png" alt="image-20220609155619696" style="zoom:50%;" />

3. 备份⽂件写⼊数据

   3.1 打开源⽂件 和 备份⽂件
   3.2 将源⽂件数据写⼊备份⽂件
   3.3 关闭⽂件

   ```
   # 3.1 打开⽂件
   old_f = open(old_name, 'rb')
   new_f = open(new_name, 'wb')
   
   # 3.2 将源⽂件数据写⼊备份⽂件
   while True:
    con = old_f.read(1024)
    if len(con) == 0:
    break
    new_f.write(con)
    
   # 3.3 关闭⽂件
   old_f.close()
   new_f.close()
   ```

   ## ⽂件和⽂件夹的操作
   
   在Python中⽂件和⽂件夹的操作要借助os模块⾥⾯的相关功能
   
   ```
   import os
   os.函数名(）
   
   #文件重命名
   os.rename(⽬标⽂件名, 新⽂件名)
   
   #删除文件
   os.remove(⽬标⽂件名)
   
   #创建文件夹
   os.mkdir(⽂件夹名字)
   
   #删除文件夹
   os.rmdir(⽂件夹名字)
   
   #获取当前目录
   os.getcwd()
   
   #改变默认目录
   os.chdir(⽬录)
   
   #获取目录列表
   os.listdir(⽬录)
   
   ```
   
   

# 6-9（day14）

## 定义类

```
class 类名():
 代码
 .....
注意：类名要满⾜标识符命名规则，同时遵循⼤驼峰命名习惯
```

举例：

```
class Washer():
    def wash(self):
         print('我会洗⾐服')
```

## 创建对象

对象⼜名实例

```
对象名 = 类名()

# 创建对象
haier1 = Washer()

# <__main__.Washer object at 0x0000018B7B224240>
print(haier1)

# haier对象调⽤实例⽅法
haier1.wash()

```



# 6-19（day15）
