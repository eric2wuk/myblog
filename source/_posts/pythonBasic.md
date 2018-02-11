---
title: pythonBasic
date: 2018-02-02 17:15:04
categories: [python]
tags: [python]
---

### pyton review
* 学习指南 https://www.zhihu.com/question/29138020
  - https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000
* 运行
  - 在Windows上运行Python时，请先启动命令行，然后运行python。
  - 在Mac和Linux上运行Python时，请打开终端，然后运行python3。(本身有Python2版本文件, 为区分)
* python 为解释型语言
* 解释器种类
  - 默认为CPython,
  - IPython 基于CPython
  - PyPy追求执行速度执行动态编译 与CPythin可能相同代码不同执行结果
  - Jython 运行于Java平台的Python解释器,编译Python代码为Java字节码
  - IronPython运行于.Net
* 可以直接 命令行中 python hello.py 执行python文件 hello.py
<!----more--->
* Mac与Linux可以直接运行.py文件, win不行需要在文件第一行, 还要命令给文件已执行权限chmod a+x hello.py
  ```python
  #!/usr/bin/env python3
  ```
* print()可接受多个字符串, 用逗号','隔开输出连接逗号转变成空格
* input()输入, input('please enter your name:')参数是友好提示
* 数字 十六进制0xff00, 浮点数 1.23e-8,计算机由于使用二进制，所以，有时候用十六进制表示整数比较方便，十六进制用0x前缀和0-9，a-f表示，例如：0xff00，0xa5b4c3d2，等等。
* 字符串 r''内部字符串不转义
* print('''...''')格式表示多行内容与r'''...'''可组合使用
  - ``` python3
    print('''line1
    ... line2
    ... line3''')
    line1
    line2
    line3
    ```
* boolean值 True,False , 可用 and, or , not 运算
* None值
* /浮点除, // 地板除, %取余 10/3  浮点型 10//3 整数 除地板
* 编码ASCII,Unicode,为传输存储速度发明了可变长编码UTF-8, A 65, a 97, 0 48
* python字符串
  - python 字符串 ord('A') chr(20013), 也可以十六进制直接写出'\u0030'
  - 'dkjKJDFL'.lower(), 'adf'.upper()
  - b'ABC'直接转化为bytes,非单字节字符, 需用'中文'.encode('utf-8');
  - 如果encode无法显示为ASCII,用\x##表示, 字节流转义用 decode()
   ```python3
   b'\xe4\xb8\xad\xe6\x96\x87'.decode('utf-8')
   ```
  - 计算字符长度len('中文'),用转换为bytes.len()可计算字节数
  - 为避免编码问题,保存源码指定保存为UTF-8编码读取, 通常在文件开头写入
    ```python3
    #!/usr/bin/env python3
    # -*- coding: utf-8 -*-
    ```
    - 格式化占位符用% 'hello, %s' % 'world',  顺序对应%s替换字符串, %d替换整数 %f浮点数 %x 十六进制整数, %%转义为%, 可定义整数补零位数%05d, 浮点数小数点后保留位数%.3f
     ```python3
       'Hi, %s, you have $%d.' % ('Michael', 1000000)
      'Hi, Michael, you have $1000000.'
      ```
* list
  - 定义 classmates = ['eric','eric2','eric3']
  - 访问 classmats[1], 最后一个元素下标 len(classmates)-1
  - 添加元素, classmates.apppend('eric4'), classmates.insert(1,'Jack')
  - 删除元素, classmates.pop(), 指定下标 classmates.pop(2)
  - 内含元素可以不同类型
* tuple
  - 一旦定义不可修改 tp = ('eric','eric2','eric3')
  - 定义 可简化(), 多变量可接收 tuple值,按位置赋值
  - 访问操作相同 tp[1]
  - ps: 一个元素(1), 括号优先为规避此问题, 一个元素 加逗号(1,)
* 分支结构判断
  ```python
    a = 100
    if a>=0:
      print(a)
    elif a>-10:
      print(a)
    else:
      print(-a)
  ```
* if x: 只要x为非零数值, 非空字符串, 非空list等, 就判断为True, 否则为False
* 提供int()用于转int型
* 循环结构
  - 简单 for name in classmates: print(name), 遍历集合数组
  - list(range(101)),生成[0,1,2,3,...100]
  - while n > 0: n = n + 2
* dict
  - 定义 d = {'eric':0,'eric2':2, 'eric3':3}
  - 访问 d['eric2'],
  - 判断元素, 访问不存在会报错, 可以在访问前, 判断元素 'eric' in d, 返回 boolean, d.get('eric')存在返回value不存在返回None(ps: 返回值为None时交互命令行不显示结果), 或者自己指定的返回值, d.get('eric',-1)
  - 添加元素 d['eric4'] = 4, 存在原元素则进行替换
  - 删除元素, d.pop('eric2') 同时返回value
* set 不重复 是一组key的集合, 不储存value, key不重复
  - 定义 s = {1,2,3,3,3,3,4,5} s = {1,2,3,4,5}
    ```python3
    > s = set([1,2,3,3,4,5])
    > s
    > {1,2,3,4,5}
    ```
  - 添加元素 s.add(6), 重复添加无效果
  - 删除元素 s.remove(key)
  - set可以做数学意义上的交并集操作 s1 & s2, s1 | s2

