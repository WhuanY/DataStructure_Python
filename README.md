# [【北京大学】数据结构与算法Python版 完整版](https://www.bilibili.com/video/BV1VC4y1x7uv/) 学习笔记
## 1 引入
### 什么是计算
- “计算” 概念的提出
- 为了解决数学本身的可检验性问题（我们能否通过“计算”的方法解决任何问题？），大数学家希尔伯特提出“能否找到一种基于有穷观点的能行方法，来判定任何一个数学命题的真假”的命题
    - 有穷观点的能行方法：
        - 由有限数量的有限指令构成；
        - 在有限步骤后终止
        - 执行结果每次都唯一
        - 原则上人可以单独采用纸笔完成，不需要依靠辅助
        - 指令可以清楚地被执行，不需要智慧或灵感
- 这种命题被否定了，也就是不是所有的问题都是纯粹计算能够解决
- 但是，这种观点成为了计算的基础，推动了科技的发展。
### 图灵机
- 概念（略）
- 例子： “a^{m}和b^{m}的模式判断”
### 算法和计算复杂性
- 世界上最早的确定性算法：辗转相除法。在解决大数的时候很有效。学者说明了某类算法在解决某种特定情境下的问题时是高校的。
- 对于某一个确定的问题，解决方案的不同也对应了解决时间的不同。
- 计算复杂性研究问题本身**有多难**，而不考虑如何解决。
- 算法研究了在不同资源约束下不同的解决方案，致力于**找到最高效**的解决方案。
- 不可计算问题和不可计算数
### 突破计算极限
- 电子计算、光子计算、DNA计算、量子计算
- 众包方案，使用人类的智慧解决问题
### 抽象和实现
- Abstract and Physical 
- 对于系统管理员而言，需要了解计算机的物理层次
- 抽象和物理层次是抽象的
- ***算法 + 数据结构 = 程序***
### 程序设计语言实现算法的机制
- 保持问题的**“整体感”**： 通过抽象和实现。
    - **数据抽象**: 抽象数据类型ADT(Abstract Data Type)
        - ADT是一种对数据进行处理的逻辑描述，不涉及如何具体实现这些处理
            - ![用户、接口、实现、操作]](image.png)
        - 如果需要讨论如何具体实现ADT所对应的功能，那么就要考虑实现这些功能所对应的不同数据结构。
        - ADT的特定功能使用程序设计语言的**控制结构**和**基本数据类型**来实现
        - ADT实现了“逻辑”层次和“物理”层次的分离。
    - **数据实现**
        - 思想：封装，不同层级的工程师注重不同层次的问题
- 学习算法的原因
## 2 算法分析
### 什么是算法分析？
- 程序和算法的关系：
    - 同一个算法：
        算法 + 编程语言1 = 程序1
        算法 + 编程语言2 = 程序2 
        ......
    - 同一个编程语言：
        ...
- 评价程序的好坏：
    - 代码风格
    - 可读性
    ...
- 评价算法的好坏
    - 更加高效地利用计算资源，就是好算法。
- **计算资源是什么？**
    - 算法解决问题所需要的存储空间或内存
    - 算法的执行时间
- 使用time模块计算机系统所需要的时间
    [time模块代码示例](算法分析/time.ipynb)
### 使用大O表示法衡量是占用的时间资源
- 使用**赋值语句**来作为运行步骤的衡量单位。
    - 一条赋值语句包含了*表达式*和*变量*两个单位
    - 对于 “问题规模” n:
        - 赋值语句数量T(n) = 1 + n
    - 算法分析的目标是要找出**问题规模**咋么会影响一个算法的运行时间
- 数量级函数 Order of Magnitute
    - 复杂度 O(f(n))
    - f(n)是问题规模 T(n) 的主导部分 （联系等价无穷小）
    - 常见的大O数量级函数
                | f(n)       | 名称     |
        |------------|---------|
        | 1          | 常数    |
        | log(n)     | 对数    |
        | n          | 线性    |
        | n*log(n)   | 对数线性 |
        | n^2        | 平方    |
        | n^3        | 立方    |
        | 2^n        | 指数    |
### 一个示例问题-”变位词判断问题“
- 核心：解决问题的不同方案复杂度不同。
- [变位词判断问题](/算法分析/变位词判断问题[同一问题的不同算法的复杂度].ipynb)
    - 注意：时间和空间的权衡。
### Python数据类型的性能
- 评估python的list和dict两种数据类型的性能。
    - 20%的功能实现80%的结果--〉让20%的功能跑得最快。
    -  Operation          | Big-O Efficiency |
|--------------------|------------------|
| index []           | O(1)             |
| index assignment   | O(1)             |
| append             | O(1)             |
| pop()              | O(1)             |
| pop(i)             | O(n)             |
| insert(i,item)     | O(n)             |
| del operator       | O(n)             |
| iteration          | O(n)             |
| contains (in)      | O(n)             |
| get slice [x:y]    | O(k)             |
| del slice          | O(n)             |
| set slice          | O(n+k)           |
| reverse            | O(n)             |
| concatenate        | O(k)             |
| sort               | O(n log n)       |
| multiply           | O(nk)            |
- list.pop() 和 list.pop(i) 复杂度的权衡
    - list.pop() 的复杂度是O()
    - list.pop(i) 的复杂度是O(n)
        - pop(i) 的实现方式是将移除元素后面的元素分别向前移动。比较麻烦
        - 但是这种方式保证了列表索引方式的实现复杂度为O(1)
        - 保证了复杂度的权衡。
    - [list.pop()](算法分析/time.ipynb)的计时实验
- dict
    - 大部分dict数据结构更快
## 常见数据 

### 线性结构
- 定义：线性结构是一种有序数据项的集合，其中每个数据项都有唯一的前驱和后继。
    - 除了第一个没有前驱，最后一个没有后继
    - 新的数据项加入数据集中时，只会嫁到原有的某个数据项之前或之后
    - 具有这种性质的数据集，就称为线性结构
- 不同线性结构的关键区别在数据项的增减方式
    - 只允许一端添加
    - 中间可以添加
    - 可以允许两端删除
    - ...
- 
#### [栈Stack](算法分析/stack.ipynb)
- 栈是一种有次序的数据项集合。在栈中，每个数据项仅从“栈顶”一端加入、移出。
    - 栈顶Top， 栈底称为Base
    - 栈的次序是LIFO(Last In First Out)
- 应用
    - [括号匹配](算法分析/stack.ipynb)
        ![Alt text](image-1.png)
    - [进制转换](算法分析/进制转换.ipynb)
#### 队列Queue
#### 双端队列Deque
#### 列表list