## JavaScript

> JavaScript是一种运行在客户端（浏览器）的脚本语言

客户端：**客户端**是相对于服务器而言的，在这里先简单理解为浏览器
浏览器就是一个客户端软件，浏览器从服务器上将资源（html,css,js,图片等）请求下来 并且在本地利用浏览器去解析这些资源
服务器本质上也是一台电脑。用来接收客户端发过来的请求，并处理请求。同时存储数据 读取数据等操作

脚本语言：不需要编译 读取一句  解析一句  一句报错 下一句不会继续执行
执行过程：源代码 - 预解析 - 运行
编译语言：需要编译 编译一旦出错  整个程序都不会运行
执行过程：源代码 - 编译后的字节码文件 - 运行

### JS的作用
1、网页特效
2、表单验证
3、服务端的JS (node.js)
4、命令行工具 (node.js)
5、app
6、游戏开发

总结：JS无所不能，我们学习的方向主要针对的是web页面

### JS的组成
+ ECMAscript： JavaScript的核心，描述了语言的基本语法和数据类型，ECMAScript是一套标准，定义了一种语言的标准与具体实现无关
+ DOM：（document object model 文档对象模型）一套操作页面元素的API
+ BOM：（browser object model  浏览器对象模型）一套操作浏览器功能的API



### JS输出语法
```js
// 调用弹出框功能
alert('Hello world');
// 调用对话框功能
prompt('Hello');
// 确认框
confirm('Are you sure?');
// 向页面输入对应的值
document.write('你好呀');
// 向控制台输出日志
console.log('我是出现在控制台 ，一般用于后期调试代码');
```
## 变量
> 概念：一块被命名的运行存储空间

> 运行存储空间：电脑应用程序在运行的时候开辟的内存空间

> 为什么要命名：方便程序员使用

> 简单理解：

存储空间：容器
命名：为了在众多容器中找到对应的容器
容器里面装了什么东西 这个变量就代表什么东西

```js
     // 声明并赋值
      // var a = 1;
      // console.log(a);

      // 先声明  后赋值
      //  var a;
      //  a = 1;
      // console.log(a);

      // 不声明直接赋值  不要这么使用 会带来作用域问题
      // a = 1;
      // console.log(a);

      // 不声明不赋值 直接使用   直接报错
      // console.log(a);
      // console.log(name);
      // console.log(window);

      // 同时声明多个变量 并单独赋值
      //  var a, b, c, d, e;
      //  a = 1;
      //  b = 2;
      //  c = 3;
      //  d = 4;
      //  e = 5;
      //  console.log(a, b, c, d, e);

      // 同时声明多个变量并赋同一个值
      var a = b = c = d = e = 1;
      console.log(a, b, c, d, e);
```
> 变量的规则和规范

+ 规则 不遵守会报错
  - 由字母、数字、下划线、$符号组成，不能以数字开头
  - 不能是关键字和保留字，例如：var for while
  - 关键字：对于JS来说有特殊意义的字符 [查询保留字和关键字]https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords
  - 保留字：现在没有意义 但是保留在那边 以后可能会有意义的字符
  - 区分大小写
+ 规范 尽量遵守
  - 变量名必须有意义
  - 遵守驼峰式命名法 首字母小写，后面单词首字母大写 例如：userName userPassword
+ 课堂测试

## 数据类型
> 在程序设计中，数据类型被定义为数据的种类，也就是说一系列可能值以及基于这些值的基本操作。
> 好处：更加充分和高效的利用内存和使用数据

### 六大数据类型

+ 基本数据类型（简单数据类型）
  - number 数值型
  - string 字符串
  - boolean 布尔型
  - undefined 未定义
  - null 空引用
+ 引用数据类型（复杂数据类型）
  - object

#### number
> 所有的数字都是Number数据类型
> 利用typeof运算符可以返回当前数据的数据类型

特殊值：NaN not a number 不是一个数字

**注意** 小数的计算可能产生丢失精度的问题
问题来源：小数的2进制存储转换会带来丢失精度的问题
 [丢失进度]https://segmentfault.com/a/1190000008268668
 [浮点数]https://zh.wikipedia.org/wiki/%E6%B5%AE%E7%82%B9%E6%95%B0
解决方法：扩大成整数去运算

#### string
> 所有添加了引号的数据都是字符串数据类型 单双引号都可

转义字符：
![转义字符](./media/1498289626813.png)

#### 布尔
> 布尔类型只有两个值 true或者false 多用于条件的判断

#### undefined null
> undefined 未定义 变量只声明没有赋值的时候浏览器默认会赋值一个undefined
> null 表示一个空的对象  一般用于将一些对象清空

