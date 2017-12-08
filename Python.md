# Python笔记

### 基本函数
- 目录`dir()`
- 帮助`help()`
- 输入`input()`
- 输出`print()`
- 查看地址`id()`
- 查看类型`type()`
### 运算符
###### 算数运算符
- `+`	加
- `-`	减
- `*`	乘
- `/`	除
- `%`	取模
- `**`	幂
- `//`	取整除

###### 逻辑运算符(短路逻辑)
- `x or y` if x is false, then y, else x
- `x and y` if x is false, then x, else y
- `not x` if x is false, then True, else False

###### 比较运算符
- `==` #两对象相等
- `<`
- `>`
- `>=`
- `<=`
- `!=`
- `is` #两对象的同一性
- `is not`
- `in` #成员资格
- `not in`
> 注意`==`和`is`的区别
> 字符串比较：按照ASCII顺序



### 基本标点符号用途
- `,` 输出两个语句中添加逗号相当于输出一个空格
- `+` 输出两个语句中添加加号相当于两个语句拼接
- ` ` 输出两个语句中添加空格相当于一个语句
---
### 基本数据类型
#### 数字
- 整数int
- 浮点数float
###### 除法
#### 字符串
#### bool
#### 空值None
#### 变量
#### 常量
###### 序列解包（sequence unpacking）
- 多个赋值同时操作`x,y,z = 1,2,3`或`x,y,z = tuple/list`
- 可以使用可变参数`x,y,z，*rest = 1,2,3,4,5,6`
- 变量交换`x,y = y,x`

----
### 字符编码
- ASCII
- Unicode
- UTF-8
---
### 序列Sequence
- 索引：`Iter[index]`
- 切片：`Iter[start:stop:step]`
- 加法：`Iter1+Iter2`表示拼接
- 乘法：`Iter*int`表示重复
- 成员资格：`obj in Iter`返回bool类型
- 长度：`len(Iter)`
- 最值：`max(Iter)`、`min(Iter)`
---
#### 列表list
###### 创建空列表
`L = []`
###### 基本操作
- 赋值`L[start:stop:step] = a`
- 删除`del L[start:stop:step]`
- 切片`L[start:stop:step]`
###### 列表方法
- `L.append(obj) #在L末尾添加obj`
- `L.count(obj) #计算obj出现的次数`
- `L.extend(L1) #L1扩充到L，L = L + L1`
- `L.index(obj) #obj的第一次出现的index`
- `L.insert(index,obj)#将obj插入index位置`
- `L.pop([index])#默认弹出最后一个元素，否则弹出第index个元素`
- `L.remove(obj) #移除第一个obj`
- `L.reverse()#L原地反转`
- `L.sort(key=,reverse=True/False)#按照key排序，默认False倒序`


###### 反转的方法
- `L.reverse() #原地反转`
- `L[::-1] #生成新列表`
- `list(reversed(sequence)) #生成新列表`
- `reversed(sequence) #生成迭代器`

---
#### 元组tuple
###### 创建元组
```Python
T = () #创建空元组
T = (a,) 或 T = a, #创建单元素元组
T = a,b,c 或T = (a,b,c) #创建元组
tuple(iterable) #将可迭代类型转换成元组
```
- 创建tuple以'(,)'为标志，括号可以省略，但逗号不可省略
- tuple可以切片，切片后还是tuple
###### 元组方法
- `T.count(obj)`
- `T.index(obj)`

---
#### range
```python
a = range(start, stop[, step]) #返回一个range类型
```
可将其转换成list
```python
a = list(range(start, stop[, step])) #返回一个range类型
```
> 可以使用成员函数`in`、索引`r.index()`、查找index位置元素`r[index]`、切片`r[start,stop,step]`



---

