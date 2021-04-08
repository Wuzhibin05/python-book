# Python基本数据类型



## 一.什么是数据类型？

什么是数据类型？

　　我们人类可以很容易的分清数字与字符的区别，但是计算机并不能呀，计算机虽然很强大，但从某种角度上看又很傻，除非你明确的告诉它，1是数字，“汉”是文字，否则它是分不清1和‘汉’的区别的，因此，在每个编程语言里都会有一个叫数据类型的东东，其实就是对常用的各种数据类型进行了明确的划分，你想让计算机进行数值运算，你就传数字给它，你想让他处理文字，就传字符串类型给他。Python中常用的数据类型有多种，如下：

　整数(int) ,字符串(str),布尔值(bool),列表(list),元组(tuple),字典(dict),集合(set).

-  int。数字：主要用于运算。1 ，2,3...
-  bool。判断真假：True, False.
-  str。简单少量的储存数据，并进行相应的操作。name = 'alex',
-  tuple。只读，不能更改。(1,'alex') 
-  list：大量有序数据，[1,'ses',True,[1,2,3],{'name':'jinxin'}]
-  dict：大量数据，且是关联性比较强的数据 {'name':'jinxin','age':18,'name_list':['张三'，'李四']}



## 二.基础数据类型。



#### 2.1数字int。

int，就是咱们常见的数据类型，主要是用于葛总运算，加减乘数等这里就不给你举例说明了。

  首先要给大家讲下是十进制与二进制之间的转换。

 **2.1.1 十进制二进制转换**

  **十进制整数转换为二进制整数**采用"除2取余，逆序排列"法。具体做法是：用2整除十进制整数，可以得到一个商和余数；再用2去除商，又会得到一个商和余数，如此进行，直到商为小于1时为止，然后把先得到的余数作为二进制数的低位有效位，后得到的余数作为二进制数的高位有效位，依次排列起来。

　　**十进制小数转换成二进制小数**采用"乘2取整，顺序排列"法。具体做法是：用2乘十进制小数，可以得到积，将积的整数部分取出，再用2乘余下的小数部分，又得到一个积，再将积的整数部分取出，如此进行，直到积中的小数部分为零，此时0或1为二进制的最后一位。或者达到所要求的精度为止。



　　**二进制转化成十进制:** 

  要从右到左用二进制的每个数去乘以2的相应次方,小数点后则是从左往右

  例如：二进制数1101.01转化成十进制

  1101.01（2）=1*20+0*21+1*22+1*23 +0*2-1+1*2-2=1+0+4+8+0+0.25=13.25（10）

  所以总结起来通用公式为：

  abcd.efg(2)=d*20+c*21+b*22+a*23+e*2-1+f*2-2+g*2-3（10）

或者是：

  把二进制数首先写成加权系数展开式，然后按十进制加法规则求和。这种做法称为"按权相加"法。