### 数据类型转换
+ 将数据转换成数值型
  - parseInt() 把字符串转换成整数
    - parseFloat() 把字符串转换成浮点数 parseFloat会解析第一个. 遇到第二个 . 或者非数字结束 如果解析的内容里只有整数，解析成整数
  - Number
    Number()可以把任意值转换成数值，如果要转换的字符串中有一个不是数值的字符，返回NaN
+ 将数据转换成字符串
  - toString() 将数据转换成字符串
  - String() 将数据转换成字符串 有些数据不能用toString 比如 undefined null
  - 隐式转换 任何数据只需要跟字符串相加最终结果一定是字符串
+ 将数据转换成布尔类型
  - boolean()
  - 0，null，undefined，空字符串，false 会被转转换成false 不成立的表达式也会



### 引用数据类型和值数据类型

> 简单数据类型（值类型）
> 在存储时，变量中存储的是值本身，因此叫做值类型。
> 如：number string  boolean undefined null
> 复杂数据类型 （引用类型）
> array object function
> 在存储时，变量中存储的仅仅是地址（引用），因此叫做引用数据类型

思考题：

```js
//1.
function Person(name, age) {
    this.name = name;
    this.age = age;
}
var p1 = new Person("zs", 18);
var p2 = p1;
p2.name = "ls";
console.log(p1.name);
console.log(p2.name);

//2.
function Person(name, age) {
  this.name = name;
  this.age = age;
}
function f1(p) {
  p.name = "ls";
  console.log(p.name);
}
var p1 = new Person("zs", 18);
console.log(p1.name);
f1(p1);
console.log(p1.name);
```

结论：简单类型存储的是值本身，复杂类型存储的是地址，引入如果把第一个对象赋值给另一个变量，此时两个变量会指向同一个对象。





## 操作符（运算符）
> 用来操作数据的符号，一般用于运算

+ 算术运算符 (+,-,*,/,%)
  - 加、减、乘、除、取模
  - 加号：数值相加 字符相连

+ 赋值运算符 (=)
  - 将等号右边的值赋予给左边
+ 自增自减运算符（一元运算符）
  - a++ ++后置 先使用 后自增
  - ++a ++前置 先自增 后使用
  - a-- --后置 先使用 后自减
  - --a --前置 后自减 先使用
+ 猜猜看：
```js
 var a = 1; var b = ++a + ++a; console.log(b);    
 var a = 1; var b = a++ + ++a; console.log(b);    
 var a = 1; var b = a++ + a++; console.log(b);    
 var a = 1; var b = ++a + a++; console.log(b);
 console.log(5++); console.log(++5); 
```
+ 自减



### 逻辑运算符

```
  // 逻辑运算符  与 或 非
  // 与 &&  可以理解为并且  两个条件必须同时满足  一个不满足整个表达式不成立
  // 或 ||  两个条件只需要满足一个即可
  // 非  取反  !true  !false

```

### 比较运算符

> 比较运算符  >、 <、 >=、 <=、 ==、 ===、 !=、 !==

```js
// 比较运算符的结果都是布尔值
console.log(2 > 1);
console.log(1 > 2);

// >= <=  这个理解为大于或者等于  小于或者等于
console.log( 5 >= 5 );
console.log( 5 <= 5 );

// == 等于  只要内容相等即可
console.log(3 == 3);
console.log(3 == '3');
console.log(0 == false);
// === 全等  全等不仅仅是内容相等 同时需要比较类型
console.log(3 === '3');

// != 比较内容即可 !== 不仅比较内容还比较类型
console.log(3 !== '3');

// 特殊情况
如果是数字和字符串的比较 则字符串数字会自动转换成数字去比较
如果是字符串和字符串比较 则会每一个字符的ASCII码去进行比较
涉及到NAN都是false （NaN）
如果是布尔值参与比较 布尔值会转换成数字0和1
```

### 操作符优先级

> 不同的操作符之间的优先级有不同

```text
优先级从高到低
1. ()  优先级最高
2. 一元运算符  ++   --   !
3. 算数运算符  先*  /  %   后 +   -
4. 关系运算符  >   >=   <   <=
5. 相等运算符   ==   !=    ===    !==
6. 逻辑运算符 先&&   后||
7. 赋值运算符
```

练习1：

```js
	var result =  1 + 2 * 8 / 4 ;  
	var result1 =  (1 + 2) * (8 / 4) ;  
	var result2 = !true + !false >= 1;  
	var result3 = !true + (!false >= 1);  
	var result4 = !(true + false)
```

练习2：

```js
4 >= 6 || '人' != '阿凡达' && !(12 * 2 == 144) && true
```

练习3：

```js
var num = 10;
5 == num / 2 && (2 + 2 * num).toString() === '22'
```

## 表达式和语句

> 可以产生一个值的式子就是表达式  在现阶段可以理解为有运算符（不包括赋值运算符）的地方就是表达式

如：a++  1+2+3;