#### 字符串string
> 注：字符串不可改变
###### 字符串格式化
1. 方式一：%格式化
    - `%s`    字符串 (采用str()的显示)
    - `%r`    字符串 (采用repr()的显示)
    - `%c`    单个字符
    - `%b`    二进制整数
    - `%d`    十进制整数
    - `%i`    十进制整数
    - `%o`    八进制整数
    - `%x`    十六进制整数
    - `%e`   指数 (基底写为e)
    - `%E`    指数 (基底写为E)
    - `%f`    浮点数
    - `%F`    浮点数，与上相同
    - `%g`    指数(e)或浮点数 (根据显示长度)
    - `%G`   指数(E)或浮点数 (根据显示长度)
    - `%%`    字符"%"
    > 注：
    >   - 整体格式化：`string % tuple`
    >   - 字段宽度和精度：`%10.2f`，字段宽度为10，精度（必须有.）为2
    > - 可以使用*表示宽度和精度：`'%*.*s' % (6,4,'asdgadfh')`
    > - 宽度不足用0填充`'%010.2f' % math.pi`、`'%0*.*f' % (8,4,1.23456789)`
    > - 左对齐`-`：`'%-10.2f' % math.pi`
    > - 添加正负号`+`：`'%+10.2f' % math.pi`
    > - 空格表示在正数前加上空格：`'% 10.2f' % math.pi`

2. 方式二：format方法（**推荐使用**）
    - `:`后面与`%`类似：`{0:10}`
    - 一般写法：`'{0}, {1}, {2}'.format('a', 'b', 'c') #{}中不写数字，默认从0开始`
    - 访问指定位置：`'{2}, {1}, {0}'.format('a', 'b', 'c')`、`'{0}{1}{0}'.format('abra', 'cad')`
    - `{}`转义：使用两层，如`{{{0}}}`
    - 访问可变参数：`'{2}, {1}, {0}'.format(*'abc') `
    - 访问关键字参数（两种方式）：

         ```python
         >>> 'Coordinates: {latitude}, {longitude}'.format(latitude='37.24N', longitude='-115.81W')
         ```

         ```python
         >>> coord = {'latitude': '37.24N', 'longitude': '-115.81W'}  
         >>> 'Coordinates: {latitude}, {longitude}'.format(**coord)
         ```
    - 访问函数属性
        ```python
        >>> c = 3-5j
        >>> ('The complex number {0} is formed from the real part {0.real} and the imaginary part {0.imag}.').format(c)
        ```
    - 访问可迭代类型的参数项items
        ```python
        >>> coord = (3, 5)
        >>> 'X: {0[0]};  Y: {0[1]}'.format(coord)
        ```    
    - 替换`%s`和`%r`字符串
        ```python
        >>> "repr() shows quotes: {!r}; str() doesn't: {!s}".format('test1', 'test2')
        ```  
    - 对齐文本并指定宽度
        ```python
        >>> '{:<30}'.format('left aligned')
        >>> '{:>30}'.format('right aligned')
        >>> '{:^30}'.format('centered')
        '{:*^30}'.format('centered')  # use '*' as a fill char
        ```  
    - 替换`%+f`、`%-f`、和`% f`并指定符号
        ```python
        >>> '{:+f}; {:+f}'.format(3.14, -3.14)  # show it always
        '+3.140000; -3.140000'
        >>> '{: f}; {: f}'.format(3.14, -3.14)  # show a space for positive numbers
        ' 3.140000; -3.140000'
        >>> '{:-f}; {:-f}'.format(3.14, -3.14)  # show only the minus -- same as '{:f}; {:f}'
        '3.140000; -3.140000'
        ```
    - 替换`%x`、`%o`并转换进制
        ```python
        >>> # format also supports binary numbers
        >>> "int: {0:d};  hex: {0:x};  oct: {0:o};  bin: {0:b}".format(42)
        'int: 42;  hex: 2a;  oct: 52;  bin: 101010'
        >>> # with 0x, 0o, or 0b as prefix:
        >>> "int: {0:d};  hex: {0:#x};  oct: {0:#o};  bin: {0:#b}".format(42)
        'int: 42;  hex: 0x2a;  oct: 0o52;  bin: 0b101010'
        ```  
    - 使用逗号作为千的分隔符    
        ```python
        >>> '{:,}'.format(1234567890)
        '1,234,567,890'
        ```
    - 百分数表示
        ```python
        >>> points = 19
        >>> total = 22
        >>> 'Correct answers: {:.2%}'.format(points/total)
        'Correct answers: 86.36%'
        ```
    - 使用特定类型的格式化        
        ```python
        >>> import datetime
        >>> d = datetime.datetime(2010, 7, 4, 12, 15, 58)
        >>> '{:%Y-%m-%d %H:%M:%S}'.format(d)
        '2010-07-04 12:15:58'
        ```
    - 嵌套参数和更复杂的示例
        ```python
        >>> for align, text in zip('<^>', ['left', 'center', 'right']):
        ...     '{0:{fill}{align}16}'.format(text, fill=align, align=align)
        ...
        'left<<<<<<<<<<<<'
        '^^^^^center^^^^^'
        '>>>>>>>>>>>right'
        >>>
        >>> octets = [192, 168, 0, 1]
        >>> '{:02X}{:02X}{:02X}{:02X}'.format(*octets)
        'C0A80001'
        >>> int(_, 16)
        3232235521
        >>>
        >>> width = 5
        >>> for num in range(5,12):
        ...     for base in 'dXob':
        ...         print('{0:{width}{base}}'.format(num, base=base, width=width), end=' ')
        ...     print()
        ...
            5     5     5   101
            6     6     6   110
            7     7     7   111
            8     8    10  1000
            9     9    11  1001
           10     A    12  1010
           11     B    13  1011

        ```