* 调用函数 abs(22), int('22'), hex(22), bool(22)
* 定义函数 def my_abs(x):
  - 如果定义一个什么也不做的空函数, 可以用pass语句,缺少pass运行有语法错误
    ```python3
     def nop():
         pass
    ```
  - 当没有return语句时, 函数执行结束也会返回结果, 结果为None,
  - return None, 可简化为return
  - 函数可返回多个值
    > return nx, my, x,y = move(100,100,60, math.pi/6)

    Ps:返回多个值实际为假象, 多个值打包为tuple, 语法上返回一个tuple可以省略括号, 多个标量接受tuple, 按位置赋值, 对书写的简化
  - math.pi, math.sqrt, math.pow
* 数据类型检查 isinstance(obj, class_or_tuple) 抛出异常
  > raise TypeError('bad operand type')

* 函数的参数
  - 位置参数, 对参数提供默认值, 则是默认参数Ps: 默认参数在必选参数后, 调用函数时, 不按照位置, 需要提供参数名Ps2: 默认参数必须是不可变对象, 否则默认参数可能改变
  - 可变参数
    ```python3
    def sum(*num):
    sum(3,4,5,6), sum(*[2,3,4])
    ```
  - 关键字参数 传入多个, 内部整合为dict
  - 命名关键词参数, 命名关键词需要一个特殊的分隔符\*, 有可变参数, 后面为命名关键词参数不再需要分隔符\*
  - 参数组合顺序, 必选参数, 默认参数, 可变参数,  命名关键词参数, 关键词参数
  - 方法调用传参可通过func(\*args,\*\*kw), \*args是可变参数，args接收的是一个tuple；\*\*kw是关键字参数，kw接收的是一个dict。以及调用函数时如何传入可变参数和关键字参数的语法：可变参数既可以直接传入：func(1, 2, 3)，又可以先组装list或tuple，再通过\*args传入：func(\*(1, 2, 3))；关键字参数既可以直接传入：func(a=1, b=2)，又可以先组装dict，再通过\*\*kw传入：func(\*\*{'a': 1, 'b': 2})。使用\*args和\*\*kw是Python的习惯写法，当然也可以用其他参数名，但最好使用习惯用法。
* 递归函数
  - 调用本身, 注意递归结束条件
  - 尾递归与循环等价, 对尾递归优化可以解决栈溢出问题
* 切片
  - 切片取前三个元素L[start\:end\:n],Ps: 第一个元素为0可省略,第二个元素默认为最后一个元素,第三个元素指n元素取1含头不含尾
  - tuple 切片操作返回tuple
  - string 切片返回string
  - -1为最后一个元素
* 列表生成式
  - list(range(4,10))
  - [x\*x for x in range(1,11)]
  - 可以循环嵌套, 生成全排列 [m + n for m in 'ABC' for n in 'XYZ']
  - 可以多变量生成列表生成器 [k + '=' + v for k,v in d.items()]
* isinstance(obj, class_or_tuple) 判断变量类型
* 生成器 generator
  - 定义 列表生成器 [] 换为()
  - 获取 next(iterator[,default])
  - 遍历 for n in g:
  - 多变量赋值 a,b = b, a+b 相当于省略临时变量
  ```python3
    t = (b,a+b)
    a = t[0]
    b = t[1]
  ```
  - 可以用函数作为generator, 如果函数包含yield关键词, 那么函数将不再是普通函数, 而是一个generator, generator在调用next()的时候执行, 遇到yield语句返回, 再次执行从上次yield语句出继续执行
* 迭代器 Iterable, from collections import Iterable
  - 可以用 isinstance函数判断
  - 生成器为Iterator对象, 但list,dict,str 虽然是Iterable, 却不是Iterator
  - Iterator 对象表示的是一个数据流, next()函数函数调用返回下一个数据,Iterator计算是惰性的,
  - 凡是可作用于for 循环的对象都是Iterable类型:
  - 凡是可作用于next()函数的对象都是Iterator类型, 他们表示一个惰性计算序列;
  - 集合类型, 可以通过iter()函数获得一个Iterator对象
* 函数式编程
  - 函数编程是一种抽象程度很高的编程范式, 纯粹的函数式编程函数没有变量, 因此, 只要输入是确定的, 输出就是确定的,
  - 函数式编程特点, 可以允许把函数本身作为参数传入另一个函数, 还允许返回一个函数
  - python对函数式编程部分支持, 由于Python允许使用变量, 因此Python不是纯函数式编程语言
* 高阶函数: 变量可以指向函数, 一个函数可以接收另一个函数作为参数, 这样的函数就称之为高阶函数, 函数式编程指这种高度抽象的编程范式
* 递归是对问题的描述, 循环是对问题的求解, 相当于方程组和计算式的关系
  - 线性递归, 树形递归, 尾递归(可优化为循环)
* map : map(func, \*iterables) --> map object
* reduce : map(fucntion, sequence[,initial]) --> value
* filter : filter(function or None , iterable) --> filter object
  - 求素数, 先定义一个生成器, 埃氏筛法, 不断嵌套filter, 筛选下一个素数
* sorted : sorted(iterable, key=None, reverse=False)
  - key 是提供一个映射关系, 对原值进行映射, 返回结果, 以返回结果排序对原值进行排序
* 返回函数 以函数作为返回值, lazy_sum 闭包结构
  - 返回一个函数时, 牢记该函数并未执行 返回的函数中不要引入任何可能变化的变量