> 语句可以理解为一个行为  语句中可以包含表达式

如：var a = 1;  var b = 2 + 4 + 6;

> 语句的分类

- 顺序语句  自上而下一步一步执行 之前学习的所有都是顺序语句

![](imgs/顺序结构.png)

- 分支语句  根据条件有选择的执行

![](imgs/分支结构.png)

- 循环语句  循环执行对应的语句
  ![](imgs/循环结构.png)

### 分支语句

```
if(条件){
	条件为真则执行大括号里面的代码
}

if(条件){
	条件为真则执行大括号里面的代码
}else{
	条件为假则执行这个括号里面的代码
}

if(条件1){
	条件1为真则执行这里的代码 并且不会继续执行下面的条件分支
}else if(条件2){
	如果条件1为假
	并且条件2为真则执行这里的代码 并且不会继续执行下面的条件分支
}else if(条件3){
	...
}else{
	上述条件都不成立 则执行这里的代码
}
```

#### 三元运算符

```javascript
// 表达式1 ? 表达式2 : 表达式3
// 1. 三元运算符会得到一个结果，结果根据表达式1的值来确定。
// 2. 如果表达式1的值为true，会返回表达式2的值
// 3. 如果表达式1的值为false，会返回表示3的值
```

```javascript
//求两个数的最大值
//思考1：求两个数的最小值
//思考2：判断成年还是未成年
//思考3：求三个数的最小值
```

#### switch case语句

> 分支语句的一种

```js
switch (表达式){
      case "值":
      //语句;
      case "值":
      //语句;
   }
```

注意：

1. switch case语句不能完全替代if else
2. switch case比较的值全等 ===
3. switch case一般需要配合break关键字使用 没有break会造成case穿透



### 循环语句

#### while 语句

![](imgs/while.png)

```js
while(条件){
	条件为真时会不断执行这个代码 直到while的条件为假
}
```

所以while循环里面的条件的值是会发生变化的 如果没有变化 则就是一个死循环

#### while语句练习

- 打印1-100的和
- 打印100以内 7的倍数
- 打印100以内所有偶数
- 打印100以内所有偶数的和

#### do while 循环

> do while 循环最大的不同的就是while循环是先判断在循环  而do while是先do 一次 在开始循环 也就是说不管能不能循环 先do一次
> ![](imgs/dowhile.png)

```js
do{
	// 循环语句
}while(true)
```

do while 循环练习

- 使用do-while循环：输出询问“我爱你，嫁给我吧？”，如果输入为“嫁”则打印”我们形影不离“，若输入为“不嫁”,则继续询问
- 让用户输入用户名和密码，只有当用户名=admin并且用户密码=123456的时候才提示登录成功，否则一直弹框

#### for 循环语句

![](imgs/for.png)

```js
	for(语句1;语句2;语句4){
		语句3;
	}

	// 语句1：初始化语句 用来初始化变量
	// 语句2：循环的判断条件
	// 语句3：循环体
	// 语句4：循环体结束之后执行的代码
```

for循环语句练习

- 打印1-100之间所有数
- 求1-100之间所有数的和
- 求1-100之间所有数的平均值
- 求1-100之间所有偶数的和
- 同时求1-100之间所有偶数和奇数的和

for循环语句进阶练习

- 打印出一个五行五列的心形
- 打印出一个五行递增列的心形 （一行一列，二行两列，三行三列，...）
- 打印99乘法表

##### break和continue

> ##### break 跳出整个循环
>
> continue 跳出当前循环 继续下一次的循环

```html
求整数1～100的累加值，但要求碰到3的倍数则停止累加
求整数1～100的累加值，但要求跳过所有为3的倍数的数
```



## 数组

> 所谓数组，就是将多个元素（通常是同一类型）按一定顺序排列放到一个集合中，那么这个集合我们就称之为数组。

> 数组是一个Array对象  属于复杂数据类型

### 创建数组

> 字面量形式

```js
var arr = ['内容1','内容2','内容3'];
```

> 构造函数形式

```
var arr = new Array('内容1','内容2','内容3');

细节注意: 使用构造函数形式array的小括号里面如果只写一个数值型的数据表示这个数组的长度 而不是内容
```

### 数组的长度和下标

获取数组的某一个元素：数组[下标]  下标从0开始
获取数组的长度 数组.length
数组的长度和下标的关系：arr.length - 1 = 最大的下标

### 数组的赋值和修改及其追加

```js
var arr = ["red", "green", "blue"];
arr[0] = "yellow";//把red替换成了yellow
arr[3] = "pink";//给数组新增加了一个pink的值
```

思考：如何给一个数组增加新的元素？

```
1. 把1-100之间所有的数，放到数组中
2. 把1-100之间所有的奇数，放到数组中
3. 把1-100之间能被3整数的数字，存到数组中
```