3. 方式三：模板字符串
    ```Python
    from string import Template
    S = Template('$x,nihao$x!')    
    S.substitute(x = '我')#打印结果：'我,nihao我!'
    ```
    - 替换的是单词的一部分，需要加{}:
        ```Python
        S = Template('${x}tion')
        ```
    - 美元符号需要两个$:
        ```Python
        S = Template('$$')
        ```
    - 还可以用dict
        ```Python
        S = Template('$A is $B')
        d = {'A':'wo','B':'ni'}
        S.substitute(d)
        ```

###### 字符串方法
- 查找子串，返回最左端索引：`S.find(sub[, start[, end]])-> int`
- 字符串大小写
    ```python
    S.upper()#S中的字母大写
    S.lower() #S中的字母小写
    S.capitalize() #首字母大写
    S.istitle() #S是否是首字母大写的
    S.isupper() #S中的字母是否便是大写
    S.islower() #S中的字母是否全是小写
    ```
- 字符串去空格
    ```python
    S.strip()去掉字符串的左右空格
    S.lstrip()去掉字符串的左边空格
    S.rstrip()去掉字符串的右边空格
    ```
- 字符串其他方法
    ```python
    S.center(width, [fillchar]) #中间对齐
    S.count(substr, [start, [end]]) #计算substr在S中出现的次数
    S.expandtabs([tabsize]) #把S中的tab字符替换没空格，每个tab替换为tabsize个空格，默认是8个
    S.isalnum() #是否全是字母和数字，并至少有一个字符
    S.isalpha() #是否全是字母，并至少有一个字符
    S.isspace() #是否全是空白字符，并至少有一个字符    
    S.ljust(width,[fillchar]) #输出width个字符，S左对齐，不足部分用fillchar填充，默认的为空格。
    S.rjust(width,[fillchar]) #右对齐
    S.splitlines([keepends]) #把S按照行分割符分为一个list，keepends是一个bool值，如果为真每行后而会保留行分割符。
    S.swapcase() #大小写互换
    S.replace(old, new[, count]) -> str，将old替换为new
    S.split(sep=None, maxsplit=-1) -> list of strings，join的逆方法
    S.translate(table) -> str，替换单个字符，但是可以同时替换
    S.join(iterable) #将S加到iterable中
    ```