* lambda x,y : x*10+y
  - 只能有一个表达式, 不用写return, 返回值就是该表达式的结果
  - 匿名函数也是函数对象, 可以复制给一个变量, 再用变量来调用该函数
  - 匿名函数也是函数对象, 也可以作为返回值
  - python支持有限, 只有一些简单情况可以使用
* 10**3 = 1000, 代表幂计算
* 装饰器 : 在运行期间动态增加功能, 又不修改原函数的定义, 这种方式我们称之为装饰器(Decorator)
  - 函数对象可以被赋值给其他变量, \_\_name\_\_可以拿到函数原名
  - \@语法 log定义在now函数上,相当于log(now),
  ```python3
  def log(func):
  def wrapper(*args, **kw):
      print('call %s():' % func.__name__)
      return func(*args, **kw)
  return wrapper
  ```
  -  多一层\@log('eric'), 相当于 log('eric')(now)
    ```python3
    def log(text):
    def decorator(func):
        def wrapper(*args, **kw):
            print('%s %s():' % (text, func.__name__))
            return func(*args, **kw)
        return wrapper
    return decorator
    ```
    - 解决\_\_name\_\_变为wrapper, import functools 使用@functionls.wraps(func)
* 偏函数 是引入已有方法, 创建一个新函数可以固定住原函数的部分参数, 从而使调用时更简单
  - import functools
  - int2 = functools.partial(int, base=2)
  - help : partial(func, \*args, \*\*keywords) - new function with partial application of the given arguments and keywords.
* 模块
  - 按目录组织模块, 包Package
  - 包中有一个\_\_init\_\_.py文件, 这个文件必须存在, 否则Python就会把这个目录当成普通目录, 而不是一个包, 这个文件可以是空文件, 也可以有Python代码, 因为\_\_init\_\_本身就是一个模块, 而模块名就是包名
  - 可以有多级目录, 组成多级层次包结构
  - 注意不要和Python自带模块名冲突
* 使用模块
  - sys模块, 内部argv变量, 存储命令行参数, python hello.py 获得的 sys.argv就是['hello.py'];, 运行python hello.py Eric 获得的sys.argv就是['hello.py','Eric']
  - if \_\_name\_\_ == '\_\_main\_\_':test(), 当我们命令行运行hello模块式, Python解释器将一个特殊变量\_\_name\_\_置为\_\_main\_\_,而其他地方导入hello模块, if判断将失败, 因此, 这种if测试可以让一个模块通过命令行运行时执行一些额外代码, 最常见就是用于运行测试
  - 作用域
    - abc, x123, PI 为public
    - \_xxx, \_\_xxx为非公开(private),
    - \_\_name\_\_等为特殊变量, 可以直接引用, 但是有特殊用途,\_\_author\_\_,文档注释可以用\_\_doc\_\_访问等
* 第三库
  - 通过pip来下载 , pip 软件包管理系统
  - pip --version
  - pip install Pillow,pip install some-package-name
  - pip uninstall some-package-name
  - 加载模块, Python在指定路径下搜索对于.py文件, 找不到,就报错
    - 默认搜索当前目录, 所有已安装内置模块和第三方模块, 搜索路径存放于sys模块path变量
    ```python3
      import sys
      sys.path
    ```
    - 可修改sys.path
      - > sys.paht.append('/u...'), 运行时生效, 运行结束后失效
      - 修改环境变量PYTHONPATH, 永久修改
* 面向对象编程 数据封装, 继承, 多态
  - \_\_init\_\_为特殊实例化方法, 可以在创建实例时将认为必须绑定的数据强制写进去
  - class Student(object) , 括号内时父类继承类, 默认object
  - class 内方法, 第一个参数为对象本身
  - 与静态语言不通, Python允许对实例对象绑定任何数据, 也就是说, 对于两个实例变量, 虽然他们都是一个类的不同实例, 但拥有的变量名称可能不同
* 访问限制
  - 双下划线前缀代表private变量, 而单下划线前缀的实例变量外部时可以访问的, 但是, 按照约定俗称的规定, 当你看到这样的变量时, 意思是, '虽然我可以被访问, 但是, 请把我视为私有变量, 不要随意访问'
  - 双下划线不能直接访问, 是因为Python解释器对外将Student类, 将\_\_name变量改成了\_Student\_\_name, 所以仍然可以通过改变后的变量名访问到,但不要这样做, 不同版本解释器变量名可能不同
  - 表面上看，外部代码“成功”地设置了\_\_name变量，但实际上这个\_\_name变量和class内部的\_\_name变量不是一个变量！内部的\_\_name变量已经被Python解释器自动改成了\_Student\_\_name，而外部代码给bart新增了一个\_\_name变量
  - Python本身没有有效高强制的访问限制, 需要自觉遵守规范
  - 私有变量, get set方法
* 继承 Animal(object) Cat(Animal) Dog(Animal)
  - 获得父类方法
  - 多态 对父类方法改进
  - 静态语言和动态语言,对于静态语言（例如Java）来说，如果需要传入Animal类型，则传入的对象必须是Animal类型或者它的子类，否则，将无法调用run()方法。对于Python这样的动态语言来说，则不一定需要传入Animal类型。我们只需要保证传入的对象有一个run()方法就可以了：