### 遍历数组

> 访问数组里面的每一个数据

```js
	for(var i = 1; i <= arr.length; i++){
        console.log(arr[i - 1]);
    }

	for(var i = 0; i < arr.length; i++){
		console.log(arr[i]);
	}
```

针对数组的应用

- 求一组数中的所有数的和的平均值
- 求一组数中的最大值和最小值 以及所在位置
- 将字符串数组用|或其他符号分割
- 要求将数组中的0项去掉，将不为0的的值存入到新的数组 生成新的数组
- 翻转数组
  +

### 冒泡排序

> 冒泡排序是排序的一种

> 主体思路：两两之间相互比较，比较完毕之后最大的数就出来了，这是第一趟 然后重复第二次两两之间相互比较 比较完毕之后第二大的数就出来了
>  一次类推 只需要比较数组的长度 - 1 次

其他排序方式了解：https://zh.wikipedia.org/wiki/%E6%8E%92%E5%BA%8F%E7%AE%97%E6%B3%95



## 函数

> 函数的定义：一堆特定代码的集合体，它负责完成某项特定任务，而且相较于其他代码，具备相对的独立性，一般会有输入参数并有返回值，提供对过程的封装和细节的隐藏
>  函数就是一个功能，并且具备复用性

> 声明函数和使用函数

```js
// 声明函数
function 函数名 (){
    // 函数体
}

// 调用函数
函数名();
```

特点说明：

- 函数默认不会执行 必须通过函数名()调用才会执行
- 函数的命名尽量遵守 动词或者动词+名词的方式 这样函数的作用一目了然

```js
function greet(){
    console.log(Hi);
}

sayHi();
```

思考：

```js
1. 封装一个打招呼的函数
2. 封装一个函数，计算两个数的和
3. 封装一个函数，计算1-100之间所有数的和
```

### 函数传参

函数的参数极大的提高了函数的灵活性

> 在声明函数的小括号里面写的数值我们称之为形式参数  形式参数的作用就是声明了两个变量 参数与参数之间用逗号隔开
> 在调用函数的小括号里面写的数值我们称之为实际参数  实际参数的作用就是给形式参数赋值，参数与参数之间用逗号隔开

形参：声明变量
实参：给变量赋值

```javascript
//带参数的函数声明
function 函数名(形参1, 形参2, 形参...){
  //函数体
}

//带参数的函数调用
函数名(实参1, 实参2, 实参3);
```

思考：

```js
1. 计算1-n之间所有数的和
2. 计算m-n之间所有数的和
3. 班级有五个学生  计算着五个学生的总成绩
```

### 函数的返回值

> 通俗的讲就是这个函数执行完毕之后的结果
> 在直观一点就是函数调用之后的值  默认是undefined

```js
    function doSomething(){
        // doing
        return result;
    }

    var jieguo = doSomething();
```

函数的返回值不是必要的，一般用于函数执行完毕之后产生一个结果 这个结果在其他地方需要使用的时候就需要返回值，如果当前函数没有返回值
浏览器会默认返回一个undefined

```
练习：计算任意班级的总成绩  再求出最好的成绩的班级
```

函数三要素：函数名，参数，返回值

思考1：

```javascript
1. 求任意半径的圆的面积
2. 求任意半径的圆的周长
3. 求任意2个数中的最大值
```

思考2：

```javascript
1. 求任意数组中的最大值
2. 求任意数组中的最小值
3. 翻转任意数组，返回一个新的数组
4. 对任意数组从小到大排序
```





1. 两个相同的函数后面的会覆盖前面的函数
2. 在Javascript中 实参的个数和形参的个数可以不一样
   - 如果实参过多 那么多余的实参会被忽略
   - 如果形参过多 会自动填上undefined
3. 函数碰到return就不会在往下执行了  函数的结束用return  break是用在循环里面的
4. return;的写法相当于return undefined;

思考:

```js
 改写数组去重
 求数组中的最大值和最小值，并且返回
 难点：返回两个值
```

### 作用域

> 作用域：变量起作用的区域

> 全局作用域：在script标签内，在函数外的区域，在全局作用域内声明的变量是全局变量，全局变量在任何地方都能访问到
> 局部作用域：在函数内部的区域，在函数内部声明的变量叫做局部变量,这个局部变量只有在当前函数内部才能访问。
> 隐式全局变量：没有用var声明的变量是全局变量（隐式全局）不要使用
> 当全局变量和局部变量重名时，会优先使用局部变量

思考：

```js
 // 1、
  var num = 11;
  function fn() {
    num = 44;
    console.log(num);
  }

  fn();
  console.log(num);

// 2、
  var num1 = 11;
  var num2 = 22;
  function fn() {
    var num1 = 33;
    num1 = 44;
    num2 = 55;
    console.log(num1);
    console.log(num2);
  }

  fn();

  console.log(num1);
  console.log(num2);
```