###### string模块（与上述方法类似）
```python
import string
```
---
#### list、tuple、string的异同与相互转换
###### 异同
- list可以修改，tuple、string不可以修改
- tuple可内嵌list达到修改的目的，string可使用切片方式修改
###### 相互转换
- list to tuple：`tuple(list)`
- tuple to list：`list(tuple)`
- list to string：`string.split()`
- string to list：`'[sep]'.join(list)`

---


### 字典dict
###### 创建字典
- 直接创建
    ```python
    D = {key1:value1,key2:value2,key3:value3,...}
    ```
- 序列创建
    ```python
    items = [('name','Ai'),('age','12')]
    D = dict(items)
    ```
- 关键字参数创建
    ```python
    D = dict(name = 'Ai', age = 12)    
    ```
###### 字典的基本操作
- `len(D)`
- `D[key]`
- `D[key] = value`
- `del D[key]`
- 成员资格：`key in D #只能查找键`
- key类型：任意的不可变量，如float、int、str、tuple
###### 字典方法
- `D.clear()`
- `D.copy() #a shallow copy of D`
- `D.get(key[,d])`
- `D.fromkeys(iterable, value=None, /)`
- `D.items()`
- `D.keys()`
- `D.pop(key)`
- `D.popitem() #弹出最后一个`
- `D.setdefault()`
- `D.update()`
- `D.values()`
---
### 集合set
- 一般方法
    ```python
    set(iter)
    ```
- 创建不可变集合
    ```python
    S = frozenset(obj)
    ```
###### set方法
- `Set.add()`
- `Set.clear()`
- `Set.copy()`
- `Set.difference(S1) #补集` 或`Set - S1`
- `Set.difference_update()`
- `Set.discard()`
- `Set.intersection()`
- `Set.intersection_update()`
- `Set.isdisjoint()`
- `Set.issubset()`
- `Set.issuperset()`
- `Set.pop() #从集合中删除并返回任意元素。`
- `Set.remove()`
- `Set.symmetric_difference(S1) #即(Set-S1)U(S1-Set)`
- `Set.symmetric_difference_update()`
- `Set.union()`
- `Set.update(S1) #把集合S1元素并入Set`

###### 集合关系
- `==`
- `!=`
- `in`
---

### 条件语句
> - 被视为false：False、None、0、''、()、{}、[]（注意它们本身不相等）
> - 判断bool类型`bool(obj)`
###### if语句
- if的三元操作符
    ```python
    Z if X else Y #若X为真，则Z，否则Y
    ```
- if语法
    ```python
    if expression:
        suite
    elif expression:
        suite
    ...
    else:
        suite
    ```

###### assert用法
`assert A`:如果A为真，则不输出任何结果，如果为假则报错。

------
### 循环语句
###### while循环
```python
while expression:
    suite
else:
    suite
```
###### for循环
```Python
for target_list in expression_list :
    suite
else:
    suite
```
###### zip函数
```Python
zip(iter1 [,iter2 [...]]) --> zip object
```
> 返回zip类型，可用`next()`读取，或者使用`list()`、`tuple()`转换

```Python
zip(*zip(iter1 [,iter2 [...]])) #得到iter1，iter2，...但类型是tuple
```

###### 特殊对象的循环
1. 字典dict
    ```Python
    knights = {'gallahad': 'the pure', 'robin': 'the brave'}
    for k, v in knights.items():
        print(k, v)
    ```
2. 列表list
    ```Python
    for i, v in enumerate(['tic', 'tac', 'toe']):
        print(i, v)
    ```
3. zip
    ```Python
    questions = ['name', 'quest', 'favorite color']
    answers = ['lancelot', 'the holy grail', 'blue']
    for q, a in zip(questions, answers):
        print('What is your {0}?  It is {1}.'.format(q, a))
    ```


### 函数
##### 内置函数