* 获取对象信息
  - type help : type(object) -> the object's type
  - isinstance help : isinstance(obj, class_or_tuple) -> return whether an object is an instance of a class or of a subclass thereof
  - dir help : dir([object]) -> list of strings, If called without an argument, return the names in the current scope. Else, return an alphabetized list of names comprising (some of) the attributes of the given object, and of attributes of the given object, and of attributes reachable from it.
  - 类似__xxx__的属性和方法在Python中都是有特殊用途的，比如__len__方法返回长度。在Python中，如果你调用len()函数试图获取一个对象的长度，实际上，在len()函数内部，它自动去调用该对象的__len__()方法,我们自己写的类，如果也想用len(myObj)的话，就自己写一个__len__()方法：
  - 也可以把一个对象的方法赋予一个变量
  - 可以用getattr(), setattr()以及hasattr()直接对一个对象的状态进行操作
  - 通过内置一系列函数, 我们可以对任意一个Python对象进行读取, 拿到其内部的数据. 要注意的是, 只有不知道对象信息的时候, 我们才会去获取对象的信息. 如果知道可以直接写:  而不是下面第二种写法
    ```python3
      > sum = obj.x + obj.y
      > sum = getattr(obj, 'x') + getattr(obj,'y')
    ```
    >对象未知时先判断, 鸭子类型

    ```python3
    def readImage(fp):
        if hasattr(fp, 'read')
            return readData(fp)
        return None
    ```
* 实例属性和类属性
  - self. 为实例属性, 写在class中的为类属性
  - 相同名字的实例树形将屏蔽类属性, 但是当你删除实例属性后, 在使用相同的名称, 访问到的将是类属性
  - 同名属性实例属性优先级高
  - 删除 属性
    >del ss.name

* 面向对象高级 多重继承, 定制类, 元类
* 可动态绑定方法, 为实例绑定方法 instance
  ```python3
  from types import MethodType
  s.set_age = MethodType(set_age, s)
  ```
* 为了给所有实例绑定的方法, 可以给class绑定方法
  ```python3
  Student.set_score = set_score
  ```
* 限制实例属性
  ```python3
  class Student(object):
      __slots__ = ('name','age')
  ```
  - slots 定义的属性只对当前class的instance 起作用, 对集成的子类是不起作用的
  - 子类也定义\_\_slots\_\_, 这样子类实例可以定义的属性就是自身的\_\_slots\_\_加上父类的\_\_slots\_\_.
* \@property 对对象属性, 便捷性和控制的解决方案
  - 为检查参数, 设置get, set方法, 属性设为私有
  - 但调用方法又略显复杂，没有直接用属性这么直接简单
  ```python3
  class Student(object):

    @property
    def score(self):
        return self._score

    @score.setter
    def score(self, value):
        if not isinstance(value, int):
            raise ValueError('score must be an integer!')
        if value < 0 or value > 100:
            raise ValueError('score must between 0 ~ 100!')
        self._score = value
  ```
  - \@property的实现比较复杂，我们先考察如何使用。把一个getter方法变成属性，只需要加上@property就可以了，此时，\@property本身又创建了另一个装饰器\@score.setter，负责把一个setter方法变成属性赋值，于是，我们就拥有一个可控的属性操作
  ```python3
  >>> s = Student()
  >>> s.score = 60 # OK，实际转化为s.set_score(60)
  >>> s.score # OK，实际转化为s.get_score()
  60
  >>> s.score = 9999
  Traceback (most recent call last):
    ...
  ValueError: score must between 0 ~ 100!
  ```