[![img](https://gss2.bdstatic.com/-fo3dSag_xI4khGkpoWK1HF6hhy/baike/s%3D250/sign=34a5a18b6d224f4a5399741639f69044/9213b07eca8065388a8973be97dda144ad348238.jpg)](https://baike.baidu.com/pic/十进制转二进制/393189/0/9213b07eca8065388a8973be97dda144ad348238?fr=lemma&ct=single)

  此时，1101=8+4+0+1=13

  再比如：二进制数100011转成十进制数可以看作这样：

  数字中共有三个1 即第一位一个，第五位一个，第六位一个，然后对应十进制数即2的0次方+2的1次方+2的5次方， 即

  100011=32+0+0+0+2+1=35

　　**2.2.2 int操作方法**

  因为数字主要是用于计算，所以针对于数字可以使用的方法除了那些运算之外，没有什么经常会用的方法，python给咱们提供了一种方法：bit_length()就是帮助你快速的计算整数在内存中占用的二进制码的长度.

```
num = 10
print(num.bit_length())  # 当十进制用二进制表示时，最少使用的位数
# 运行结果: 4
```

#### 2.2布尔值bool。

布尔值就两种：True，False。就是反应条件的正确与否。

真  1  True。

假  0  False。  

这里补充一下int str bool 三者数据类型之间的转换。

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

#### 2.3字符串str。

Python中凡是用引号引起来的数据可以称为字符串类型，组成字符串的每个元素称之为字符，将这些字符一个一个连接起来，然后在用引号起来就是字符串。

```
s1 = '太白nb'
# 对于s1这个字符串来说，它由四个字符组成：太, 白, n, b。
```

2.3.1、字符串的索引与切片。

组成字符串的字符从左至右，依次排列，他们都是有顺序的，就好比是部队的队列，从左至右依次报号(从零开始) ：0,1,2,3....

![img](https://img2018.cnblogs.com/blog/988316/201903/988316-20190321161218486-291122921.png)

 索引即下标，就是字符串组成的元素从第一个开始，初始索引为0以此类推。

```
a = 'ABCDEFGHIJK'
print(a[0])
print(a[3])
print(a[5])
print(a[7])
```

切片就是通过索引（索引：索引：步长）截取字符串的一段，形成新的字符串（原则就是顾头不顾腚）。

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
a = 'ABCDEFGHIJK'
print(a[0:3])  # print(a[:3]) 从开头开始取0可以默认不写
print(a[2:5])
print(a[:]) #默认到最后
print(a[:-1]) # -1 是列表中最后一个元素的索引，但是要满足顾头不顾腚的原则，所以取不到K元素
print(a[:5:2]) #加步长print(a[-1:-5:-2]) #反向加步长
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

2.3.2、字符串常用方法。

字符串除了可以用切片（步长）之外，还有一些其他的操作方法。

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

####  2.4列表list

**Why:** 我们现在已经学过的数据类型有：数字，布尔值，字符串，大家都知道数字主要用于计算，bool值主要是条件判断，只有字符串可以用于数据的存储，这些数据类型够用么？对于一门语言来说，肯定是不够用的。就说字符串：

  1，字符串只能存储少量的数据，对于大量的数据用字符串操作不方便也不易存储。

  2，字符串存储的数据类型太单一，只能是字符串类型。

  例如：‘1 True alex’ 像这样的字符串，我如果通过切片或者其他方法将1 True alex 取出来，他也只能是字符串，但是我想要得到数字的1，布尔值的True，必须还要转化，是不是很麻烦。

所以python给咱们也提供了一类数据类型，他能承载多种数据类型，这类数据类型被称作容器类数据类型可以存储大量的数据。列表就属于容器类的数据类型。

**What:**这个数据类型就是list列表。

  列表是python的基础数据类型之一 ,其他编程语言也有类似的数据类型.比如JS中的数 组, java中的数组等等. 它是以[ ]括起来, 每个元素用' , '隔开而且可以存放各种数据类型: 列表是python中的基础数据类型之一，其他语言中也有类似于列表的数据类

型，比如js中叫数组，他是以[]括起来，每个元素以逗号隔开，而且他里面可以存放各种数据类型比如：

li = [‘alex’,123,Ture,(1,2,3,’wusir’),[1,2,3,’小明’,],{‘name’:’alex’}]

列表相比于字符串，不仅可以储存不同的数据类型，而且可以储存大量数据，32位python的限制是 536870912 个元素,64位python的限制是 1152921504606846975 个元素。而且列表是有序的，有索引值，可切片，方便取值。

**How**：那么这个列表如何使用呢？咱们从这几方面去深入研究这个列表。

2.4.1 **列表的创建**

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
# 创建一个列表有三种方式：

# 方式一：（常用）
l1 = [1, 2, '太白']


# 方式二：（不常用）
l1 = list()  # 空列表
# l1 = list(iterable)  # 可迭代对象
l1 = list('123')
print(l1)  # ['1', '2', '3']

# 方式三：列表推导式（后面的课程会讲到）
l1 = [i for i in range(1,5)]
print(l1)  # [1, 2, 3, 4]
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

2.4.2 **列表的索引切片**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 相应练习题

2.4.3. **增**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 列表的增

2.4.4. **删**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 列表的删

2.4.5. **改**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 列表的改

2.4.6. **查**

切片去查，或者循环去查。

**2.4.5 其他操作这些方法会在数据类型的补充时再给大家讲~**

2.4.5、**其他操作**

count（数）（方法统计某个元素在列表中出现的次数）。

```
1 a = ["q","w","q","r","t","y"]
2 print(a.count("q"))
```

index（方法用于从列表中找出某个值第一个匹配项的索引位置）

```
1 a = ["q","w","r","t","y"]
2 print(a.index("r"))
```

sort （方法用于在原位置对列表进行排序）。

 reverse （方法将列表中的元素反向存放）。

```
1 a = [2,1,3,4,5]
2 a.sort()# 他没有返回值，所以只能打印a
3 print(a)
4 a.reverse()#他也没有返回值，所以只能打印a
5 print(a)
```

**列表也可以相加与整数相乘**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 列表也可以相加(与int相乘)

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 相应练习题

**2.4.6 列表的嵌套**

```
l1 = [1, 2, 'taibai', [1, 'WuSir', 3,]]
1, 将l1中的'taibai'变成大写并放回原处。
2，给小列表[1,'alex',3,]追加一个元素,'老男孩教育'。
3，将列表中的'alex'通过字符串拼接的方式在列表中变成'alexsb'
```

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 相应练习题

**Where**:(这个知识点用在什么地方)：

　　你需要存储大量的数据，且需要这些数据有序的时候。

　　制定一些特殊的数据群体：按顺序，按规则，自定制设计数据。

#### 2.5元组tuple。

**Why**:对于容器型数据类型list，无论谁都可以对其增删改查，那么有一些重要的数据放在list中是不安全的，所以需要一种容器类的数据类型存放重要的数据，创建之初只能查看而不能增删改，这种数据类型就是元组。

**what**:这个容器型数据类型就是元组。

元组:俗称不可变的列表,又被成为只读列表,元祖也是python的基本数据类型之一,用小括号括起来,里面可以放任何数据类型的数据,查询可以,循环也可以,切片也可以.但就是不能改.

2.5.1 **元组的索引切片**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 元组的索引切片

**2.5.2 其他操作这些方法会在数据类型的补充时再给大家讲~**

2.5.2 **元组其他操作方法**

因为元组的特性，直接从属于元组的元素不能更改，所以元组只能查看。

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

**index**：通过元素找索引（可切片），找到第一个元素就返回，找不到该元素即报错。

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

**count**: 获取某元素在列表中出现的次数

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

2.5.3 len

```
tu1 = (1,2,3,4,84,5,2,8,2,11,88,2)
print(len(tu1))

结果:
12　
```

**Where**:

  1，就是将一些非常重要的不可让人改动的数据放在元组中，只供查看。

  2，常用于元组的拆包（数据类型补充的时候会给大家讲到）。

#### 2.6字典dict。

　　**2.6.1 字典的初识**

**Why:**咱们目前已经学习到的容器型数据类型只有list，那么list够用？他有什么缺点呢？

  \1. 列表可以存储大量的数据类型，但是如果数据量大的话，他的查询速度比较慢。

  \2. 列表只能按照顺序存储，数据与数据之间关联性不强。

所以针对于上的缺点，说咱们需要引入另一种容器型的数据类型，解决上面的问题，这就需要dict字典。

**what：**

  数据类型可以按照多种角度进行分类，就跟咱们人一样，人按照地域可以划分分为亚洲人，欧洲人，美洲人等，但是按照肤色又可以分为白种人，黄种人，黑种人，等等，数据类型可以按照不同的角度进行分类，先给大家按照可变与不可变的数据类型的分类：

  不可变（可哈希）的数据类型：int，str，bool，tuple。

  可变（不可哈希）的数据类型：list，dict，set。

字典是Python语言中的映射类型，他是以{}括起来，里面的内容是以键值对的形式储存的：

  Key: 不可变（可哈希）的数据类型.并且键是唯一的，不重复的。

  Value:任意数据(int，str，bool，tuple，list，dict，set)，包括后面要学的实例对象等。

　在Python3.5版本（包括此版本）之前，字典是无序的。

　在Python3.6版本之后，字典会按照初建字典时的顺序排列(即第一次插入数据的顺序排序)。

　当然，字典也有缺点：他的缺点就是内存消耗巨大。

　　**字典查询之所以快的解释：（了解）**

**字典的查询速度非常快，简单解释一下原因**：字典的键值对会存在一个散列表（稀疏数组）这样的空间中，每一个单位称作一个表元，表元里面记录着key：value,如果你想要找到这个key对应的值，先要对这个key进行hash获取一串数字咱们简称为门牌号（非内存地址），然后通过门牌号，确定表元，对比查询的key与被锁定的key是否相同，如果相同，将值返回，如果不同，报错。（这里只是简单的说一下过程，其实还是比较复杂的。），下面我已图形举例：

 

![img](http://crm.pythonav.com/media/uploads/2019/03/28/IMAGE.PNG)

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 详细解释

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 解释：字典内存开销巨大(了解)

　　**2.6.2 创建字典的几种方式：**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

　　**2.6.3 验证字典的合法性**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

　　**2.6.4 字典的常用操作方法**

　　**接下来咱们就进入字典的学习环节，字典对于咱们小白来说可能相对于列表是不好理解的，因为列表是有序的一个一个排列的，但是字典的键值对对于大家来说是比较陌生的，所以咱们可以把字典比喻成一个公寓，公寓里面有N多个房间，房间号就是键，房间里面具体的东西就值：比如房间001号：对应的房间住着两个人，也就是2person，简称2P，房间99号：3P， 房间78号：有人还有小动物....... 这样，咱们就能通过房间号（也就是键）找到对应的房间，查看里面的内容，也就是值。**

  **那么首先先从字典的增删改查开始学习。**

**增**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 字典的增

**删**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 字典的删

**改**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 字典的改

**查**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 字典的查

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 相关练习题

fromkeys 数据类型的补充时会给大家讲到~

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

**其他操作**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

**这里补充一个知识点：分别赋值，也叫拆包。**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

 **所以利用上面刚学的拆包的概念，我们循环字典时还可以这样获取字典的键，以及值：**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

 **4.1.5字典的嵌套**

  字典的嵌套是非常重要的知识点，这个必须要建立在熟练使用字典的增删改查的基础上，而且字典的嵌套才是咱们在工作中经常会遇到的字典，工作中遇到的字典不是简简单单一层，而就像是葱头一样，一层接一层，但一般都是很有规律的嵌套，那么接下来我们就学习一下字典的嵌套：

  **现在有如下字典，完成一下需求：**

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

解题思路：

  1.获取汪峰的名字。: 这个比较简单，汪峰就是dic的一个键对应的值，我们通过这个key就可以获取到汪峰这个值。

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

  \2. 获取这个字典{'name':'国际章','age':38}: 想要获取这个字典，先要看字典从属于谁？这个字典从属于一个列表，而这个列表是字典wife对应的键，所以咱们应该先通过wife获取到对应的这个列表，然后通过这个列表按照所以取值取到对应的这个字典。

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

  \3. 获取汪峰的妻子名字: 还是按照上一题的思路：想要获取汪峰妻子的名字：国际章，那么他是一个字典的键对应的值，所以我们通过'name'这个键就可以获取到对应的值，这个题的难点是获取到这个小字典，而上一个题我们已经获取了这个小字典，所以在上面的基础上再执行就可以了。

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

  \4. 获取汪峰的第三个孩子名字: 汪峰的孩子们是在一个字典中的，你要想获取汪峰的第三个孩子，你应该先获取到它从属于的这个字典，然后再通过这个字典获取第三个孩子的名字。

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) View Code

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 相关练习题

#### 2.7集合set (了解)

集合是无序的，不重复的数据集合，它里面的元素是可哈希的(不可变类型)，但是集合本身是不可哈希（所以集合做不了字典的键）的。以下是集合最重要的两点：

　　去重，把一个列表变成集合，就自动去重了。

　　关系测试，测试两组数据之前的交集、差集、并集等关系。

1，集合的创建。

```
set1 = set({1,2,'barry'})
set2 = {1,2,'barry'}
print(set1,set2)  # {1, 2, 'barry'} {1, 2, 'barry'}
```

2，集合的增。

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
set1 = {'alex','wusir','ritian','egon','barry'}
set1.add('景女神')
print(set1)

#update：迭代着增加
set1.update('A')
print(set1)
set1.update('老师')
print(set1)
set1.update([1,2,3])
print(set1)
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

3，集合的删。

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
set1 = {'alex','wusir','ritian','egon','barry'}

set1.remove('alex')  # 删除一个元素
print(set1)

set1.pop()  # 随机删除一个元素
print(set1)

set1.clear()  # 清空集合
print(set1)

del set1  # 删除集合
print(set1)
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

4，集合的其他操作：

　　4.1 交集。（& 或者 intersection）

```
set1 = {1,2,3,4,5}
set2 = {4,5,6,7,8}
print(set1 & set2)  # {4, 5}
print(set1.intersection(set2))  # {4, 5}
```

　　4.2 并集。（| 或者 union）

```
set1 = {1,2,3,4,5}
set2 = {4,5,6,7,8}
print(set1 | set2)  # {1, 2, 3, 4, 5, 6, 7,8}print(set2.union(set1))  # {1, 2, 3, 4, 5, 6, 7,8}
```

　　4.3 差集。（- 或者 difference）

```
set1 = {1,2,3,4,5}
set2 = {4,5,6,7,8}
print(set1 - set2)  # {1, 2, 3}
print(set1.difference(set2))  # {1, 2, 3}
```

 　4.4反交集。 （^ 或者 symmetric_difference）

```
set1 = {1,2,3,4,5}
set2 = {4,5,6,7,8}
print(set1 ^ set2)  # {1, 2, 3, 6, 7, 8}
print(set1.symmetric_difference(set2))  # {1, 2, 3, 6, 7, 8}
```

　　4.5子集与超集

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
set1 = {1,2,3}
set2 = {1,2,3,4,5,6}

print(set1 < set2)
print(set1.issubset(set2))  # 这两个相同，都是说明set1是set2子集。

print(set2 > set1)
print(set2.issuperset(set1))  # 这两个相同，都是说明set2是set1超集。
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

5，frozenset不可变集合，让集合变成不可变类型。

```
s = frozenset('barry')
print(s,type(s))  # frozenset({'a', 'y', 'b', 'r'}) <class 'frozenset'>
```

## 三.其他（for，enumerate，range）。

for循环：用户按照顺序循环可迭代对象的内容。

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
msg = '老男孩python是全国范围内最好的python培训机构'
for item in msg:
    print(item)

li = ['alex','银角','女神','egon','太白']
for i in li:
    print(i)

dic = {'name':'太白','age':18,'sex':'man'}
for k,v in dic.items():
    print(k,v)
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

enumerate：枚举，对于一个可迭代的（iterable）/可遍历的对象（如列表、字符串），enumerate将其组成一个索引序列，利用它可以同时获得索引和值。

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
li = ['alex','银角','女神','egon','太白']
for i in enumerate(li):
    print(i)
for index,name in enumerate(li,1):
    print(index,name)
for index, name in enumerate(li, 100):  # 起始位置默认是0，可更改
    print(index, name)　　　　
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

range：指定范围，生成指定数字。

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

```
for i in range(1,10):
    print(i)

for i in range(1,10,2):  # 步长
    print(i)

for i in range(10,1,-2): # 反向步长
    print(i)
```

[![复制代码](https://common.cnblogs.com/images/copycode.gif)](javascript:void(0);)

![img](https://images.cnblogs.com/OutliningIndicators/ContractedBlock.gif) 利用len和range打印列表的索引