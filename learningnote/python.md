类属性:

```python
__age = 18
```

对象属性  :

```python
def __init__(self,name,age):
	self.name = name
	self.age = age

```

私有化：对外隐藏属性，实例化的对象也无法访问，只有在类内可以进行赋值

```python
class Student:
    __age = 18
    def __init__(self,name,age):
        self.name = name
        self.age = age
        #私有化
        self.__score = 56
    def __str__(self):
        return 'name:{},age:{},score:{}'.format(self.name,self.age,self.__score)
s = Student('kk',18)
print(s)

s.age = 22
print(s)
print('========')
#无法打印改变的值
s.__score //无法取值 ， 私有化之后无法取到
print(s.__score)
```

私有化：修改属性通过类内函数

```python
class Student:
    __age = 18
    def __init__(self,name,age,score):
        self.__name = name
        self.__age = age
        self.__score = score
    def setagescore(self,age,score):
        self.__age = age
        self.__score = score
    def getagescore(self):
        print('age:{},score:{}'.format(self.__age,self.__score))
    def __str__(self):
        return 'name:{},age:{},score:{}'.format(self.__name,self.__age,self.__score)
s = Student('kk',26,77)
print(s)
s.setagescore(30,99)
s.getagescore()
```

封装

设置私有化数据：

1.可以对于输入进行限制，设置验证

2.通过设置类内函数，作为与外界交换数据的接口，这是类内函数的重要作用

```python
class Student:
    __age = 18
    def __init__(self,name,age,score):
        self.__name = name
        self.__age = age
        self.__score = score
        #设置函数为类内数据获取接口
    def setagescore(self,age,score):
        if (age>0 and age<120) and (score>=0 and score<=100):
            self.__age = age
            self.__score = score
            print('age:{},score:{}'.format(self.__age, self.__score))
        elif (age<=0 or age>=120) and (score>=0 and score<=100):
            print('sorry!out of the range of age')
        elif (score<=0 or score>=100) and (age>0 and age<120):
            print('sorry! the score is not in line with the actual situation')
        else :
            print('sorry please, input again')

    def __str__(self):
        return 'name:{},age:{},score:{}'.format(self.__name,self.__age,self.__score)
s = Student('kk',18,77)
print(s)
s.setagescore(160,99)
#只能获取类内的数据，self.xxx的数据获取不了，因为这是对象的数据，而非类数据
print(dir(Student))
#这个就可以看到对象属性结果
print(dir(s))

```

output: attribut list

```python
['_Student__age', '__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__', 'setagescore']


['_Student__age', '_Student__name', '_Student__score', '__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__', 'setagescore']

```

私有化的本质：

```python
__age ====>_Student__age  变形之后，s._age无法访问，s.—Student__age可以访问
不建议这样去访问__age
```