* 多重继承 MixIn
  - class Dog(Mammal, Runnable):
  - 由于Python允许使用多重继承，因此，MixIn就是一种常见的设计。只允许单一继承的语言（如Java）不能使用MixIn的设计
  - 多继承的好处在于不需要复杂而庞大的继承链, 只要选择组合不同的类的功能, 就可以快速构造出所需的子类
  - 多继承, 顺序C3算法, MRO算法计算优先级序列
  - 本地优先级: 指生命父类的顺序, 比如C(A,B), 如果访问C类对象属性时, 应该根据声明顺序, 优先查找A类, 然后再查找B类.
  - 单调性: 如果在C的解析顺序中, A排在B的前面, 那么在C的所有子类里, 也必须满足这个顺序
  - 如果继承至多个基类 class B(A1,A2,A3 ...), 这时B的mro序列 mro(B) = [B] + merge(mro(A1), mro(A2), mro(A3) ..., [A1,A2,A3])
  - merge操作就是C3算法的核心。遍历执行merge操作的序列，如果一个序列的第一个元素，在其他序列中也是第一个元素，或不在其他序列出现，则从所有执行merge操作序列中删除这个元素，合并到当前的mro中。merge操作后的序列，继续执行merge操作，直到merge操作的序列为空。如果merge操作的序列无法为空，则说明不合法。
  -[E]+ merge([A,D,O],[B,O],[C,D,O],[D,O],[A,B,C,D]) = [E,A,B,C,D]
  * 定制类
    - \_\_str\_\_  , 相当于java, toString print时 打印自己定制的信息
    - \_\_repr\_\_ , 直接敲变量不用print,还是不好看, 这是因为直接显示变量对用的不是\_\_str\_\_返回用户看到的字符串, 而\_\_repr\_\_ 返回程序开发者看到的字符串, 就是说, \_\_repr\_\_()是为调试服务的
    - \_\_iter\_\_ , \_\_next\_\_如果一个类想被用于for ... in循环，类似list或tuple那样，就必须实现一个__iter__()方法，该方法返回一个迭代对象，然后，Python的for循环就会不断调用该迭代对象的__next__()方法拿到循环的下一个值，直到遇到StopIteration错误时退出循环。
      ```python3
      class Fib(object):
        	def __init__(self):
        		self.a, self.b = 0,1

        	def __iter__(self):
        		return self # 实例对象本身就是迭代对象

        	def __next__(self):
        		self.a, self.b = self.b, self.a +self.b
        		if self.a >100000:
        			raise StopIteration()
        		return self.a
      ```
    - \_\_getitem\_\_ 要表现的像list那样下标去除元素, 需要 实现 \_\_getitem\_\_() def \_\_getitem\_\_方法 (self, n):
    - 切片功能list[1:4:2], 是指传入参数可能为int值, 也可能为slice对象
    - \_\_setitem\_\_ 方法, 把对象视为list或dict来对集合赋值,
    - \_\_delitem\_\_方法, 用于删除某个元素.
    - 通过上述定制方法, 我买的自己定义的类表现的和Python自带的list,tuple,dict没什么分别, 这完全归功与动态语言的"鸭子类型", 不需要强制集成那个接口
    - \_\_getattr\_\_ 当调用不存在的属性时，比如score，Python解释器会试图调用__getattr__(self, 'score')来尝试获得属性，这样，我们就有机会返回score的值,返回函数也是完全可以的：注意，只有在没有找到属性的情况下，才调用__getattr__，已有的属性，比如name，不会在__getattr__中查找。此外，注意到任意调用如s.abc都会返回None，这是因为我们定义的__getattr__默认返回就是None。要让class只响应特定的几个属性，我们就要按照约定，抛出AttributeError的错误：
    - \_\_call\_\_() 任何类, 只需要定义一个\_\_call\_\_()方法, 就可以直接再实例本身调用, \_\_call\_\_()还可以定义函数, 对实例进行直接调用就好比对一个函数调用一样, 所以你完全可以把对象堪称函数, 把函数汉城对象, 因为两者之间本没有根本区别. 那么, 怎么判断一个变量是对象还是函数? 其实, 更多的时候, 我买的需要判断一个对象是否能被调用, 能被调用的就是一个Callable对象, 比如函数和我买的上面定义的带有\_\_call\_\_ 的类实例
  * 枚举类
    - 定义 , value属性则是自动赋予成员变量的int常量, 默认从1 开始计数
      ```python3
      from enum import Enum
      Month = Enum('Month', ('Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'))
      ```
    - 这样我们就获得了Month类型的枚举类, 可以直接使用Month.Jan 来引用一个变量, 或者枚举他的所有成员
      ```python3
        for name, member in Month.__members__.items():
            print(name, '=>' , member, ',', member.value)
      ```
    - 精确定义, 如果需要更精确的控制枚举类型, 可以从Enum派生自定义类
    - py文件名不能有数字
* 调试
  - 调试的方式：
    1.  用print()把可能有问题的变量打印出来看看
    2. 使用assert(断言)
    3. 使用logging(日志)，logging不会抛出错误，而且可以输出到文件。
    4. pdb（Python的调试器），让程序以单步的方式运行
    5. pdb.set_trace()
    6. IDE打断点
* idea 开发
  - 安装python plugin
  - new project create virtual env
* 文档调试
  - 将运行结果写在文档注释中, 更直接, 需要用doctest组件
    ```python3
      def abs(n):
          '''
          Function to get absolute value of number.

          Example:

          >>> abs(1)
          1         
          >>> abs(-1)
          1
          >>> abs(0)
          0
          '''
          return n if n >= 0 else (-n)
      if __name__=='__main__':
        import doctest
        doctest.testmod()
    ```
    - 文档注释的测试方式,无疑更明确地告诉函数的调用者该函数的期望输入和输出。并且，Python内置的“文档测试”（doctest）模块可以直接提取注释中的代码并执行测试。doctest严格按照Python交互式命令行的输入和输出来判断测试结果是否正确。只有测试异常的时候，可以用...表示中间一大段烦人的输出。
    - doctest非常有用，不但可以用来测试，还可以直接作为示例代码。通过某些文档生成工具，就可以自动把包含doctest的注释提取出来。用户看文档的时候，同时也看到了doctest。
* IO编程
  - IO在计算机中指Input/Output，也就是输入和输出。由于程序和运行时数据是在内存中驻留，由CPU这个超快的计算核心来执行，涉及到数据交换的地方，通常是磁盘、网络等，就需要IO接口。
  - 很明显，使用异步IO来编写程序性能会远远高于同步IO，但是异步IO的缺点是编程模型复杂。想想看，你得知道什么时候通知你“汉堡做好了”，而通知你的方法也各不相同。如果是服务员跑过来找到你，这是回调模式，如果服务员发短信通知你，你就得不停地检查手机，这是轮询模式。总之，异步IO的复杂度远远高于同步IO。
  - 操作IO的能力都是由操作系统提供的，每一种编程语言都会把操作系统提供的低级C接口封装起来方便使用，Python也不例外。我们后面会详细讨论Python的IO编程接口。