[所有内置函数](https://docs.python.org/3/library/functions.html)

内置函数可以直接使用即可。

##### 自定义函数
```Python
def funcname([parameter_list]):
     suite
     return obj
```



- 定义空函数
    ```Python
    def funcname([parameter_list]):
         pass
    ```

> 注：
> - 可用变量指向函数，相当于该函数的别名，如
>   ```Python
>   a = abs   
>   a(-1)  #等同于abs(-1)
>   ```
> - 可将函数指向其他对象，但之后该函数将不可用（实际不能这样操作）
> - 遇到return语句，函数就会终止
> - 没有返回值，可写`return None`或`return`
> - 如果没有return语句，默认返回None
> - 定义函数时，可进行参数检查`isinstance(obj,type)`
> - 可以返回多个值，但其实是返回一个tuple

###### 函数的参数
-  参数的写法
`func(positional_args,keyword_args,*typle_nonkw_args,**dict_kw_args)`

- 参数的传递
    - 位置传递：按照位置依次传入，如位置参数
    - 关键字传递：声明默认值的参数，如默认参数
        - 有参数名：按照参数名传递
        - 无参数名：按照位置传递，同位置参数
        - 参数默认值一定要指向不可变对象，如需用到list，可改为：
            ```python
            if L is None:
                L = []
            ```
    - 包裹传递：传递不定数量的参数组
        - 包裹位置参数：`func(*typle_nonkw_args)`
            1. 调用时，收集实参自动包裹成tuple
            2. （解包）先组装list/tuple再传入，但需要加`*`，如：
                ```python
                def func(*args):
                    pass

                num = [1,2,3]
                func(*num)
                ```    
        - 包裹位置参数： `func(**dict_kw_args)`
            1. 任意数量参数封装成dict，允许参数缺失&无序
            2. （解包）先组装dict再传入，但需要加`**`，如：
                ```python
                def func(**kw):
                    pass

                num = {k1:v1,k2:v2,k3:v3]
                func(**num)
                ```

        - 解包操作：形如`def func(*args,**kw)`
            - 首先拆解`args`，按顺序传给位置参数、默认参数、可变参数，然后拆解`**kw`，传给关键字参数。
            - packing是定义函数时使用，uupacking是调用函数时使用，两者相互独立，并非相反。
    - 参数传递形式
        - 值传递：变量传递给函数后，函数在内存中复制一个新变量在函数中使用，不影响原有变量
        - 指针传递：变量传递给函数的是指针，指向list在内存中的位置，在函数中对list进行操作，会改变原有变量。
        - 参数检查
        ```python
        # 基本数据类型值传递
        a= 1
        def change_integer(a):
                a=a+1
                return a

        print (change_integer(a))
        print (a)
        # list类型指针传递
        b= [1, 2, 3]
        def change_list(b):
                b[0]= b[0]+1
                return b

        print (change_list(b))
        print (b)
        ```



1. 位置参数`positional_args`
    ```Python
    def power(x)      #x是位置参数，按照位置传递参数
	def power(x,n)    #按照x,n的位置传递参数
    ```
2. 默认参数`keyword_args`
    ```Python
    def power(x,n=2)
    ```
    > - n默认为2，相当于调用power(x,2)
    > - 当输入power(3,4)时，4就传入n替换掉n=2
    > - 默认参数当作是缺省值
    > - 注意：
    >   - 必须参数在前，默认参数在后，否则报错
    >   - 当函数有多个参数时，将变化大的参数放在前面，变化小的放在后面
    >   - 调用时，默认参数可以省略，只有当默认参数不符时才需提供
    >   - 也可不按参数顺序调用，但需要把参数名写上
    >   - 默认参数必须指向不变对象，当是list等可变对象时需注意，不变对象如None，str，例子：
    >        ```Python
    >       def add_end(L=[]):
    >          L.append('END')
    >           return L
    >
    >        add_end()
    >        add_end()
    >        add_end() #多试几次
    >        ```

3. 可变参数（收集参数）`*typle_nonkw_args`
    ```Python   
    def calc(*num)    #将num作为可变参数传进去，将list或tuple中的每个元素都传进去，0个或任意个参数
    ```
    - 不加*可以是列表或元组，例如
        ```Python
        def calc(num):
        	sum = 0
        	for n  in num:
        		sum = sum +n * n
        	return sum

        print(calc((1,2,3,4)))#或print(calc([1,2,3,4]))		
        ```			  
	- 加*可以直接传入参数值，如
        ```Python
    	def calc(*num):
    		sum = 0
    		for n  in num:
    			sum = sum +n * n
    		return sum

    	print(calc(1,2,3,4))  #函数在调用时自动组装成tuple  
        ```
	- 如果已有list或者tuple，在list或tuple前加`*`可以把list或tuple中的元素变成可变参数传进去,如：
        ```Python
        num = [1,2,3]
        calc(*num) #*是一个序列解包操作
        ```

4. 关键字参数`**dict_kw_args`
    关键字参数允许传入0个或任意个含参数名的参数，这些关键字参数在函数内部自动组装成一个dict.
    如：
    ```python
    def person(name, age, **kw):     #kw是关键字参数
        print('name:',name, 'age:',age, 'other:' kw)

    person('Mike', 30)
    name:Mike age:30 other: {}

    person('Lily', 35, city = 'Beijing')   #也可以传入任意个数的关键字参数
    name:Lily age:35 other: {'city' : 'Beijing'}
    ```
    关键字参数的作用在于，可以调用必须信息，并且可以拓展其他信息。

    也可以把`dict`转化为关键字参数传进去，如：
    ```python
    extra=｛'city' : "BJ", 'job' : 'Dr'｝

    person('jack', 24, city=extra['city'],job= extra['job'])
    或
    person('jack', 24, **extra)#**extra是把extra 这个dict中的所有key-value用关键字参数传入到函数**kw参数，kw获得一个dict
    ```
5. 命名关键字参数
    用`*,`分隔，限制关键字的名字，如：
    ```python
    def person(name, age,*, city, job): #*后面的参数被视为命名关键字参数，只接受city和job作为关键字参数
        print(name,age,city,job)
    ```
    - 命名关键字参数必须传入参数名，如果没有传入参数名，调用将会报错。
    - 命名关键字参数可以有缺省值，当存在缺省值时，调用时可以不传入。如：
        ```python
        def person(name,age,*, city = "BJ", job):
            print(name,age, city, job)
        person("Jack", 24, job="Dr")
        ```
6. 参数组合
    - 可变参数和命名关键字参数不能混合；其他5种参数类型均可以组合使用。如：
        ```python
        def f1(a,b,c=0,*d,**e):
            print ('a=',a,'b=',b,'c=',c,'d=',d,'e=',e)

        def f2(a,b,c=0,*,d,**e):
            print ('a=',a,'b=',b,'c=',c,'d=',d,'e=',e)
        ```
    - 任意函数都是可以通过类似`func(*args,**kw)`的形式调用，无论其参数是如何定义的。如：
        ```python
        >>> args = (1, 2, 3, 4)
        >>> kw = {'d': 99, 'x': '#'}
        >>> f1(*args, **kw)
        a = 1 b = 2 c = 3 args = (4,) kw = {'d': 99, 'x': '#'}
        >>> args = (1, 2, 3)
        >>> kw = {'d': 88, 'x': '#'}
        >>> f2(*args, **kw)
        a = 1 b = 2 c = 3 d = 88 kw = {'x': '#'}
        ```

> 总结：
> - 可变参数和关键字参数的习惯语法格式：
> 	- `*args`是可变参数，`args`接收的是一个`tuple`；
> 	- `**kw`是关键字参数，`kw`接收的是一个`dict`。
> - 函数调用时传入可变参数和关键字参数的语法：
>   - 可变参数既可以直接传入：`func(1,2,3)`,又可以先组装`list`或`tuple`，再通过`*args`传入：`func(*(1,2,3))`;
> 	- 关键字参数既可以直接传入：`func(a=1, b=2)`,又可以先组装`dict`，再通过`**kw`传入：`func(**{'a':1,'b':2})`


##### 变量作用域
- 全局变量：
    - 除非被删除，否则存活到程序运行结束。
    - 函数内可以使用，但要在`=`后，不能修改，除非声明`global`。
- 局部变量
    - 只允许函数内部使用
    - 存活状态依赖于函数是否被执行。
    - 函数内部局部变量会隐藏全局变量。
##### 递归函数
- 函数调用其本身称为**递归**。如：
    ```python
    def fact(n):#计算阶乘
    	if n==1:
    		return 1
    	return n * fact(n - 1)
    ```
    > 使用递归函数时需要注意防止栈溢出，函数的调用是通过栈（Stack）来实现的，每当进入一个函数调用，栈就会加一层栈帧，每当函数返回时，栈就会减一层栈帧，递归调用的次数过多，就会导致栈溢出。其解决方法是通过尾递归优化
    > 尾递归：在函数返回时，调用自身，且`return`语句不能包含表达式，尾递归与循环的效果是等价的
     ```python
     def fact(n):
     	return fact_iter(n,1)

     def fact_iter(num,product):
     	if num ==1:
     		return product
     	return fact_iter(num - 1, num * product)
     ```


##### 函数式编程
> 函数式编程是一种编程范式，属于结构化编程，采用子程序，程式码区块，`for`或`while`循环。  
> 其思想时把运算过程尽量写成一系列嵌套的函数调用。
> 允许把函数作为参数传入另一个函数，如高阶函数；或返回一个函数。
> python不是函数式编程语言，但支持一些函数式编程语言的构建，如匿名函数、内置函数`map`、`filter`和偏函数；其本质是通过封装对象实现函数式编程。



- 匿名函数`lambda`
    - 表达式：同一行定义体+声明，不用写`return`
        ```Python
        lambda arg1,arg2,...:expression
        ```
    - 用法
        - 赋值给一个变量`a = lambda x,y: x+y`
            > 其含义是：`lambda`生成一个函数对象，参数为`x,y`，返回值为`x+y`,函数对象赋给`a`
        - 作为函数的返回值返回
            ```Python
            def a(x,y):
                return lambda :x*x+y*y

            print(a(1,2)())
            ```
- 高阶函数
将函数作为另一个函数的参数传入。可与`lambda`结合。
    - 一般性
        ```Python
        def f(a):
            if a >= 0:
                pass
            else:
                a = -a
            return a

        def add(x, y, f):
            return f(x) + f(y)
        ```
    - `filter(function or None,iterable)`：将函数对象依次作用于每个元素，根据返回值是`True`或`False`决定保留还是丢弃该元素。
    - `map(func,*iterable)`：将函数对象依次作用于每个元素，每次作用的结果存储于返回的list中，可以有n个列表（`*`的用途），对应于n个参数。
    - `reduce(function,iterable[,init])`:
        - `function`是一个二元函数，接受两个参数，一个接收上一次的返回值/结果，另一个接收序列下一个元素。
        - `init`是初始化器，可缺省
        - 需要`from functools import reduce`

##### 偏函数
将一个函数的某些参数固定住，并返回一个新的函数。
```python
from functools import partial
new_function = partial(function,*args,**kw)
```
> 可固定位置参数或重设关键字参数，如：`add1 = partial(add,1)`、`int2(1) = partial(int,base=2)`




##### 装饰器Decorator


##### 闭包
闭包是一个函数，其特点是：
- 定义在另一个函数里面（嵌套函数）
- 引用其所在的函数环境的自由变量
- 装饰器是一个闭包，是一个嵌套函数


### 生成器generator
###### 列表生成式(不是生成器)
- `a = [i * i for i in range(5)] #列表生成式，输出一个list`
- `[x * x for x in range(1, 11) if x % 2 == 0]`
- `[m + n for m in 'ABC' for n in 'XYZ']`
```python
>>> d = {'x': 'A', 'y': 'B', 'z': 'C' }
>>> [k + '=' + v for k, v in d.items()]
['y=B', 'x=A', 'z=C']
```
```python
>>> L = ['Hello', 'World', 'IBM', 'Apple']
>>> [s.lower() for s in L]
['hello', 'world', 'ibm', 'apple']
```

###### 生成器表达式(generator expression)
`a = (i * i for i in range(5)) #输出一个generator`
- 可使用`next()`获取generator的下一个元素，没有元素时会报错（一般不使用该方法）
- 也可使用for循环依次打印出来（一般使用该方法）

###### 生成器函数generator function
如果一个函数定义中包含`yield`关键字，那么这个函数就不再是一个普通函数，而是一个 generator function

- 生成器方法
    - `send()` 接收外部变量，并根据变量内容计算结果后返回
    - `close()` 手动关闭生成器函数，关闭之后后面不能再运行，否则会产生StopIteration异常
    - `throw()` 向生成器送入一个异常，


###### 迭代器iterator
凡是可以被`next()`函数调用并不断返回下一个值的对象称为迭代器，生成器就是一个迭代器。
迭代器表示的是一个数据流，可以是一个有序序列，但不能提前知道序列的长度，甚至是无限序列。
- 判断一个对象是否是Iterator：
    ```python
    >>> from collections import Iterator
    >>> isinstance((x for x in range(10)), Iterator)
    True
    >>> isinstance([], Iterator)
    False
    >>> isinstance({}, Iterator)
    False
    >>> isinstance('abc', Iterator)
    False
    ```

- 可迭代对象iterable
凡是可作用于 for 循环的对象都是 Iterable 类型。可使用`iter()`将Iterable转换成Iterator
    - 一类是集合数据类型，如 list 、 tuple 、 dict 、 set 、 str 等；
    - 一类是 generator ，包括生成器和带 yield 的 generator function

    > 大部分对象都是可迭代，只要实现了__iter__方法的对象就是可迭代的。如：
    >    ```Python
    >    >>> lst = [1,2,3]
    >    >>> lst.__iter__()
    >    <listiterator object at 0x7f97c549aa50>
    >    ```
    - 判断对象是否可迭代
    ```Python
    >>> from collections import Iterable
    >>> isinstance('abc',Iterable)
    ```

- 容器container
    容器是一种把多个元素组织在一起的数据结构，容器中的元素可以逐个地迭代获取，可以用in, not in关键字判断元素是否包含在容器中。当它可以用来询问某个元素是否包含在其中时，那么这个对象就可以认为是一个容器，比如 list，set，tuple，dict都是容器对象。

    尽管绝大多数容器都提供了某种方式来获取其中的每一个元素，但这并不是容器本身提供的能力，而是可迭代对象赋予了容器这种能力，当然并不是所有的容器都是可迭代的，比如：Bloom filter，虽然Bloom filter可以用来检测某个元素是否包含在容器中，但是并不能从容器中获取其中的每一个值，因为Bloom filter压根就没把元素存储在容器中，而是通过一个散列函数映射成一个值保存在数组中。




### 类和对象
面向对象的特征：
1、封装（信息隐蔽）
2、继承（子类自动继承父类的特征）
3、多态（不同对象对同一方法响应不同的行动或不同类的对象使用相同的操作）


对象=属性（静态）+方法（动态）

python类名用大写字母开头


面向对象编程
1、`self`（相当于C++的this指针）（相同外观的房子的不同门牌号）
2、`__init__(self)`
3、公有和私有（Python中没有权限的，但是可以运用一定的写法将其私有）
将双下横线表示成`类名\__变量名`（前面单下横线，后面双下横线）


### 异常检测与处理
###### 异常类型

###### 异常检测
- 异常检测方式1：
```Python
try：
    检测范围
except Exception [ as reason ]： // Exception处填写异常名
    出现异常（Exception）后的处理代码
```
- 异常检测方式2：
```Python
try：
    检测范围
except Exception [ as reason ]： // Exception处填写异常名
    出现异常（Exception）后的处理代码
finally：
    无论如何都会执行的代码
```
- 异常检测方式3：
```Python
try：
    检测范围
except Exception [ as reason ]： // Exception处填写异常名
    出现异常（Exception）后的处理代码
else：
    没有出现异常的代码
```







### 常用模块
