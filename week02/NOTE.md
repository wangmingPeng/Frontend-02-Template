# 学习总结

## 1、编程语言的分类方法
###  a、非形式语言
    中文、英文
### b、形式语言（乔姆斯基谱系）
    0型 无限制文法
    1型 上下文相关文法
    2型 上下文无关文法
    3型 正则文法

## 2、定义语法
### 产生式（BNF）
    语法规则：
    1、用尖括号括起来的名称来表示语法结构名
    2、语法结构分成基础机构和需要用其他语法结构定义的复合结构
        基础结构称终结符
        复合结构称非终结符
    3、引号和中间的字符表示终结符
    4、可以有括号
    5、* 表示重复多次
    6、| 表示或
    7、+ 表示至少一次
### 其他产生式
    EBNF ABNF Customized

## 3、编程语言分类
### a、形式语言--用途
#### 数据描述语言
    JSON、HTML、XAML、SQL、CSS
#### 编成语言
    C、C++、Java、C#、Python、Ruby、Perl、Lisp、T-SQL、Clojure、Haskell、JavaScript
### b、形式语言--表达方式
#### 声明式语言
    JSON、HTML、XAML、SQL、CSS、Lisp、Clojure、Haskell
#### 命令型语言
    C、C++、Java、C#、Python、Ruby、Perl、T-SQL、JavaScript

## 4个人对编程语言的分类
### 编程语言有
    C,C++,C#,Java,Python,JavaScript,Lisp,Go,HTML,XAML,CSS,Ruby,SQL,JSON,Delphi,VB,PHP,Perl,Fortran,Ada,Pascal,Smalltalk,Objective-C,Basic,Lua,汇编,Clojure,Haskell，TypeScript

    面向对象语言：C++，Java，PHP，Samlltalk，Objective-C
    面向过程语言：C，Fortran，汇编
    动态语言：Lua，Perl，PHP，Python，Ruby，Smalltalk，JavaScript
    静态语言：Java，C++，C#，C，TypeScript
    脚本语言：shell，JavaScript，PHP，Python，Ruby，Perl，Lua
    解释型：Python，Perl，Java、JavaScript，Ruby
    编译型：C，C++，Delphi，Pascal

## 5、图灵完备性
### a、命令式--图灵机
    goto
    if 和 while
### b、声明式--lambda
    递归
## 6、动态与静态
### a、动态
    在用户的设备/在线服务器上
    产品实际运行时
    Runtime
### c、静态
    在程序员的设备上
    产品开发时
    Compiletime
## 7、类型系统
### a、动态类型系统与静态类型系统
### b、强类型与弱类型
    String + Number
    String == Boolean
### c、复合类型
    结构体
    函数签名
### d、子类型
### e、泛型
    逆变/协变
## 8、一般命令式编程语言
    有以下几个组成部分
    Atom    Expression  Statement   structure   Program
### a、Atom
    Identifier
    Literal
### b、Expression
    Atom
    Operator
    Punctuator
### c、Statement
    Expression
    Keyword
    Punctuator
### d、Structure
    Function
    Class
    Process
    Namespace
    ......
### e、Program
    Program
    Module
    Package
    Library
## 9、Types
    Number
    String
    Boolean
    Object
    Null
    Undefined
    Symbol
### a、Number
    JavaScript中的 Number 是双精度浮点数 有 2^64-253+3 个值
    几个例外情况
        NaN 
        Infinity 无穷大
        —Infinity 负无穷大
    需要区分 +0 和 —0
    非整数的 Number 类型无法用 == 来比较
    比较方法为
        Math.abs(0.1 + 0.2 - 0.3) <= Number.EPSILON
    IEEE 754 Double Float  在内存中表示由以下组成
        Sign(1) 符号位
        Exponent(11) 阶码
        Fraction(52) 二进制科学计数法小数点后面的部分
### b、String
#### 编码方式
    ASCII
    Unicode
    UCS
    GB （GB2313、 GBK、GB18030）
    ISO-8859
    BIG5

    String 的意义并非“字符串”，而是字符串的 UTF16 编码
    JavaScript 中的字符串是永远无法变更的，一旦构建出来，无法用任何方式改变字符串的内容
### c、Boolean
    true
    false
### d、Null
    只有一个值 null，表示空值， null 是 JavaScript的关键字，可以使用 null 关键字来获取 null 的值
### e、Undefined
    表示未定义，值为 undefined 因为 undefined 不是一个关键字 通常使用 void 0 来获取undefined 的值
### f、Symbol
    是一切非字符串的对象的 key 的集合，具有唯一性
### g、Object
    任何一个对象都是唯一的，与它本身的状态无关
    两个完全一致的对象也并不相等
    用状态来描述对象
    状态的改变即为行为

    在 JavaScript 中，用属性来统一抽象对象的状态和行为
    数据属性用来描述状态，访问器属性用来描述行为，数据属性中如果存在存储函数，也可以用于描述行为

    JavaScript 中有一些特殊的对象 eg：函数对象
    函数对象除了一般对象的属性和原型，还有有一个行为 [[call]]
    用 JavaScript 中的 function 关键字、箭头运算符或者 Function 构造器创造的对象，会有[[call]]这个行为， 用 f() 做函数调用的时，会访问到[[call]] 这个行为，如果对应的对象没有[[call]]这个行为则会报错

### 原型（对象属性）
    Javascript规定，每一个函数都有一个prototype对象属性，指向另一个对象（原型链上面的）。
    prototype(对象属性)的所有属性和方法，都会被构造函数的实例继承。这意味着，我们可以把那些不变(公用)的属性和方法，直接定义在prototype对象属性上。

    prototype就是调用构造函数所创建的那个实例对象的原型（proto）。

    prototype可以让所有对象实例共享它所包含的属性和方法。也就是说，不必在构造函数中定义对象信息，而是可以直接将这些信息添加到原型中。

### 原型链 （JS原型与原型链继承）
    实例对象与原型之间的连接，叫做原型链。proto( 隐式连接 )
    JS在创建对象的时候，都有一个叫做proto的内置属性，用于指向创建它的函数对象的原型对象prototype。
    内部原型(proto)和构造器的原型（prototype）
    1、每个对象都有一个proto属性,原型链上的对象正是依靠这个属性连结在一起
    2、作为一个对象，当你访问其中的一个属性或方法的时候，如果这个对象中没有这个 方法或属性，那么Javascript引擎将会访问这个对象的proto属性所指向上一个对 象，并在那个对象中查找指定的方法或属性，如果不能找到，那就会继续通过那个对象 的proto属性指向的对象进行向上查找，直到这个链表结束