* 文件读写
  - 读文件, 使用Python内置open()函数, 传入文件名和标示符:
    ``` python3
      f = open('./test.txt','r')
      f.read()
    ```
  - 前边讲的默认都是读取文本文件, 并且是UTF-8编码的文本文件, 要读取二进制文件,比如图片, 视频等等, 用'rb'模式打开文件即可:
  - 要读取非UTF-8编码的文本文件, 需要给open()函数传入enconding参数, 例如读取GBK编码的文件:
    ``` python3
        f = open('/Users/michael/test.txt','r', encoding='gbk', errors='ignore')
    ```
  - IO操作需要调用close()方法关闭文件, 文件使用完毕后必须关闭, 因为文件对象绘制用操作系统的资源, 并且操作系统同一时间能打开的文件数量也是有限的, 文件读写易产生IOError, 一旦出错, 后面的f.close()就不会调用, 所以为保证无论是否错误都能正确的关闭文件, 我们可以使用 try ... finally来实现
    ```python3
      try:
          f = open('/path/to/file', 'r')
          print(f.read())
      finally:
          if f:
              f.close()
    ```
  - 这样写太繁琐, 所以, Python引入了with语句来自动帮我们调用close()方法:
    ```python3
        with open('/path/to/file','r') as f:
            print(f.read())
    ```
  - 调用read()会一次性读取文件的全部内容，如果文件有10G，内存就爆了，所以，要保险起见，可以反复调用read(size)方法，每次最多读取size个字节的内容。另外，调用readline()可以每次读取一行内容，调用readlines()一次读取所有内容并按行返回list。因此，要根据需要决定怎么调用。如果文件很小，read()一次性读取最方便；如果不能确定文件大小，反复调用read(size)比较保险；如果是配置文件，调用readlines()最方便：
  - file-like object: 像open()函数返回的这种有个read()方法的对象, 在Python中统称为file-like Object. 出了file外, 还可以是内存的字节流, 网络流, 自定义流等等. file-like Object不要求从特定类继承, 只要写个read()方法就行.
    - StringIO就是在内存中创建的file-like Object, 常用作临时缓冲.
  - 写文件: 写文件和读文件是一样的, 唯一区别是调用open()函数时, 传入标识符'w'或者'wb'表示写文本文件或写二进制文件:
    ```python
      f = open('/Users/michael/test.txt','w')
      f.write('Hello, world')
      f.close()
    ```
* StringIO和BytesIO: StringIO和BytesIO是在内存中操作str和bytes的方法，使得和读写文件具有一致的接口。
  ```python3
      from io import BytesIO
      fff = BytesIO()
      fff.write('中文ss'.encode('utf-8'))
      print(fff.getvalue())
  ```
  ```python3
    from io import StringIO
    f = StringIO('   Hello!   \nHi!\nGoodbye!')
    while True:
        s = f.readline()
        if s == '':
            break
        print(s.strip())
  ```
* 操作文件和目录
  > import os

  - os.name # 操作系统类型 posix ,说明为Linux, Unit 或 Mac OS X, 如果是 nt, 就是windows系统, 详细信息用os.uname函数, window函数Windows上不提供, os模块的某些函数是跟操作系统相关的.
  - 环境变量: os.environ, 过去某个环境变量的值, 可以调用os.envirsion.get('key')
    ```python3
        os.path.abspath('.') # 查看当前目录的绝对路径
        os.path.join(os.path.abspath('.'),'testdir') # 把两个路径拼接,不直接拼字符串, 而是通过 os.path.join()函数, 这样可以正确处理不同操作系统的路径分隔符Linux/Unix/Mac '/' windows '\'
        os.path.split(os.path.abspath('.')) # 同样的道理，要拆分路径时，也不要直接去拆字符串，而要通过os.path.split()函数，这样可以把一个路径拆分为两部分，后一部分总是最后级别的目录或文件名：
        os.makedir(os.path.join(os.path.abspath('.'),'testdir')) # 创建目录
        os.rmdir(os.path.join(os.path.abspath('.'),'testdir')) #删除一个目录
        os.path.splitext() # 可以直接让你得到文件扩展名, 很多时候非常方便
        os.rename('test.txt','test.py') # 对文件重命名
        os.remove('test.py') # 删掉文件
    ```
    - 文件赋值可以通过shutil模块的copyfile()函数, shutil中海油很多使用函数, 可以叫做os模块的补充
    - 列出当前目录下的所有目录
      ``` python3
        [x for x in os.listdir('.') if os.path.isdir(x)]
      ```
    - 列出当前目录下的所有.py文件
      ```python3
        [x for x in os.listdir('.') if os.path.isfile(x) and os.path.splitext(x)[1] == '.py']
      ```
    - Python的os模块封装了操作系统的目录和文件操作，要注意这些函数有的在os模块中，有的在os.path模块中。