### 预解析

> JS在真正执行之前，在JS运行之前 JS解析器会将JS代码预先解析  （将变量声明和函数声明提前）
> 如果遇到同名的函数和变量，函数优先（权重更高）。

思考：

```js
console.log(a);
var a = 1;
console.log(a);

fn();
function fn (){
    console.log(111);
}

// 重名getcool的问题
getCool();

// 同名情况下 函数声明的权重比变量高
console.log(a);

  function a() {
    console.log('aaaa');
  }
   var a = 1;
console.log(a);
```

面试题：

```javascript

//1.
var num = 10;
fn1();
function fn1() {
  console.log(num);
  var num = 20;
}

//2.
var a = 18;
fn2();
function fn2() {
    var b = 9;
    console.log(a);
    console.log(b);
}

//3.
fn3();
console.log(c);
console.log(b);
console.log(a);
function fn3() {
  var a = b = c = 9;
  console.log(a);
  console.log(b);
  console.log(c);
}


//4.
a();
function a (){
console.log(1);
}
var a = 1;
a();
console.log(a);

// 5、
var n1 = 11;
  var n2 = 22;
  fn2();
  fn();
  function fn() {
    var n1 = 111;
    n2 = 222;
    var n3 = 333;
    console.log(n1, n2, n3);
  }

  function fn2() {
    n1 = 1111;
    var n2 = 2222;
    var n3 = 3333;
    console.log(n1, n2, n3);
  }
  console.log(n1, n2);
  console.log(n3);
```

### 匿名函数

> 何为匿名函数  就是没有名字的函数

```js
function(){

}
```

匿名函数因为没有名字 所以没有办法直接使用
1.通过将匿名函数赋值给一个变量 我们将这个称之为函数表达式
函数表达式值会预解析前面的var 后面的值不会被解析
2.函数自执行
匿名函数();

函数可以避免全局变量的污染



### 声明函数的两种方式

函数声明：

```javascript
function 函数名(){
  //函数体
}
```

函数表达式(匿名函数)：

```javascript
var 函数名 = function(){
  //函数体
}
```

### 函数作为参数

> 通常，我们把作为参数传递的函数叫做回调函数

```javascript
function fn1(fn) {
  fn();
}
fn1(function(){
   console.log("哈哈");
});
```

### 函数作为返回值

> 在js高级中，闭包会使用到。

```javascript
function fn1() {
    return function(){
      console.log("呵呵");
    }
}
fn1()();//调用
```



### 自执行函数

函数可以自执行

```javascript
(function fn(){
  console.log("我可以自己执行哦");
})();
```



## 对象

何为对象：万物皆对象 客观世界中的具体的实体就是对象 如 一个人 一个气球  一辆汽车 每一个对象实体都有对应的特征

思考：上述对象都是客观世界的，那JS这门语言中为什么要有对象呢 又如何用代码去描述一个对象呢

数组：**是有序的元素集合** ，数组用于存放一组数据，比如一个班级所有人的名字，一个班级所有人的成绩。

函数：**封装一段重复的代码，只要声明一次，就可以多次调用。**

```javascript
思考1：如果要存储一个人的信息，应该怎么办？
var name = "张三";
var age = 18;
var sex = "男";
var hobby = "上网";
思考2：这么做的缺点是什么？
这些变量都是属于一个人的，应该跟数组一样，使用一个集合把所有的信息都存储起来。
```

对象：**是一组无序的键值对的集合。**

- 事物的特征在对象中用属性来表示。
- 事物的行为在对象中用方法来表示。

```javascript
//数组多个元素之间使用,隔开
//对象中多个键值对之间也用,隔开，，，键值对的格式： 键:值
var obj = {
  name:"张三",
  age:18,
  sex:"男",
  hobby:"上网",
  greet: function() {
    console.log('你好呀！！');
  }
}
```

### 创建对象和使用

> 字面量的形式 11 “abc”  true  [] {}等

```javascript
var o = {};
var o = {
  name : "zs",
  age : 18,
  sex : true,
  sayHi : function() {
    console.log(this.name);
  }
};
```

### 通过Object构造函数创建

```javascript
var hero = new Object();//创建一个空的对象
```

### 设置对象的属性

```javascript
//语法  对象名.属性 = 值;
var obj = new Object();
obj.name = "zs";
obj.age = 18;
obj.gender = "男";

//给对象设置添加一个方法
obj.sayHi = function() {
  console.log("大家好，我是"+obj.name);
}
```

### 获取对象的属性

```javascript
//语法：  对象名.属性
console.log(obj.name);
console.log(obj.age);
console.log(obj.gender);

//如果是方法，可以调用
obj.sayHi();
```

### 批量创建对象  工厂函数



