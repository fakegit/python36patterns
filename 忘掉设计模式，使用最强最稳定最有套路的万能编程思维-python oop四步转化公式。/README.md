# 列举出4种编程方式，并介绍万能的oop 四步转化公式。
```
包含4种编程写法
1）模块级 全局变量  + 函数
2）在一组函数中无限频繁传参 和return
3）无效装逼废物滑稽面向过程类伪oop
4） 真oop
使用4种编程方式来实现男生、女生吃喝拉撒长身体，并说明缺点。

总结oop 四步转化公式。oop转化公式能够做到万能通用，适用一切任意编程场景，能够大幅度减少编程难度和减少代码行数。
只要按照这个公式写代码，就不需要死记硬背套设计模式。
此种编程方式，可以使任意极端纯面向过程代码的文件和项目减少50%行至95%行，写法更直观，并达到流程级可复用。
```

# 3 介绍神级别通用固定oop 4步转化公式，写代码下笔时候行云流水（只需学习这套固定面向过程转oop 4步走转化公式，远强于背诵设计模式）。

**使用这个公式，不需要背设计模式，不需要每次写新文件先花几天想破头皮怎么设计布局代码成为高扩展和高维护。**


[忘掉设计模式，使用最强最稳定最有固定套路的万能编程思维-python oop四步转化公式](https://github.com/ydf0509/python36patterns/tree/master/%E5%BF%98%E6%8E%89%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%EF%BC%8C%E4%BD%BF%E7%94%A8%E6%9C%80%E5%BC%BA%E6%9C%80%E7%A8%B3%E5%AE%9A%E6%9C%80%E6%9C%89%E5%A5%97%E8%B7%AF%E7%9A%84%E4%B8%87%E8%83%BD%E7%BC%96%E7%A8%8B%E6%80%9D%E7%BB%B4-python%20oop%E5%9B%9B%E6%AD%A5%E8%BD%AC%E5%8C%96%E5%85%AC%E5%BC%8F%E3%80%82)


这个oop四步走转化公式是最重要的，其他的36个设计模式python例子你在很多地方都能看到类似的。

先简要说明四步转化公式，具体的看上面链接的文档

## 3.1 四步走转化公式，具体步骤如下

### 第0步，按照模块+函数写python代码，脑子里面打草稿，写全局变量多多益善

**第0步是灵魂步骤，后面3步是死板的代码形式转化。你不做这一步，直接做后面三步，那就是写出无效废物装逼滑稽类，因为写出来也是面向过程的类。**

python模块文件下面多写全局变量，全局变量要多多益善；       
多个函数之间不要疯狂传递一大堆相同名字或意义的入参；      
每个函数末尾不要疯狂return一大堆中间状态变量；       
不要把这些return出来的变量，频繁传递给另外一个函数；   

**你应该尽可能全部设计成全局变量，然后每个函数里面去修改这一堆全局变量，这样就大幅避免了多个函数频繁传递一大堆入参，也不需要每个函数末尾疯狂return一大堆中间状态变量。**

这一步是脑子打草稿，多写全局变量，每个函数少传一大堆入参，少写return一大堆结果变量。 

这一步和老师教你要少写全局变量不同，似乎是反智，但请往下看。

### 第1步 模块降级为类名

就是要把模块级代码移到class 类下面

写个class 类，就是把你之前脑子打的草稿，模块 + 全局变量 + 函数，改成 类+实例属性+实例方法

### 第2步 全局变量降级为实例属性

之前为什么让你多写全局变量，就是为了这一步，全局变量降级为实例属性。你以为最终目的是为了多写全局变量吗？多写全局变量肯定是不行的是反语言的。

### 第3步 函数降级为实例方法

函数改为实例方法，但是函数第一个入参要加个self。

之前模块函数里面直接用全局变量 var_xx，现在实例方法里面读取和修这个"全局变量"，使用 self.var_xx。

## 3.2 oop 四步走转化公式的说明：

转化oop要有灵魂的第0步，如果跳过此步骤，直接执行第1到3步，就会想当然以为转化oop就是函数外面加个class关键字外壳，觉得转化没用。   
那是因为你不按照我说的步骤走，造成写成了无效废物装逼滑稽面向过程类，当然会觉得不需要转化。oop要的是内涵不要搞形式class外壳。

## 3.3 为什么要 oop 四步走转化，说明最根本核心原因

### 3.1 直接 模块级 + 多多益善的全局变量 + 函数  有什么问题？

```
最根本原因是因为模块是单例的，模块的变量是全局唯一的，例如按照第五章的代码你 描述一个人 吃喝拉撒(函数) 影响人的身高体重（全局变量）。

如果你要调用 小红 小明 小黄 小黑 4个人吃喝拉撒，由于全局变量只有一份，那会互相影响，因为全局变量没有隔离。小红调用吃饭，为什么要增加小明的体重？

所以你为了避免这种全局变量不适合多个人调用吃喝拉撒的问题，就写出了类似5.1教程的代码，写成了多个函数间疯狂传参，疯狂return一大堆变量，把这些变量再外部保存，并在函数间传来传去。
```

### 3.2 使用oop的天然多实例，每个实例的属性互不干扰的特性，天然解决全局变量只有一份的问题

```
既想写代码简单粗暴，全局变量加函数的思维，又要解决 全局变量只有一个，不能隔离的问题。那就是使用oop开发代码，     
oop的类天然就是多实例的，每个实例的属性是互不干扰的，天然解决全局变量只有一份的问题。

oop写代码后，类的每个对象的方法访问和修改实例属性，就像函数里面操作全局变量那样丝滑，并且是每个实例的属性天生是各自的，不会互相干扰的。      
你调用 小红.吃饭()  再也不用担心影响到 小明.体重 了。
```
### 3.3 不要用辩证法说有时候面向过程编程有时候更有优势 之类的话！

有的人就是杠精，我说 "考公务员都是精致的利己主义者，就是为了工资高 永不失业 退休金高"；   
他却辩证法说 "也有考公务员是为了成为高尚的人民公仆，例如雷锋就是不喜欢钱，就是喜欢把国家发的工资和退休金都捐给农村老人用"。

```
最怕有的人，完全不去思考为什么需要oop，自己懒得要死，上来就来一句 "有时候面向过程编程更简单更好" 的话 或者 "只有大项目才需要oop" 的话。

不要这么使用辩证法偷懒好吗。我没说过任何场景一定要用oop，最最关键的判断依据是你需不需要多实例， 你不需要多实例那就可以不要面向对象写法,
也不需要单例模式装逼写个类，你直接模块加函数就好了，反正不需要全局变量隔离的需求。

例如本文档第5章节，描写一个人吃喝拉撒运动影响了身高体重，这个需求是非常非常简单吧，绝对是你口中的小项目，绝对是你认为的不需要oop。
但事实就是，用oop来完成需求，比面向过程写法实现时候简单多了，最重要的是调用时候简单太多了。

为什么我写的所有包，例如 funboost  nb_time nb_log都很好用，都是用法十分简单但功能十分强大的python包，原因就是在于此。     
假如你来封装python三方包或框架给别人用，如果你不按我的思路写代码，就会造成不仅你自己实现框架时候很麻烦、很难扩展、爱出错、不好维护，    
更重要的是你把这个包发布出来后，即使功能能达到目的，但用户会感觉极端难使用、不好用、不方便。
例如5.1写法封装的模块，用户来调用人.吃饭() 和人.撒尿() ,用户需要风控传一大堆入参和接受并保存一大堆返回，体验太差了。
```



# oop转化公式的重要本质需要理解的方面
```
最重要是理解：  命名空间  全局变量  实例属性  多实例需求  函数和方法 的关系，搞清楚了，
写oop十分之简单，不会造成极端面向过程的曲折写法。
在word文档中会写更详细的解释。
```

# 常见问题解答
```
1、是不是所有代码都要用oop？
答：不是，按照上面的方式判断用那种方式好，再用oop转化公式，使用真正得oo编程。
如果只是对现有代码直接在函数上套个类名，函数改成方法，99%的情况下弄出来的只会是废物滑稽类，伪oop，
不能有写类就高大上能吓唬人装逼了这种想法。

2、函数和类上面区别？
没有区别，就像问人和走路有什么区别，猪和吃饭有什么区别，问得牛头不对马嘴的伪问题，函数和方法才可以比较。
类（对象）和模块才有可比性，必须要搞清楚原因，不然脑袋中有这个比较的想法那就不可能写得了oop。

面向过程是 文件模块名.eat(狗的名字，shit)
oop是  狗.eat(shit)
```

# python编程范式
```
1.1 方式一，平铺指令。 从上往下叠加指令，适合简单的独立脚本。不需要和没机会被别的模块导入。
1.2 方式二，面向过程函数式编程。适合实现独立的转化功能，基本原理是要实现转化 y = f(x)，
适合函数无依赖状态（不需要在多个函数中频繁的传入和return相同意义的参数）。
1.3 方式三，oop编程.适合多个函数间需要使用同一个变量，并且需要多实例（如果使在使用面向过程时候需要使用函数频繁的return各
种状态/变量由类外使用多个参数来保存这些值和传入这些值，那就是也判断为需要多实例），必须同时满足这两个条件，才使用oop好，
否则不需要oop。（但单例模式为了控制灵活的初始化传参，一般也用类的方式）
1.4 网上说的简单用面向过程，复杂的用面向对象，这简直是错误的废话。简单和复杂界定不了，即使是一个简单的查询价格，经过大量
平台的重写对比，oop都能比面向过程减少70%行以上的代码，所以用网上这句话来判断用什么方式来写代码是错误的。只要严格使用上面
描述的判断方式，就能很容易知道在什么场景什么时候使用哪种方式好了，不需要oop嗨写成类就是没理解好oop能更好地解决什么。
1.5 要多使用oop，但不要写成纯静态或者半静态的无效废物类。 面向过程一定可以搞定一切，但是实现麻烦、调用更麻烦，那就不适合
面向过程了。比如猴子补丁可以搞定继承，闭包可以搞定封装，但是没什么好处，实现麻烦。先要转oop，只有放弃极端面向过程，不对面
向过程过分的偏执和喜欢，才能开始学习更多设计模式。
```


# 5【重要】使用三种代码设计思路写代码模拟人 吃喝拉撒导致身高体重变化。（具体例子，产生强烈对比）

**代码体验分为两部分，第一部分是作者自己封装公共代码时候是否爽快容易扩展维护；第二部分是别人调用你封装的公共包是否感觉爽快好用。**

**三个写法思路分别是： 封装痛苦，调用更苦      封装爽快，调用更爽        封装爽快，调用痛苦**   

情不自禁纯粹极端面向过程编程还是c语言中毒了，从来都不使用面向对象，不用提设计模式。

有些人完全没思考过面向对象，一味的只会说"大型项目才需要面向对象，小项目面向过程更合适"。简直是胡说八道，不看场景只看项目大小。

比如一个简单需求，描写人,吃饭 增加体重和身高，拉尿体重降低。需求是非常非常的简单了吧，绝对是非常小的项目，单个文件就好了，来验证下是不是小项目面向过程就好了。

## 5.1 使用频繁传参和大量return的面向过程来实现，看看代码实现时候有多垃圾麻烦，调用时候多么麻烦。（封装痛苦，调用更苦）

这个面向过程代码实现很麻烦，要频繁传很多入入参和return大量参数；调用时候更加痛苦；  
所以面向过程开发工程师不仅自己写代码麻烦，还造成封装的公共包使用很麻烦

```python
# 吃饭函数
def eat(name, height, weight, food_weight):
    """吃饭：增加体重和身高"""
    new_weight = weight + food_weight
    new_height = height + food_weight * 0.01
    print(f"{name} 吃了 {food_weight} 千克食物，体重: {new_weight} 千克，身高: {new_height} 厘米")
    return new_height, new_weight

# 拉尿函数
def pee(name, height, weight, pee_weight):
    """拉尿：减少体重"""
    if pee_weight > weight:
        pee_weight = weight
    new_weight = weight - pee_weight
    print(f"{name} 拉了 {pee_weight} 千克尿，体重: {new_weight} 千克，身高: {height} 厘米")
    return height, new_weight

# 测试代码
if __name__ == "__main__":
    # 小明的初始状态
    xiaoming_height = 170
    xiaoming_weight = 60

    # 小红的初始状态
    xiaohong_height = 160
    xiaohong_weight = 50

    print(f"小明 初始状态 - 身高: {xiaoming_height} 厘米，体重: {xiaoming_weight} 千克")
    print(f"小红 初始状态 - 身高: {xiaohong_height} 厘米，体重: {xiaohong_weight} 千克")

    # 小明吃饭和拉尿，调用封装的函数太恶心了，传了一大堆入参，还要return一大堆变量，还要在调用处保存这些变量，如果把小红的体重和小明的姓名传混乱就乱了。
    xiaoming_height, xiaoming_weight = eat("小明", xiaoming_height, xiaoming_weight, 2)
    xiaoming_height, xiaoming_weight = pee("小明", xiaoming_height, xiaoming_weight, 1)

    # 小红吃饭和拉尿，调用封装的函数太恶心了，传了一大堆入参，还要return一大堆变量，还要在调用处保存这些变量
    xiaohong_height, xiaohong_weight = eat("小红", xiaohong_height, xiaohong_weight, 3)
    xiaohong_height, xiaohong_weight = pee("小红", xiaohong_height, xiaohong_weight, 2)
```

## 5.2 面向对象来实现 方法加实例属性，看看代码实现多简单调用多方便 （封装爽快，调用更爽）

这个oop面向对象代码，实现时候很丝滑很容易，不需要在每个方法频繁传一大堆入参，和每个方法return 一大堆变量；   
用户在调用时候很简单很爽快。

```python
class Person:
    def __init__(self, name, height, weight):
        self.name = name
        self.height = height  # 身高，单位：厘米
        self.weight = weight  # 体重，单位：千克

    def eat(self, food_weight):
        """吃饭：增加体重和身高"""
        self.weight += food_weight
        self.height += food_weight * 0.01
        print(f"{self.name} 吃了 {food_weight} 千克食物，体重: {self.weight} 千克，身高: {self.height} 厘米")

    def pee(self, pee_weight):
        """拉尿：减少体重"""
        if pee_weight > self.weight:
            pee_weight = self.weight
        self.weight -= pee_weight
        print(f"{self.name} 拉了 {pee_weight} 千克尿，体重: {self.weight} 千克，身高: {self.height} 厘米")

# 测试代码
if __name__ == "__main__":
    # 创建小明和小红
    xiaoming = Person("小明", 170, 60)
    xiaohong = Person("小红", 160, 50)

    # 小明吃饭和拉尿， 调用太爽了，不用传一大堆入参，不用return一大堆变量，不用在调用处保存这些中间变量
    xiaoming.eat(2)
    xiaoming.pee(1)

    # 小红吃饭和拉尿，调用太爽了，不用传一大堆入参，不用return一大堆变量，不用在调用处保存这些中间变量
    xiaohong.eat(3)
    xiaohong.pee(2)
```

```
面向对象起码有封装，极端面向过程那就实现时候，每个函数结尾需要疯狂的return 一大堆变量，然后将一大堆变量传给另外一个函数进行处理。
而面向对象不需要你把一大堆入参疯狂在各个函数传来传去，return来return去。


如果你给我说，定义一个结构体或者字典来存放 身高 体重 姓名，然后充分利用字典是可变类型，这样既减少了每个函数的入参数量，
又不需要return一大堆变量，还是可以用面向过程来写这个代码，
就避免了上面我说的疯狂传参和疯狂return的弊端，那么继承和多态阁下有如何应对呢？ 

比如大人吃1kg长0.1kg体重，小孩吃1kg长0.2kg体重，并且我假设eat函数调用了另外一个_eat2的私有函数来具体的执行体重增加计算，
你在面向过程时候，就要加一个 大人eat的函数 加一个 大人_eat2 的函数，  
并且大人eat的函数里面调用大人_eat2的函数，在小孩eat的函数里面调用小孩_eat2的函数， 整个链路的就都要替换，
而面向对象仅仅需要增加一个大人的类，继承重写 _eat2这个私有方法就好了。
你想下纯粹极端面向过程实现公共代码时候有多low多复杂，并且调用它的时候有多麻烦。

如果你的思维是c语言中毒了，情不自禁极端面向过程编程，连入门的面向对象封装概念都没有，更别提更高阶的设计模式了。

```


## 5.3 使用模块 + 全局变量多多益善 + 函数 的写法，来实现吃喝拉撒影响身高体重，实现是爽 ！！但调用时候不可理喻。（封装爽快，调用痛苦）

这个写法思路不需要多个函数之间频繁传参，实现代码时候很丝滑平顺。！！！但是 但是 但是调用时候无法多实例隔离全局变量，实际不可理喻！

老师和任何教程都说过，写代码要少用全局变量，在编程实践中应当尽量减少其使用。csdn或者ai去搜索 "少用全局变量" 的博客一大堆，自己去看为什么，不展开啰嗦了。

这种 使用模块 + 全局变量多多益善 + 函数 的写法，来实现吃喝拉撒影响身高体重，实现代码时候的确很丝滑，    
因为这个代码实现时候，完全不需要频繁在不同函数之间传一大堆入参，也不需要每个函数return一大堆变量，所以实现起来很爽快。

但是调用时候，由于全局变量是唯一的，所以调用时候无法多实例隔离全局变量，实际不可理喻！因为你一会儿要小红吃饭撒尿影响小红体重，一会儿要小明吃饭撒尿影响小明体重，但姓名 身高 体重 由于是全局变量在内存中只有一份，虽然实现爽，但实际上可调用性很差。   
如果你的场景是脚本单独单次运行，不存在同时需要实现小明 小红 小黑 来复用调用公共包的需求，那你可以使用这种面向过程写法，我从没说过任何场景一定要用oop，一定要你使用oop四步走转化公式写个class类。

这种写法平铺直叙很爽快，适合在单个脚本来单次自己使用，不适合作为公共包被其他地方或其他人调用复用。

所以再次印证了，我上面说的，什么时候应该用面向对象，什么时候可以使用面向过程，不是以项目代码长度来作为依据。而是以是否需要多实例作为依据


- **需要多实例** → 用OOP
- **不需要多实例** → 用面向过程（模块+函数）


```python
# 全局变量多多益善
name = ""
height = 0
weight = 0

def eat(food_weight):
    """吃饭：增加体重和身高"""
    global weight, height
    weight += food_weight
    height += food_weight * 0.01
    print(f"{name} 吃了 {food_weight} 千克食物，体重: {weight} 千克，身高: {height} 厘米")

def pee(pee_weight):
    """拉尿：减少体重"""
    global weight
    if pee_weight > weight:
        pee_weight = weight
    weight -= pee_weight
    print(f"{name} 拉了 {pee_weight} 千克尿，体重: {weight} 千克，身高: {height} 厘米")

# 测试代码 - 写代码很丝滑！
if __name__ == "__main__":
    # 小明的情况
    name = "小明"
    height = 170
    weight = 60
    
    eat(2)  # 不需要传一堆参数！
    pee(1)  # 不需要return和接收一堆变量！
    
    # 但是现在要处理小红，全局变量就乱了...
    name = "小红"  # 这会覆盖掉小明的数据
    height = 160
    weight = 50
    
    eat(3)  # 小红吃饭，但前面小明的状态丢失了
```


## 5.4 鼓励面向过程工程师在脑子里打草稿使用5.3的写法，然后使用4步走转化公式，转化成oop写法。

文章第三章介绍了万能的oop四步走转化公式，你可以在脑子里打草稿使用5.3的写法，然后使用4步走转化公式，转化成oop写法。

如果你是面向过程工程师，不知道怎么设计oop。   
请你一定要按照5.3的 模块 + 全局变量多多益善 + 函数  实现代码思路，然后套用oop四步走转化公式。    
千万不要再使用5.1的 模块 + 无全局变量 + 多个函数之间频繁传一堆参数 + 每个函数末尾风控return一大堆变量 的写法。      
你使用5.1的写法，就是在面向过程一条道走到黑，不光自己实现代码麻烦难扩展维护，更严重的别人调用你封装的公共包还贼恶心贼难用。   


## 5.5 何时需要使用oop

如何上面用真实代码证明的，何时需要使用oop。

- **需要多实例** → 用OOP
- **不需要多实例** → 用面向过程（模块+函数）


### 5.5.2 如果你还是不确定是否需要多实例，建议全部写成oop类。

为什么建议不确定是否要多实例时候，全部写成类oop形式？

#### 第一，oop多实例总是能满足单例需求，但单例无法满足多实例需求。

因为你现在不确定啊，oop是多实例，即使你永远不需要多实例，但你可以只实例化一次，多实例的实现能兼容单例调用。
反过来，你一开始写成模块 + 全局变量 + 函数，那就是个单例，如果你需要多实例，单例不能反过来兼容多实例调用的需求。

```
就好比你设计一个api接口，一个订单下面的商品，是设计成数组还是单个元素？
如果你设计成单个元素，万一以后老板说一个订单能购买多个不同的商品呢?如果你一开始设计成单个元素，原来的api接口设计和代码就无法满足需要大改特改了。
反之，如果你之前是设计成订单下的商品是一个数组，即使一个订单只能购买一个商品，你数组也能兼容里面只包含一个元素，
而且也能兼容以后一个订单购买多个商品。

这说的是可逆和不可逆的区别。
```

例如5.3的代码，你原来只需要小明来调用可以，你后面要小明 小红 小黑都调用，那就全局变量无法隔离，无法满足需求。

#### 第二，全局变量在函数里面修改需要麻烦的global声明，否则是生成修改局部变量，oop天然是实例属性，不需要global声明，不存在变量隔离和污染。

如5.3代码所示，全局变量在函数里面使用并修改时候，需要麻烦的使用global 声明一下，这正是python设计之初，担心用户随意修改污染全局变量。

#### 第三，复杂系统时候，代码量很大，你都写成模块 + 函数，那要分成很多个py文件，类能把一个py文件划分成多个更小模块。

如果吧一组相关功能写一个模块，那要分成很多个py文件，py文件太多了。

而如果把不相关函数放在一个模块，那就很混乱，不知道哪一组函数是负责a功能的，哪一组函数是负责b功能的。

如果写成class类，有代码缩进，通过不同的类名有代码快缩进，就能知道哪些函数是负责什么的，你一个py文件下的100个函数分贝是什么作用能划分更清晰。



#### 只需要按文档的面向过程转 oop 4步走里面的固定公式，脑子里面打草稿全局变量设计得多多益善 + 全局变量->实例属性，函数->方法 降维转化，就可以设计出强大的代码，无需死记硬背23种设计模式。