* 序列化: 将数据从内存变成可存储或传输的过程称为序列化, 在Python中成为pickling, 在其他语言中称为serialization, marshalling, flattening, 都是一个意思.
  - 获取序列化数据:
    ```python3
      import pickle
      d = dict(name='Bob', age=20, score=88)
      pickle.dumps(d)
    ```
  - 将序列化数据写入文件:
    ``` python3
      f = open('dump.txt','rb')
      d = pickle.dump(d,f)
      f.close()
    ```
  - 将对象从磁盘读到内存时, 可以先将内容读到一个bytes, 然后用pickle.loads()方法反序列化出对象, 也可以直接pickle.load()方法从一个file-like Object中直接反序列化出对象
    ```python3
        f = open('dump.txt','rb')
        d = pickle.load(f)
        f.close()
        d
    ```
  - Pickle的问题和其他编程语言的反序列化问题一样, 就是他只能用于Python, 并且可能不同版本的Python彼此都不兼容, 因此, 只能用Pickle保存那些不重要的数据, 不能充公的反序列化也没关系
  - 为传递对象, 可以用JSON作为标准存储格式
    ```python3
      import json
      fff = open('dump.txt','w')
      d = dict(name='Bob', age=20, score=88)
      json.dumps(d) # '{"age": 20, "score": 88, "name": "Bob"}'
      json.dump(d,fff) # 类似的，dump()方法可以直接把JSON写入一个file-like Object。
      json_str = '{"age": 20, "score": 88, "name": "Bob"}'
      json.loads(json_str)
      json.load(open('dump.txt','r').read())
    ```
  - 对象的序列化和反序列化通过dict进行转换
    ```python3
        def student2dict(std):
            return{
              'name': std.name,
              'age': std.age,
              'score': std.score
            }
      json.dumps(s, default=student2dict) # 对象的序列化
      json.dumps(s, default=lambda obj: obj.__dict__)
    ```
    ```python3
        def dict2student(d):
            return Student(d['name'], d['age'], d['score'])
        print(json.loads(json_str, object_hook=dict2student)) #<__main__.Student object at 0x10cd3c190> 打印出反序列化的Student实例对象
    ```
  - Python语言特定的序列化模块是pickle，但如果要把序列化搞得更通用、更符合Web标准，就可以使用json模块。json模块的dumps()和loads()函数是定义得非常好的接口的典范。当我们使用时，只需要传入一个必须的参数。但是，当默认的序列化或反序列机制不满足我们的要求时，我们又可以传入更多的参数来定制序列化或反序列化的规则，既做到了接口简单易用，又做到了充分的扩展性和灵活性。
* 进程和线程:线程是最小的执行单元，而进程由至少一个线程组成。如何调度进程和线程，完全由操作系统决定，程序自己不能决定什么时候执行，执行多长时间。多进程和多线程的程序涉及到同步、数据共享的问题，编写起来更复杂。
* process: 在Unix/Linux下，可以使用fork()调用实现多进程。要实现跨平台的多进程，可以使用multiprocessing模块。进程间通信是通过Queue、Pipes等实现的。
* Thread, 多线程编程, 模型复杂, 容易发生冲突, 必须用锁加以隔离, 同时, 又要小心死锁的发生, Python解释器由于设计时有GIL全局锁, 导致了多线程无法利用多核, 多线程的并发在Python 就是一个美丽的梦.
* ThreadLocal对象:一个ThreadLocal变量虽然是全局变量，但每个线程都只能读写自己线程的独立副本，互不干扰。ThreadLocal解决了参数在一个线程中各个函数之间互相传递的问题。
  - 全局变量local_school就是一个ThreadLocal对象，每个Thread对它都可以读写student属性，但互不影响。你可以把local_school看成全局变量，但每个属性如local_school.student都是线程的局部变量，可以任意读写而互不干扰，也不用管理锁的问题，ThreadLocal内部会处理。可以理解为全局变量local_school是一个dict，不但可以用local_school.student，还可以绑定其他变量，如local_school.teacher等等。ThreadLocal最常用的地方就是为每个线程绑定一个数据库连接，HTTP请求，用户身份信息等，这样一个线程的所有调用到的处理函数都可以非常方便地访问这些资源。
* 多进程vs多线程
  - 多进程稳定性高, 多线程易崩溃
  - 计算密集型任务适合单任务, 代码运行效率高, c语言; IO密集型适合多任务, CPU等待IO操作
  - 异步IO:考虑到CPU和IO之间巨大的速度差异，一个任务在执行的过程中大部分时间都在等待IO操作，单进程单线程模型会导致别的任务无法并行执行，因此，我们才需要多进程模型或者多线程模型来支持多任务并发执行。现代操作系统对IO操作已经做了巨大的改进，最大的特点就是支持异步IO。如果充分利用操作系统提供的异步IO支持，就可以用单进程单线程模型来执行多任务，这种全新的模型称为事件驱动模型，Nginx就是支持异步IO的Web服务器，它在单核CPU上采用单进程模型就可以高效地支持多任务。在多核CPU上，可以运行多个进程（数量与CPU核心数相同），充分利用多核CPU。由于系统总的进程数量十分有限，因此操作系统调度非常高效。用异步IO编程模型来实现多任务是一个主要的趋势。对应到Python语言，单线程的异步编程模型称为协程，有了协程的支持，就可以基于事件驱动编写高效的多任务程序。我们会在后面讨论如何编写协程。