```js
// 上述都是重复去做一件事情 重复去做一件事情 我们就可以利用function封装 然后重复调用 传递对应的参数
  function creatStudent(name, age, height, hobby) {
    var obj = {
      name: name,
      age: age,
      height: height,
      hobby: hobby,
      sayHi: function () {
        console.log('Hello everyone');
      },
      study: function () {
        console.log('好好学习 天天向上');
      }
    }

    return obj;
  }

  var xmg = creatStudent('xmg', '16', 180, '嘿嘿');
  var wt = creatStudent('wt', '14', 180, '嘻嘻');
  var ff = creatStudent('ff', '18', 110, '呼呼');
```

优点：可以同时创建多个对象
缺点：麻烦，并且没有原型关系（JS精讲）

### 实例

实例：就是实际的例子   例如：“人” 是一个模板（构造函数）  而飞飞则是这个模板的一个实例
或者“猫” 是一个模板（构造函数） 而我家的猫 则是这个模板的一个实例
JS内部提供了不同数据的模板，都可以通过new去创建出一个新的实例出来

```js
 // 得到数组的实例
  var arr = new Array(1,2,3);
  console.log(arr);

  // 得到普通对象的实例
  var obj = new Object({name:123});
  console.log(obj);

  // 得到函数的实例
  var fn = new Function('a','b','c','d');
  console.log(fn);

  // 得到数字的实例
  var num = new Number(123);
  console.log(num);

  // 得到布尔的实例
  var bool = new Boolean(true);
  console.log(bool);

  // 得到字符串的实例
  var str = new String('123');
  console.log(str);

  // 上述都是JS内部提供的 但JS没有提供学生（模板） 所以需要动手创建
  var stu = new Student('小明',18);
```

### 构造函数 

```js
// 构造函数名字大写
function Student (name, age, hobby, gender){
    this.name = name;
    this.age = age;
    this.hobby = hobby;
    this.gender = gender;
}

var obj = new Student('小马哥', 18, '开车', '未知');
```

### new 运算符

- 创建一个新的对象 类型从属于对应的构造函数
- 将this指向这个新对象
- 执行构造函数
- 返回这个新对象

new运算符一般配合构造函数使用 这种方式创建对象更加简单。并且有原型关系（JS高级精讲）

### []语法操作对象属性

> 对象["属性名"]

```js
    var obj = {
        name: 'feifei',
        age: 18,
        gender: '男',
        i: 1
      };
      console.log(obj.age);

      var obj1 = {
        name: '马哥',
        'true-age': 20
      }
      console.log(obj1);

      // 关联数组的方式
      console.log(obj1["true-age"]);

      // 点语法可以操作对象的属性  但是如果属性名中有-这些特殊字符的  通过.语法就操作不了
      // 但是我们可以利用关联数组的方式去操作
      // 对象['属性名']  或者 对象.属性名

      var i = "name";
      console.log(obj.i); //  undefined 因为JS解析器会把I作为对象的属性  而当前对象并没有i这个属性  所以是udnefined
      console.log(obj[i]);// 关联数组的方式不加引号  会解析成变量 将变量里面存的值作为对象属性
      console.log(obj["i"]); // 添加上了引号  直接解析成对象对应的属性
```

### 遍历对象

> for遍历的问题：

- 对象的长度  也就是说循环多少次
- 获取对象里面的具体属性

> 通过for in语法

```js
var obj = {
    name: 'feifei',
    age: 15,
    gender: 'male'
  };

  /*for(var i = 0; i < 3; i++){
    obj[0]
  };*/

  // for循环遍历对象的两个问题：
  // 1、对象的长度  也就是说循环多少次
  // 2、获取变量里面的具体属性

  for(var attr in obj){
    // console.log('1');
    // console.log(attr);
    console.log(obj[attr]);
  }
```



## 内置对象

> JS内置对象就是指Javascript自带的一些对象，供开发者使用，这些对象提供了一些常用的的功能。
>
> 常见的内置对象有Math、String、Array、Date等

内置对象有很多，我们主要是记下这些内置对象的用法即可。但是同学们也不可能一下子记住这么多的方法，因此当同学们忘了某个方法该如何使用的时候，可以通过以下方式查看。