* 正则模块
  - 使用
    ```python
      import re
      re.match(r'^\d{3}\-\d{3,8}$', '010-12345') # 匹配成功返回Match对象, 否则返回None

      test = '用户输入的字符串'
      if re.match(r'正则表达式', test):
          print('ok')
      else:
          print('failed')
    ```
  - 可用来切割字符串
    ```python
      re.split(r'\s+', 'a b   c')
      # ['a','b','c']
      re.split(r'[\s\,]+', 'a,b,  c, d')
      #['a','b','c','d'], 可以用正则表达式来把不贵但的输入转化为正确的数组.
    ```
  - 分组: 除了简单地判断是否匹配之外，正则表达式还有提取子串的强大功能。用()表示的就是要提取的分组（Group）
    ```python
      m = re.match(r'^(\d{3})-(\d{3,8})$', '010-12345')
      # <_sre.SRE_Match object; span=(0, 9), match='010-12345'>
      # 如果正则表达式定义了组, 就可以再Match对象上用group()方法提取出字串来.
      m.group(0)
      # '010-12345'
      m.group(1)
      # '010'
      m.group(2)
      # '12345'
    ```
  - 当时在Python中使用正则表达式, re模块内部会干两件事:
    - 编译正则表达式, 如果正则表达式字符串本身不合法, 后报错;
    - 用编译后的正则表达式去匹配字符串.
    - 如果一个正则要重复使用几千次, 出于效率考虑, 我们可以预编译该正则表达式, 接下来就不需要编译这个步骤了, 直接匹配:
      ```python
        import re
        re_telephone = re.compile(r'^(\d{3})-(\d{3,8})$')
        re_telephone.match('010-12345').groups()
        # ('010','12345')
        re_telephone.match('010-8086').groups()
        # ('010','8086')
      ```
* datetime
  - 当前时间的获取: now= datetime.now()
  - 获取指定日期和时间, 我们可以直接用参数构建一个datetime: dt = datetime(2017,11,29,17,27)
  - timestamp对象
    - 在计算机中，时间实际上是用数字表示的。我们把1970年1月1日 00:00:00 UTC+00:00时区的时刻称为epoch time，记为0（1970年以前的时间timestamp为负数），当前时间就是相对于epoch time的秒数，称为timestamp。
        - timestamp = 0 = 1970-1-1 00:00:00 UTC+0:00
        - 北京 timestamp = 0 = 1970-1-1 08:00:00 UTC+8:00
    - 可见timestamp的值与时区毫无关系，因为timestamp一旦确定，其UTC时间就确定了，转换到任意时区的时间也是完全确定的，这就是为什么计算机存储的当前时间是以timestamp表示的，因为全球各地的计算机在任意时刻的timestamp都是完全相同的（假定时间已校准）.
    - 转换
      ```python
        from datetime import datetime
        dt = datetime(2017,11,29,20)
        dt.timestamp()
      ```
* collections: collections是Python内建的一个集合模块，提供了许多有用的集合类
  - namedtuple: namedtuple是一个函数，它用来创建一个自定义的tuple对象，并且规定了tuple元素的个数，并可以用属性而不是索引来引用tuple的某个元素
  - deque：deque 是为了高效实现插入和删除操作的双向列表，适合用于队列和栈。可以再首或者尾进行删除和插入
  - defaultdict: 使用dict时，如果引用的Key不存在，就会抛出KeyError。如果希望key不存在时，返回一个默认值，就可以用defaultdict
  - OrderedDict: 可以保证key的顺序
* base64: Base64是一种任意二进制到文本字符串的编码方法，常用于在URL、Cookie、网页中传输少量二进制数据。
  ```python
  import base64

  print(base64.b64encode(b'binary\x00string'))
  # 如果要编码的二进制数据不是3的倍数，最后会剩下1个或2个字节怎么办？Base64用\x00字节在末尾补足后，再在编码的末尾加上1个或2个=号，表示补了多少字节，解码的时候，会自动去掉。
  print(base64.b64decode(b'YmluYXJ5AHN0cmluZw=='))

  # 由于标准的Base64编码后可能出现字符+和/，在URL中就不能直接作为参数，所以又有一种"url safe"的base64编码，其实就是把字符+和/分别变成-和_：
  print(base64.urlsafe_b64decode(b'i\xb7\x1d\xef\xff'))

  # 由于=字符也可能出现在Base64编码中，但=用在URL、Cookie里面会造成歧义，所以，很多Base64编码后会把=去掉
  # 去掉=后怎么解码呢？因为Base64是把3个字节变为4个字节，所以，Base64编码的长度永远是4的倍数，因此，需要加上=把Base64字符串的长度变为4的倍数，就可以正常解码了。
  ```
* hashlib: 摘要算法在很多地方都有广泛的应用。要注意摘要算法不是加密算法，不能用于加密（因为无法通过摘要反推明文），只能用于防篡改，但是它的单向计算特性决定了可以在不存储明文口令的情况下验证用户口令。
  ```python
  import hashlib
  md5 = hashlib.md5()
  md5.update('how to use md5 in python hashlib?'.encode('utf-8'))
  print(md5.hexdigest())

  # 如果数据量很大, 可以分块多次调用update(), 最后计算结果一样
  md5_2 = hashlib.md5()
  md5_2.update('how to use md5 in '.encode('utf-8'))
  md5_2.update('python hashlib?'.encode('utf-8'))
  print(md5_2.hexdigest())

  ```
* hmac:Python内置的hmac模块实现了标准的Hmac算法，它利用一个key对message计算“杂凑”后的hash，使用hmac算法比标准hash算法更安全，因为针对相同的message，不同的key会产生不同的hash。(加盐)
* itertools: itertools模块提供的全部是处理迭代功能的函数，它们的返回值不是list，而是Iterator，只有用for循环迭代的时候才真正计算。