- 跳转到定义`ctrl+左键`
- [火狐开发者网站MDN](https://developer.mozilla.org/zh-CN/)
- [W3School网站](http://www.w3school.com.cn/jsref/)
- 离线文档
- 笔记

### Math对象

> Math对象中封装很多与数学相关的属性和方法。

- 属性PI

  `Math.PI`

- ### 最大值/最小值

  ```
  Math.max();
  Math.min();
  ```

- 取整（★）

  ```javascript
  Math.ceil();//天花板，向上取整
  Math.floor();//地板，向下取整
  Math.round();//四舍五入，如果是.5，则取更大的那个数
  ```

- 随机数（★）

  ```javascript
  Math.random();//返回一个[0,1)之间的数，能取到0，取不到1
  ```

- 绝对值

  ```javascript
  Math.abs();//求绝对值
  ```

- 次幂和平方

  ```javascript
  Math.pow(num, power);//求num的power次方
  Math.sqrt(num);//对num开平方
  ```

- 练习

```javascript
  随机生成一个rgb颜色？
  function randomRGB(){
    var colorA = parseInt( Math.random() * 256 );
    var colorB = parseInt( Math.random() * 256 );
    var colorC = parseInt( Math.random() * 256 );
    return 'rgb('+ colorA + "," + colorB + ',' + colorC +')';
  }
```

### Date对象

> Date对象用来处理日期和时间

- 创建一个日期对象

  ```javascript
  var date = new Date();//使用构造函数创建一个当前时间的对象
  var date = new Date("2017-03-22");//创建一个指定时间的日期对象
  var date = new Date("2017-03-22 00:52:34");//创建一个指定时间的日期对象
  var date = new Date(2017, 2, 22, 0, 52, 34);
  var date = new Date(1523199394644);//参数：毫秒值

  Date构造函数的参数
  1. 毫秒数 1498099000356		new Date(1498099000356)
  2. 日期格式字符串  '2015-5-1'	 new Date('2015-5-1')
  3. 年、月、日……				 var date = new Date(2017, 2, 22, 0, 52, 34);月份从0开始
  ```

- 日期格式化(了解)

  ```javascript
  date.toString();//默认的日期格式
  date.toLocalString();//本地风格的日期格式（兼容性）
  date.toDateString();
  date.toLocaleDateString();
  date.toTimeString();
  date.toLocaleTimeString();
  ```

- 获取日期的指定部分

  ```javascript
  getMilliseconds();//获取毫秒值
  getSeconds();//获取秒
  getMinutes();//获取分钟
  getHours();//获取小时
  getDay();//获取星期，0-6    0：星期天
  getDate();//获取日，即当月的第几天
  getMonth();//返回月份，注意从0开始计算，这个地方坑爹，0-11
  getFullYear();//返回4位的年份  如 2016

  //思考：
  //封装一个函数，返回当前的时间，格式是：yyyy-MM-dd HH:mm:ss
  ```

- 时间戳

  ```javascript
  var date = +new Date();//1970年01月01日00时00分00秒起至现在的总毫秒数
  //思考
  //如何统计一段代码的执行时间？
  ```

### Array对象

> 数组对象在javascript中非常的常用

- 数组转换（★）

  ```javascript
  //语法：array.join(separator)
  //作用：将数组的值拼接成字符串

  var arr = [1,2,3,4,5];
  arr.join();//不传参数，默认按【,】进行拼接
  arr.join("-");//按【-】进行拼接
  ```

- 数组的增删操作（★）

  ```javascript
  array.push();//从后面添加元素，返回新数组的length
  array.pop();//从数组的后面删除元素，返回删除的那个元素
  array.unshift();//从数组的前面的添加元素，返回新数组的长度
  array.shift();//从数组的最前面删除元素，返回删除的那个元素

  //练习1
  var arr = ["刘备"];
  //添加数据后变成：["赵云","马超","刘备","关羽","张飞"]
  //删除数据后变成：["关羽","张飞"]

  //练习2
  var arr = ["赵云","马超","刘备","关羽","张飞"];
  //把数组的最后一个元素变成数组的第一个元素
  //把数组的第一个元素变成数组的最后一个元素
  ```

- ### 数组的翻转与排序

  ```javascript
  array.reverse();//翻转数组
  array.sort();//数组的排序，默认按照字母顺序排序

  //sort方法可以传递一个函数作为参数，这个参数用来控制数组如何进行排序
  arr.sort(function(a, b){
    //如果返回值>0,则交换位置
    return a - b;
  });
  ```

```javascript
  //思考：
  //将[3, 6, 1, 5, 10, 2,11]从小到大排列
  //将字符串数组按照字符长度从小到大排列
  //将学生数组按照年龄从小到大排列
```

- 数组的拼接与截取

  ```javascript
  //concat：数组合并，不会影响原来的数组，会返回一个新数组。
  var newArray = array.concat(array2);

  //slice:数组切分，复制数组的一部分到一个新数组，并返回这个数组
  //原来的数组不受影响，包含begin，不包含end
  var newArray = array.slice(begin, end);

  //splice:删除数组或者增加数据元素
  //start:开始位置  deleteCount:删除的个数  items:替换的内容
  array.slice(start, deleteCount, [items]);

  //练习：
  var arr = ["赵云","马超","刘备","关羽","张飞"];
  //截取["刘备","关羽"]
  //在马超后面增加 马腾
  //删除关羽
  ```

- 数组查找元素

  ```javascript
  //indexOf方法用来查找数组中某个元素第一次出现的位置，如果找不到，返回-1
  array.indexOf(search, [fromIndex]);

  //astIndexOf()从后面开始查找数组中元素出现位置,如果找不到，返回-1
  array.lastIndexOf(search, [fromIndex]);
  ```

- 清空数组

  ```javascript
  //1. array.splice(0,array.leng);//删除数组中所有的元素
  //2．array.length = 0;//直接修改数组的长度
  //3．array = [];//将数组赋值为一个空数组，推荐
  ```

- 数组综合练习

  ```javascript
  var arr = ["c", "a", "z", "a", "x", "a", "a", "z", "c", "x", "a", "x"]
  //1. 找到数组中第一个a出现的位置
  //2. 找到数组中最后一个a出现的位置
  //3. 找到数组中每一个a出现的位置
  //4. 数组去重，返回一个新数组
  //5. 获取数组中每个元素出现的次数
  ```

## 基本包装类型

> **简单数据类型是没有方法的**。为了方便操作基本数据类型，JavaScript还提供了三个特殊的引用类型：String/Number/Boolean。

基本包装类型：把基本类型包装成复杂类型。

```javascript
var num = 123;
var result = num.toString();
//发生了三件事情
1. 把简单类型转换成复杂类型：var s = new Number(num);
2. 调用包装类型的indexOf方法：var result = s.toString();
3. 销毁刚刚创建的复杂类型
```

### Number对象

> Number对象是数字的包装类型，数字可以直接使用这些方法

```javascript
toFixed(2)//保留2位小数
toString();//转换成字符串
```

### Boolean对象

> Boolean对象是布尔类型的包装类型。

```javascript
toString( );//转换成字符串
```

**undefined和null没有包装类型，所以调用toString方法会报错**

### String对象

> 字符串可以看成是一个字符数组（伪数组）。因此字符串也有长度，也可以进行遍历。String对象很多方法的名字和和Array的一样。可以少记很多的单词。

- 查找指定字符串

  ```javascript
  //indexOf:获取某个字符串第一次出现的位置，如果没有，返回-1
  //lastIndexOf:从后面开始查找第一次出现的位置。如果没有，返回-1
  ```

- 去除空白

  ```javascript
  trim();//去除字符串两边的空格，内部空格不会去除
  ```

- 大小写转换

```javascript
  //toUpperCase：全部转换成大写字母
  //toLowerCase：全部转换成小写字母
```

- 字符串拼接与截取

  ```javascript
  //字符串拼接
  //可以用concat，用法与数组一样，但是字符串拼串我们一般都用+

  //字符串截取的方法有很多，记得越多，越混乱，因此就记好用的就行
  //slice ：从start开始，end结束，并且取不到end。
  //substring ：从start开始，end结束，并且取不到end
  //substr ： ：从start开始，截取length个字符。
  ```

- 字符串切割

  ```javascript
  //split:将字符串分割成数组（很常用）
  //功能和数组的join正好相反。
  var str = "张三,李四,王五";
  var arr = str.split(",");
  ```

- 字符串替换

  ```javascript
  replace(searchValue, replaceValue)
  //参数：searchValue:需要替换的值    replaceValue:用来替换的值
  ```

- 练习

  ```javascript
  //1. 截取字符串"我爱中华人民共和国"，中的"中华"
  //2. "abcoefoxyozzopp"查找字符串中所有o出现的位置
  //3. 把字符串中所有的o替换成!
  //4. 把一个字符串中所有的空格全部去掉
  //5. 统计一个字符串中每个字符出现的次数
  ```



## 调试断点

> 断点调试是指自己在程序的某一行设置一个断点，调试时，程序运行到这一行就会停住，然后你可以一步一步往下调试，调试过程中可以看各个变量当前的值，出错的话，调试到出错的代码行即显示错误，停下。

调试步骤：

```html
  浏览器中按F12-->sources-->找到需要调试的文件-->在程序的某一行设置断点
```

调试中的相关操作:

```
    Watch:监视，通过watch可以监视变量的值的变化，非常的常用。
    F10:程序单步执行，让程序一行一行的执行，这个时候，观察watch中变量的值的变化。
    F8：跳到下一个断点处，如果后面没有断点了，则程序执行结束。
```

苦口婆心一下：

1. 代码调试的能力非常重要，只有学会了代码调试，才能学会自己解决bug的能力。初学者不要觉得调试代码麻烦就不去调试，知识点花点功夫肯定学的会，但是代码调试这个东西，自己不去练，永远都学不会。
2. 今天学的代码调试非常的简单，只要求同学们记住代码调试的这几个按钮的作用即可，后面还会学到很多的代码调试技巧。
3. ​
