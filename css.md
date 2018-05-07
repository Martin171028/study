## 一、CSS的概念

层叠样式表  (Cascading Style Sheets   )   => 可以发生相互层叠的样式表

基本框架思想:

.nav>ul>li>a

1. nav高度 设置背景颜色
2. ul:list-style:none 清除浮动
3. li:浮动
4. a:行内块:宽高(要与上面nav高度保持一致)





## 二、字体属性  font-swsf

1. font-size : 字体大小
2. font-weight : 字体的粗细
   - 数字 :  正常(400)、粗(700)
   - 关键字 : 正常(normal)、粗( **bold** )
3. font-style : 字体的样式
4. font-family : 字体类型
5. 连写 : 

```html
font: 样式 粗细 大小 类型 
font:  font-style font-weight font-size  font-family
```

font: italic bold 100px 宋体;

1. 记忆 : '稍微舒服' 'swsf'  ; 
2. 更爽的记忆 : ` font: italic bold 40px '宋体';`
3. 可以省略前两个


## 三、css样式:嵌套/行内/外联

1. **嵌套样式**

```html
<style>
    div {
    	color: red;
    }
</style>
```

2. **行内样式**

```html
<div style="color: red; font-size: 200px;">小可爱</div>​
```

3. **外联样式**

- 新建一个文件, 后缀叫 .css

- 在这个文件中直接通过 link 引入

  ```html
  <link ref="stylesheet" href="路径" >
  ```

**4. 三种样式的使用范围(记)**

| 样式名称 | 作用范围       | 存放位置              | 应用                     |
| ---- | ---------- | ----------------- | ---------------------- |
| 嵌套样式 | 整个页面       | head中的title下面     | 存放一些当前页面会用到的样式         |
| 行内样式 | 只能作用于当前标签  | 标签中通过style设置      | (页面只有这个标签需要这个样式)       |
| 外联样式 | 所有的页面都可以使用 | 在其他文件中,通过link标签导入 | 存放一些所有页面都会用到的公共样式, 项目中 |

## 四、"颜色"取值:rgb/英文/#ccc

color : 颜色 ;   属性取值可以是 :

1. 具体的颜色的英文单词: yellow, pink, red;

2. 使用十六进制颜色表示法  **#**666666  => **#**666

   取值范围:**#**0-9/a-f/A-F;

3. rgb 表示法

   rgb( 0, 0, 0 ) 分别表示 red green blue 的比重, 数值范围 0-255

   e.g:	(255,0,0)红色;(0,0,0)黑色;

   ​	(0,255,0)绿色;(255,255,255)白色

   ​	(0,0;255)蓝色;

4. rgba表示法, 最后一个表示透明度

   rgb( 0, 0, 0, **0.5** )  ;0-1越来越清晰

## 五、简单选择器 :标签/类/id

**一)、标签	选择器: 	p { };div { }**

效果 : 会将`所有的这类标签`都加上相同的属性



标签选择器的选择:

文字:换行=>不加粗=>p

​			加粗=>h

​	不换行=>一行显示多个=>span 

​			跳转=>a

图片:img--可以设置尺寸

​	background=>可以改变位置

列表:ul>li

​	dl>dt+dd

​	

**二)、类	选择器:	.red  { }	< p class="red**"      

> 需求2 : 四个都设置不同的颜色 : => 不同的标签可以 (ok) => 类选择器 => 先从标签哪里入手

需要给要设置的标签添加一个类名: class

```
<p class="red"> 小花 </p>
```

特点 : 

1. 一个标签可以使用多个类选择器 , 	
2. 一个类选择器 可以用在多个标签上;

**三)、id  选择器:   #id名  { }     < p  id="id名"**

> 需求3 : 都设置不同的颜色 不用类选择器 : id选择器

```
<style>
	#id名(选择器) {
		属性名1: 属性值1;
	}
</style>
```

效果: 会将拥有这个id名的标签加上对应的属性

特点 : **一对一**; 

  (一个标签只能用一个id选择器 ,一个页面上也只能用唯一的id)

```js
注意 : id 主要不是为了设置css样式,,而且为了后面的js使用
```

**四)、类名选择器 和  id 选择器的区别**

1. 类名 : 相当于人的名字  (可以重复)

   特点 : 

   1. 一个标签可以使用多个类选择器 , 	
   2. 一个类选择器 可以用在多个标签上;

2. id : 相当于身份证号码  (一个页面中只能有唯一的)

   特点 :   (一对一)

   1. 只能给一个标签设置这一个id名
   2. 一个标签也只能有一个id名;
   3. 一个网页也只能有一个id 

**id 不是专门给 css 使用的, 而是主要给 javascript 使用的**

## 六、 复杂选择器:*/并/交/后/子

**一)、 * 通配符选择器**

> 需求 :把页面内所有的元素都设置一个颜色为red

作用: 会将页面上所有的标签都设置这个属性

代码:

```html
<style>
	* {
		属性名: 属性值;
	}
</style>
```

注意: 通配符会去页面上一个个的遍历页面所有的标签,  然后给他们进行设置样式(效率低, 不要滥用)



**二)、 并集 选择器：	div，p { }     中间是逗号**

> 需求 : 把 div 和 p 盒子的设置红色  => 代码量 ↑

作用 : 将满足两种选择器类型的元素全部选择出来

代码 : 

```html
<style>
	选择器, 选择器 {
		属性名1: 属性值1;
	}
</style>
```

注意 : 用逗号隔开



**三)、 交集选择器:		p.red {  }     中间没有空格，标签选择器写在类选择器之前**

作用 : 从两个集合中选择他们相同的部分:

代码 : 

```css
p.zm {
	color: red;
}
选择器选择器 {
	属性名1: 属性值1;
}
```

两个选择器连起来写,,注意如果其中有标签选择器,要把标签选择器提前



**四)、 后代选择器    ：   .father  p{ }   中间有空格**

作用 : 选中满足条件的后代元素 (后代 : 儿子、孙子、重孙子......)

代码 : 

```html
<style>
	.father p {
		color: red;
	}
</style>

选择器 选择器 {
	属性名1: 属性值1;
	....
}
```

**五)、 子代选择器：	.father > p { }**

作用 : 选中满足条件的直接子代元素 (子代 : 儿子)

代码 : 

```css
<style>
	.father > p {
		color: red;
	}
</style>

选择器 > 选择器 {
	属性名1: 属性值1;
	....
}
```



## 七、" text "属性  indent/align/decoration

1. **text-indent** 

   - 作用 : 设置首行缩进
   - 使用 : `text-indent = 2em`
   - 注意: 单位是 em, 一个文本的宽度 
   - 2em 表示两个文本的宽度 (会以当前字体大小为基准)

2. **text-align**

   - 作用 : 设置文本的位置
   - 取值 :
     - center:  设置`内容`在容器中 **水平居中**
     - left:    设置`内容`在容器中 靠左
     - right:   设置`内容`在容器中 靠右​

3. **text-decoration**

   - 作用: 设置文本的装饰
   - 取值:
     1. none 没有任何装饰
     2. underline 下划线
     3. line-through 删除线

   > 这个看来 : 第一天讲的 strong、em、ins、del 已经全部都css替换掉了
   >
   > strong=font的bold, em=font的italic,  ins=underline下划线,del=line-through删除线

   ​

## 八、居中  

## margin: 0 auto的原理以及和text-align/line-height区别

```
margin: 0 auto;
```

作用: 可以让`容器`水平居中

原理:

```
margin 0 auto;=
margin-top:0;
margin-bottom:0;
margin-left:auto;
margin-right:auto;
```

div盒子默认:margin-right:auto;

auto的本质:自动均分margin的值;

使用的条件:

1. 有宽度;
2. 跨级元素;
3. margin(本质);



**margin和text-align的区别:**

text-align:center;内容居中;适用:**文本;行内;行内块;**

margin:0 auto;在容器内居中,有宽度的盒子(**块级**:就是本身有margin值才可以去平分设置)

**text-align和line-height的区别:**

text-align:center;水平居中

line-height:height;垂直居中

**作用范围:文本;行内;行内块;**



**块级元素**居中

1. margin 0 auto(水平)+margin-top(垂直)+解决塌陷问题(overflow:hidden)
2. 用transform:translate();见十六.定位中案例


## 九、CSS 特性:继承性/层叠性/优先级

**一)、继承性**

- 作用 : 子元素可以继承父元素的属性样式
- 可以继承属性 : 

```
text- align;indent;decoration
font- style;weight;size;family
line- height =>行高:垂直居中
color 
```

- 应用 : 在写页面之前,,我们一般会通过 body 设置一个字体, 让将来页面上所有的标签都能继承这个属性,统一设置默认页面风格 : 比如 `font: bold 40px '楷体'`
- **特殊性** :  **[ 介绍底层 ]**
  1. **a标签,** 有**颜色**, 不能通过继承设置, 要修改 a 标签的颜色, 直接作用在 a 标签上面
  2. **h标签**, 有**字体大小**,不能通过继承设置, 要修改 h 标签的大小, 直接作用在 h 标签上
  3. **div** 的**高度**如果不能设置,由内容决定 (没有内容, 高度为0), **宽度默认由父元素继承过来**

**二)、层叠性**

- 层叠性: 	是浏览器处理处理冲突的一个特性

- 作用: 如果一个属性通过两个选择器设置到同一个元素上面, 那么这个时候, 一个属性会被层叠掉

- 如果两个选择器设置不同的属性到同一个元素上面, 不会层叠

- 代码:

  ```css
  /* 优先级的问题 */
  .box { background: pink;}
  div {	background: green;
          font-size: 40px;
          color: red;
  }
  div { background: orange;}
  ```

**三)、优先级**

1. **优先级**

   ```js
   !important > 行内样式 > id > 类 > 标签 > 通配符 * > 继承

   记忆:
   最爱>唯一>身份证号>姓李>男>全部>继承
   ```

   **注意:  ! important  但是不能继承,继承之后就是最小的.**

2. **权重**

   - 权重作用 :多个选择器组合以后的优先级 ! 

   - 公式算法 : ( 0, 0, 0, 0);

     ```js
     第一个0 !important的个数, 
     第二个0 是id选择器的个数, 
     第三个0 对应类选择器的个数, 
     第四个0 对应标签选择器的个数, 
     ```

   - 代码:

   ```css
   div div { 
       color: red;
     }
     div .son {
       color: blue;
     }
     div #son {
       color: pink;
     }
     .father div {
       color: yellow;
     }
     .father .son {
       color: green;
     }
     .father #son {
       color: gray;
     }
     #father div {
       color: purple;
     }
   <div class="father" id="father">
   	<div class="son" id="son">葫芦娃</div>
   </div>
   ```

   - 比较 : 就是从第一个开始比较, 如果第一个大, 那么就大, 如果第一个一样, 那么就比第二个... 依次类推

   - 总结 : 权重其实就是优先级的算法, 优先级 是 层叠的表现

   - 算题使用步骤 :

     ```js
     第一步 : 先有没有具体定位到该标签, 继承==> pass掉
     第二步 : 使用公式 0.0.0.0  
     第三部 : 如果权重一样,那么就是最靠近的那个.(浏览器从后往前加载)
     ```

3. **选择器工作的原理**

   > 选择器在查找元素的时候, 不是从左往右找, 而是从右往左找的

   使用 : 1.工作中还是使用左到右的去找 (做了项目就知道了);

   ​	   2.面试问 ==>说从后往前;

   ​           3.做面试题的话, 容易找的从前往后,,不容易找的,从后往前;

## 十、背景属性

##  red/url()/no-repeat/center

**一)、背景相关的属性**

1. background-color: 背景颜色

2. background-image: 背景图片

   写法: background-image: url(图片的路径); // **默认情况下如果比容器要小, 他会平铺**

3. background-repeat: 背景是否平铺

   取值:

   - no-repeat 不平铺
   - repeat-x  在水平方向上平铺
   - repeat-y  在垂直方向上平铺
   - repeat    平铺 (默认)

4. background-position: 设置背景图片位置

   用法: background-position: x, y;

   取值:

   1. 数字 background-position: 0 0;  (设置背景图片左顶点的坐标)

   2. 方位名词  left right bottom top center

      左上: left top
      居中: center center

**二)、背景连写**

```
background: color image repeat position;
- color 或者 image 一般情况下只使用一个较多
如果只要颜色,可以省略颜色后面的.
如果只要图片,可以省略颜色.

如果分开写,下面的会覆盖上面的.
```

**三)、练习 : 英雄联盟**



## 十一、元素三种显示方式

## 块级/行内/行内块

**一)、块级元素  div, p ,h系列**

- 属性 : **display : block ;**(判定)
- 特点 : 
  1. 一行只能**显示一个**  (算不上缺点)
  2. 宽度继承父元素
  3. 可以**设置宽高**   (优点)

**二)、行内元素: span ,a**

- 属性: **display : inline  ;** 
- 特点 :
    1. 一行可以**显示多个**;  (优点)
    2. 宽度由内容决定
    3. **无法设置宽高**   (缺点)

**三)、行内块级元素:   input,img**

- 属性 :  display: inline-block ; 


- 特点 : 
  1. 一行可以**显示多个** (行内)
  2. **又能设置宽高**  (块级)

四**)、三种显示方式的转换**

- display: block; 转成块级
- display: inline-block; 转成行内块
- display: inline; 转成行内

**五)、练习 : 史上最丑导航**

![](md-imgs/cdh.png)

## 十二、伪类  : 锚伪类:lvha顺序

**一)、锚伪类**

> 回顾一下 **a链接的特性**;

```js
(1) a:link {
		color: red;
	}
	作用: 给a标签设置`没有被访问过`的样式

(2) a:visited {
		color: blue;
	}
	作用: 给a标签设置`访问过`的样式
	一般这个只设置 color, 其他属性会无效

(3) a:hover {
		color: pink;
		font-size: 20px;
	}
	作用: 给a标签设置 `鼠标悬停`的样式;也可以给其他标签使用;
	 补充:cursor:pointer:增加触摸时显示小手

(4) a:active {
		color: green;
		font-size: 30px;
	}
	作用: 给a标签设置 ` 激活(点击中) `的状态
```

**二)、锚伪类需要注意的一些特点**

​	-  注意: 使用锚伪类必须要按照顺序写

​	- a:link a:visited a:hover a:active

​	- 记忆方式: lvha, 看到lv包心里乐哈哈	

**三)、其他元素也能被鼠标悬停**

​	所有 :hover 也可以加给其他元素



## 十三、行高 ( line-height )

- 定义: 两行文本**基线**的距离


- 应用: 将行高设置等于容器的高度, 可以让文本**垂直居中**


- 注意: 行高是可以**继承**的

  **一)、行高的单位**

  取值:

  1. 具体的像素:30px

  2. em 

     em 会根据当前标签设置的字体大小计算长度
     例如: 如果当前标签字体大小为基数计算, 如果是16px, 那么 2em=32px

  3. 百分号 :%

     % 也是根据当前标签字体大小为基数计算
     例如: 如果当前标签字体大小为基数, 如果是16px, 那么 200% = 32px;

  4. ,直接写数字,不带单位:2

     也是根据当前标签字体大小为基数计算

  补充: 谷歌浏览器默认字体大小 16px;

  注意: 

  1. 在设置行高的时候, 如果单位是 em 和 %, 将来行高会先计算出值, 再继承给子元素
  2. 如果是 数字, 没有单位, 会先继承下来, 再根据子元素字体大小计算

  **二)、行高与font的关系**

  字体连写里面还有行高: font: font-style font-weight font-size/line-height font-family

  **line-height 如果写在 font 连写前面, 会被层叠掉**

## 十四、盒子模型  border/padding/margin

一)、**border**--边框

==>**border: 1px solid #ccc;**   =>  盒子的挡板

- **基本属性** : 

  1. border-width: 边框的宽度;  (eg: 10px);

  2. border-style: 边框的样式;  

     ```js
     solid : 实线 
     dashed : 虚线
     dotted : 点线
     ```

  3. border-color: 边框的颜色

     ```js
     1. 有颜色 : red/#fff/rgb()等
     2. 透明 : transparent
     ```

- 边框的连写:

  ```js
  border: border-width border-style border-color;
  border: 1px solid blue;  // 不要记上面那个,,就记这个 [超级重要]
  ```

- **分段写** : top、right、bottom、left

- 增加边框,,,盒子尺寸会增加

- **补充**

  1. **细线表格, 去掉单元格间的间隙**

     **边框合并 :**   **border-collapse: collapse;**

  2. 学会使用开发人员工具查看盒子模型

**二)、padding ** --内边距

**--- 盒子的泡沫,    记忆 : 顺指针 , 上右下左;  没有的找对面**

作用: 设置盒子与内容边框之间的距离, 内边距

取值:

1. padding: **40px;**

   给**上右下左**的内边距都设置了 40px 的距离

2. padding: **40px 80px;**

   给**上下**设置了40px, 给**左右**设置了80px内边距

3. padding: 40px 60px 80px;

   给**上40px, 左右60px, 下80px**的内边距

4. padding: 40px 60px 80px 100;

   上40 右80 下80 左100
   记忆: 顺时针, 上右下左;不足4个的看对面的值补足

单独设置: 

```
padding-top
padding-right
padding-bottom
padding-left 
```

**三)、计算盒子的大小**

注意: padding(盒子的填充物) 会改变盒子的大小(和日常生活有区别)

计算盒子大小的公式:

盒子宽: 左外边框+左内边框+内容+右内边框+右外边框

```
border-left-width + padding-left + width + padding-right + border-right-width
```

盒子高度: 

```
border-top-width + padding-top + width + padding-bottom + border-bottom-width
```

盒子大小是由: 边框, 填充, 内容决定的

我们之前设置的 **width 和 height** **只是设置内容的大小**

**四)、特殊情况下 padding 不会改变盒子的大小**

当一个大盒子包含一个小盒子, 并且大小盒子, **都是块级**元素, 小盒子**宽度继承**自父盒子, 这时候给小盒子加 **padding-left** **不会改变小盒子大小**



**三)、margin **

一)、 基本使用

作用: 设置盒子与盒子之间的距离

取值: 

1. margin: 10px; 

   设置 上下左右40px 的外边距

2. margin: 10px 20px; 

   设置 上下10px, 左右20px 的外边距

3. margin: 10px 20px 40px;

   设置 上10px, 左右20px, 下40px 的外边距

4. margin: 10px 20px 40px 80px;

   设置 上 10, 右20, 下40, 左80 的外边距

单独设置: 

```
margin-top
margin-right
margin-bottom
margin-left
```

**二)、 注意: 很多标签默认带有 margin 和 padding**

所以将来进行页面布局的时候, 一定要清除这些标签的默认 margin 和 padding	

例如: 

```
(1) body 标签: 自带 margin: 8px; 的属性
(2) p 标签: 默认带有 margin: font-size 0; 的值
(3) h 标签: 也默认带有 margin-top 和 margin-bottom
(4) ul标签: ul 标签默认带有上下的 margin, 和 padding-left
...
```

 清除的方法:

```
* {
	margin: 0;
	padding: 0;
}
```

我们在后期项目中, 会通过 css 初始化来进行重置样式

三)、强化练习:

1. **新闻列表**
2. **爱宠知识**

四)、margin 的两种特殊现象

**1. 外边距合并现象:**

- 水平排序:left和right同时设置会**叠加**;
- **垂直排序**:top和bottom同时设置会**合并**;选择值大一点的那个

如果两个 div 上下排序, 给上面一个 div 设置 margin-bottom, 给下面一个 div 设置 margin-top, 那么两个 margin 会发生合并现象, 合并成值较大的那个

#### **2. margin塌陷现象(简答题):**

如果一个大盒子中包含一个小盒子, 给小盒子设置 margin-top 大盒子会一起向下平移

解决方法:

1. 给父盒子加一个边框 :**border-top**

2. 给父盒子**加 padding-top**

3. 给父盒子设置属性 **overflow: hidden;**

   原因:会触发BFC(block farmating context )

   -->块级格式化上下文-->父盒子就会成为独立的容器

4. 浮动也可以解决 塌陷问题;

   原因:父盒子拖标(脱离了标准流)-->正常标准流-->排序:从左到右,从上到下

## 十五、浮动 float:

```css
 float: left;
 float: right;
```

**一)浮动的特点(选择题)**

标准流: 就是浏览器默认摆放盒子的顺序

**总结:(重点记忆)**

1. 浮动的元素会**脱标**=>飘起来=>比标准流高半个级别==>相当于是行内块元素,可以设置宽高,
2. 浮动的元素会被盒子的**边框限制**

具体解释:

1. 浮动的元素会脱离标准流 **(脱标**)

   ```
   如果一个元素按照正常的标准流来显示, 会在 html 中所属的位置占位, 后面的元素会紧跟着它, 但是浮动脱离了标准流, 将来在看到浮动的元素以后,就不能以正常的标准流来判断了 (浮动的元素在标准流中不占位置了)
   ```

2. 浮动以后的元素, 会**覆盖**在标准流的**元素**之上;浮动的元素级别比标准流的元素高半个级别;

3. 浮动的规则: **浮动找浮动 ,不浮动找不浮动**

   ```
   浮动找浮动: 只有写在同一个结构下面的浮动才会浮动找浮动
   ```

4. 浮动以后的位置是与原本不浮动之前的位置是对应的

5. 浮动的重点: 浮动的元素只会影响下面的元素:

   浮动的元素也是有限制的,收边框的限制;

6. 浮动的元素会改变显示方式

   ```
   不管元素是行内元素还是块级元素将来在显示的时候, 都会在同一行显示
   浮动以后的元素可以设置宽高

   总结: 浮动以后的元素的显示方式与行内块级元素一样
   ```

**二)浮动的案例练习**

1. 使用浮动完成网页的页面布局

   eg:新浪首页:

   版心:.w{

   width:900px;

   margin:0 auto;

   }

   可以建类,要浮动都浮动

2. 制作导航

   注意: 之前直接使用 a 标签 display: inline-block 制作导航是有问题的

   1. 导航与导航之间应该是列表关系, 如果想要将这些关系通过 html 语义化表示出来, 必须要用到 ul 标签
   2. 如果这些 a 标签不用其他的标签包裹起来, 那么将来浏览器会将这些 a 标签中的文字, 当做普通文本一起显示, SEO 在查看页面时, 认为该页面在作弊, 就是在进行关键字堆砌

   所以, 导航必须要用 ul 和 li 将 a 标签包裹起来



    步骤:
    1. 在ul中清除点,list-style:none;
    2. li里面设置浮动,让其水平排列;
    3. 设置具体的盒子格式;

   ```css
   <style>
     * {
       margin: 0 ;
       padding: 0 ;
    	 }
     ul {
       list-style: none;
    	 }
     ul>li {
       background: pink;
       float: left;
   	  }
     ul li a {
       width: 100px;
       height: 50px;
       line-height: 50px;
       text-align: center;
       display: inline-block;
       text-decoration: none;
    	 }
     ul li a:hover{
    	 background: blue;
   	}
   	</style>
   </head>
   <body>
   	<ul>
   		<li>
   			<a href="#">导航1</a>
   			<a href="#">导航2</a>
   			<a href="#">导航3</a>
   			<a href="#">导航4</a>
   		</li>
   	</ul>
   </body>
   ```

   ​

3. 文字环绕图片

#### **三)清除浮动**:4个方法(简答题)

**1. 浮动对页面的影响:**

子元素不浮动:父盒子高度由子元素撑开;

子元素浮动后,父盒子的高度=0==>会导致下面的补位上来.

浮动: float: left; float: right;
清除浮动: clear: both;

**2. 额外标签法   		创建块级+clear:both**

```css
 .clear {
		clear: both;
		}
 <div class="clear"></div>
```
**在浮动的盒子内部,** 再放一个**块级标签**, 在这个标签内使用 **clear: both**;

缺点:需要新增加一个盒子(不常用)

**3. 使用 overflow **=>触发bfc=>独立的容器.(没有超过父盒子多余的部分,可以使用)

找到浮动盒子的父元素, 再**在父元素中**添加一个属性, overflow: hidden; 

缺点:超过盒子的部分,会被裁剪掉(后面没有超过父盒子多余的部分 	可以使用overflow:hidden)

#### **4. 使用伪元素** **(最佳选择)**

伪元素: 在页面上不存在的元素, 但是可以通过  css 添加上去

```css
::after
::before
```

注意:  

1. 每个元素都可以添加自己的伪元素
2. 默认伪元素是行内元素, 不过可以通过 display 修改

清除浮动:(重要记忆)

```css
.clearfix::after {
    content: "";     	使用伪元素,必须要添加content=" "*/
    display: block;		设置为块级元素
    clear: both;		清除浮动的核心代码

    height: 0;			使其看不见三步
    line-height: 0;
    visibility: hidden;
}
```

区别伪类和伪元素:

伪类:   => .类:

伪元素:  => ::*/

**面试问题**

清除浮动的四个方法:

1.  额外标签法
2.  overflow:hidden;
3.  .clearfix;
4.  设置行高



## 十六、定位(简答题)  static/relative/absolute/fixed

```
默认情况下, 我们发现
left 是定位后相对于浏览器上边框的距离
top  是定位后相对于浏览器左边框的距离
```

**1. static: 静态定位**  

**默认**都是 position: static;  	所有标准流中的元素都是静态定位

**2. relative: 相对定位 (自恋型)**   自身位置   **没有脱标**

要配合 top,left,right,bottom 来使用

```
.two {
	background: yellow;
	position: relative;
	top: 20px;
	left: 20px;
}
```

以 .two **盒子原来的位置**发生偏移, 在垂直方向向下 20px, 在水平方向向右 20px;(**相反方向**)

注意点: 

1. 相对于原来的位置进行偏移
2. 设置了相对定位的元素在页面上**占据了位置**(**没有脱标**)

#### **3. absolute: 绝对定位    脱标**

使用的时候, 要配合 trbl 属性来使用

    .three {
    	background: green;
    	position: absolute;
    	top: 30px;
    	left: 30px;
    }
特点:

1. 绝对定位的元素,**没有父级元素**,, trbl 默认是相对于 **浏览器**来定位的
2. 绝对定位的元素,**有父级元素(没有定位)**, trbl 还是相对于 **浏览器**来定位的
3. 绝对定位的元素,**有父级元素,有定位(非static)**,  那么相对于**父元素**定位偏移
4. 绝对定位的元素在页面中**不占位置**;**脱标**:相当于是行内块,可以设置宽高;


**4. fixed: 固定定位 **   脱标

position: fixed;

可以独立使用,但最好还是和top,right,left,botoom;

特点:

1.  trbl 永远是相对于**浏览器**的边框
2.  固定定位的元素也**脱离了标准流**(不在页面中占据位置)


应用:

1. 固定定位的盒子最好放在body中,
2. 在设置顶部布局,需要固定,注意设置**宽高**,因为**脱标**了,类似行内块,继承不了父盒子的宽度.设置为**width=100%**;






**面试问题**:3个方法:讲后三个,因为第一个是默认的,静态定位.	



**绝对定位和固定定位:都要有宽高,因为定位会脱标,特点相当于行内块,WH要么内容内容撑开;**



**将来在写页面的时候, 是绝对定位与相对定位一起配合使用: (口诀) 子绝父相**

注意: 子绝父绝也可以, 只是子绝父相用的比较多

目的:给子盒子一个完美的定位.

A盒子的步骤:

1. 给A盒子的父盒子设置相对定位,
2. 给A盒子设置绝对定位;

**子绝父相定位居中案例:定位子盒子**

如果小盒子在大盒子中要定位并且水平居中

1. 先 left: 50%, 将小盒子在大盒子平移大盒子的一半
2. 再设置 margin-left: -(小盒子自身宽高的一半), 注意一定是负数, 那么将来小盒子就可以水平居中了

具体:

1. 子绝父相
2. 子盒子:left:50%;
3. margin-left:-50px;(子盒子宽度的一半)

如果子盒子的宽度也是变动,就要配transform(动画转换).

translateX:沿着X轴方向移动;

取值:

1. 具体值:-50px;

2. 百分比:-50%;

综合:要水平居中:

1. 子绝父相

2. 子盒子:

   left:50%;

   top:50%;

   transform:translateX(-50%);

   要水平垂直均居中:

   ransform:translate(-50%,-50%);


练习:新浪首页/尚合



## 十七、  z-index/vertical-align/overflow/

浮动和定位的级别:定位级别比浮动高;

1. 定位中的 **z-index**:

控制定位盒子的层级;(重要)

**默认值:auto;**

```css
z-index:20px;
```

默认情况下,是层叠的,后面的会层叠前面的

**2.vertical-align**:设置**图片和文字的对齐**方式;

取值:

- baseline:基线;
- bottom:底部对齐;
- middle:中部对齐;
- top:顶部对齐;

比较常见的,a;img,input都会涉及到;**优先给图片使用**,不行再试试文字;

#### **3.overflow: 溢出**

在父级盒子中

1. 盒子之间溢出:overflow:hidden;

   1. 盒子和文字之间溢出:取值:


```
hidden 如果文本超出盒子范围, 就隐藏(剪切)(较多)
visible (默认值)超出不裁剪
scroll   显示滚动条(没有超出盒子就没有滚动条)
auto   根据具体的情况, 判断是否要添加滚动条(较多)
```

#### 4.元素隐藏(简答题):

```css
overflow: hidden; 将超出的部分裁剪掉
	应用:剪切多余的元素空间;清除浮动;防止塌陷;
visibility: hidden; 元素隐藏, 占位置
	应用:伪元素清除浮动;占位置的隐藏,起到占位置的作用;
display: none; 元素隐藏, 不占位置
	应用:与display:bolck=>显示;切换一个元素的显示与隐藏;
```

## 十八、CSS3 扩展  ( 部分 )

- **html标签中的嵌套关系**

1. 行内元素里面只放行内元素(a链接除外,可以放图片==>效果:点击图片跳转)

2. 块级元素里面可以放行内元素和块级元素(除了p/h/dt标签,)

3. 总结:看特定语义放特定内容:

   3.1 p/ h/ span/ a/ dt 语义是放文本内容的,最好只放文本,

   3.2 div/ ul/ li 这种事当做容器,里面可以放文本/图片/盒子都可以

   ​		




#### 一 选择器  属性/结构伪类

- 属性选择器:选择器[属性] {}
  1. li [skill]          含有skill的;   (常用)
  2. li [skill="id"]     含有skill,属性值="id"   (常用)
  3. li [skill**^**="id"]   含有skill属性,以id**开头的**
  4. li [skill**$**="id"]   含有skill属性以id**结尾的**
  5. li [skill*****="i"]   含有skill属性,**含有i的都有**


- 结构伪类选择器-child系列

本质:选中 li元素的父元素的第几个孩子

1. li:first-child {} 选中第一个孩子 (常用).取值范围是从1开始,区别n是从0 开始;

2. li:last-child {} 选中最后一个孩子 (常用)

3. li:nth-child(数字) {}  指定第几个孩子 (常用)

4. li:nth-child(odd/even) {} 指定奇数/偶数的

5. li:nth-child(n) {} 选中所有;n的取值范围:从0开始

   li:nth-child(2n) {} 选中偶数

   li:nth-child(2n+1) {}选中奇数

   eg:第七列的一列,li:nth-child(7n)

   ​	前四个变成红色:(-n+4)

- 结构伪类选择器 nth-of-type(n)

本质:先找此元素的父元素下**同类型**的li,然后再去找第几个

比较区别:

nth-child:先找第几个,然后再判断类型;

nth-of-type:先找同类型的,然后再找第几个;

#### **二 阴影 text/box-shadow**

- 文字阴影:text-shadow:1px 2px 3px red;==>x轴偏移值 y轴偏移值 模糊度>=0 颜色

  多重阴影,逗号给开:1px 2px 3px red,2px 3px 4px green;


- 盒子阴影:box-shadow:1px 2px 3px 4px red inset;==>x轴偏移值 y轴偏移值 模糊度(>=0)  外延值(可正可负) 颜色  有显示内部阴影,没有显示外部阴影;

#### **三 边框圆角   border radius**

- border radius(边框半径)

  border radius:40px; 移动之后的原点,半径40px画圆==>变成圆角的效果

  border radius:20px 40px;==>左上20px,右上40px,右下20px,左下40px;

  border radius:20px 40px 60px 80px=>同上顺序,顺势针;

  取值:数字/百分比

#### **四 Input边框/textarea边框** 

- order:none;清除可见框;



- outline-style:none;清除聚焦边框;


​	可以使用border radius 来做圆角;



- 禁止textarea进行缩放 resize:none

#### 五 过度:translation:all 1s;

#### 六 双伪元素清除浮动(记)

​	display:table=display:block+触发BFC

```css
防塌陷:
	.clearfix::before,
	.clearfix::after {
		content:"";                               
		display:table;
	}
清除浮动:
	.clearfix::after {
		clear:both;
	}
	.clearfix {
	*zoom:1;
	}
注释:
 1. before触发BFC 防塌陷
 2. after:因为只有块级元素才能使用
因为是伪元素所以写content
伪元素清除浮动的核心代码:clear:both
兼容IE6/7 :zoom:1
```

#### 七 BFC块级格式化上下文(记)

Block Formatting Context:页面上的一个隔离的独立容器

触发BFC的方式:(了解==>最好记忆)

1. overflow(不为visible)
2. 浮动(float不为none)
3. display:table/table-cell
4. position的值不为relative/static

特点:

1. 触发BFC的盒子,就成为一个隔离的独立容器,里面子元素不会在布局上影响到外面的元素.

   应用:BFC=>防坍塌+清除浮动

2. 触发BFC的普通盒子,不会与浮动元素重叠.

   应用:圣杯布局:目的:适配屏幕的大小(当界面缩小,两边不变,中间内容减少,eg:淘宝首页)

#### 八 display 解决图片下面间隙:

给图片设置样式:display:block;

## 十九、 项目搭建

- 项目文件夹	：最大的文件夹，所有的项目文件都存放在这个文件夹里面 例如：pinyougou
  css文件夹	：专门用来存放css文件的文件夹
- 初始化css : base.css
- 公共css模块 : common.css
- 网页对应的css : 比如 : index.css 、list.css
- images文件夹：专门用来图片的文件夹
- fonts文件夹 ：专门用来存放字体相关的文件夹



## 二十、项目注意

#### 一)、转化为行内块特点方法:

1. display:inlne-block              ==> 可以设置宽高 + 一行多个

2. 浮动 : ( float:left 和 float:right)    ==> 可以设置宽高 + 一行多个

3. 定位 :  绝对定位和固定定位    ==> 可以设置宽高 + 一行多个

   > 以前讲过的一句话 :浮动和定位,都会让元素脱标 ==> 具有类似行内块的特点 : 
   >
   > 以后要给盒子设置宽高,如果不是具体定位,,可以使用浮动进行转化!!!

#### 二)、处理多个盒子水平一行

1. 用/转行内块
2. 用/转行内
3. 设置浮动 

#### 三)、合理使用标签 :

1. 布局 + 盒子 ==> div
2. 文字 => p , a , span , h
   - 是否占一行?  占一行 => p 和 h  、一行多个 ==> a和 span
   - 区分占一行的 ?  普通段落,细 ==> p、 文字粗大,标题 ==> h
   - 区分一行多个的??  可点击 ==> a 、 不可点击 ==> span
3. img 和 background 
   - 单纯的显示图片,两者都可以 img = div+background
   - 单纯的设置背景 ==> background
   - 图片和小盒子 ==> img

#### 四)、导航的a标签=>两种 : 宽度相等/padding相等;

#### 五)、设置导航内的a标签宽高

1. 设置 display:inline-block;
2. 浮动 => 脱标 => 类似行内块的特点;
3. display:block  => 因为li浮动了

#### 六)、合写的层叠问题

1. background层叠

```
background: red url(images.01.png) no-repeat center 
background: pink;

```

2. margin的层叠

```
margin: 0 auto !
margin-top:20;
```

3. line-height

```js
font : bold 15px 'sonhti';
line-height : 40px;

```

总结 :分开的写在合体的之后

#### 七)、logo + h1



## 二十一、网页SEO三大标签

#### 1、网页的title标签

title具有不可替代性，是我们的网页第一个重要标签，是搜索引擎了解网页的入口，和对网页主题归属的最佳判断点。

首页建议：网站名（产品名）- 网站的介绍 
例如：

`品优购-综合网购首选-正品低价、品质保障、配送及时、轻松购物！`   

`京东(JD.COM)-正品低价、品质保障、配送及时、轻松购物！`



#### 2、Description标签

针对网站的描述，是标题的一个补充，可以较为详细，一般不超过120个字，作用相对次之

```html
<meta name="description" content="品优购-专业的综合网上购物商城,销售家电、数码通讯、电脑、家居百货、服装服饰、母婴、图书、食品等数万个品牌优质商品.便捷、诚信的服务，为您提供愉悦的网上购物体验!" />
```

#### 3、Keywords关键字

搜索引擎的关注点之一

```html
<meta name="Keywords" content="网上购物,网上商城,手机,笔记本,电脑,MP3,CD,VCD,DV,相机,数码,配件,手表,存储卡,品优购" />
```



## 二十二、精灵图

一)、什么是精灵图 ? (淘宝)

就是将一些较小的图片放在一张大的图片上

好处: 将很多的小图片放在一张大图片,最终只要请求一次就行了, 可以减少对服务器的请求次数, 减轻服务器的压力



二)、精灵图的使用

一张大的图片上, 有很多小的图片, 那么如何将这个小的图片拿出来呢 ?

1. 必须要了解我们需要的小图片的大小, 以及在精灵图上的位置
2. 在页面上通过背景定位显示出来, 注意容器大小一定要和精灵小图片的大小一样大

```js
   1. 精灵图通过背景定位, 让所有的小图片都能显示
   2. 小盒子和图片大小一致
   3. 在ps 或者 fireworks中,通过切片,量的坐标 ,,直接取负值即可
```

------

强化练习1: 拼出自己的名字



## 二十三、字体图标

图片缺点: 

1. 增加了很多额外的"http请求"，大大降低网页的性能。
2. 图片不能很好的进行“缩放”，因为图片放大和缩小会失真。很多情况下我们希望图标是可以缩放的

而字体图标（iconfont)就可以解决这些问题

**优点: 本质是文字, 可以任意改变颜色, 大小, 不失真**



阿里iconfont字库

http://www.iconfont.cn/ 阿里的一个字体图标字库



使用步骤

1. 登录阿里 iconfont 字库, 将自己想要的图标加入购物车, 并创建一个新的项目

2. 下载字体图标文件包

3. 在项目目录新建 font 文件夹, 将字体图标文件包内所有文件拷贝进 font 文件夹

4. 在项目中引入字体css文件   (字体文件包中的 demo_fontclass.html 为说明书 )

   ```
   <link rel="stylesheet" href="font/iconfont.css">
   ```

5. 用类名使用  (字体文件包中的 demo_fontclass.html 为说明书 )

   ```
   <i class="iconfont icon-refresh"></i>
   ```

------



## 二十四、滑动门

利用已学技术,根据文本内容,让背景自适应,,,以创造出一些特殊的效果。(QQ聊天气泡)

画图演示 : QQ聊天气泡  

滑动门步骤 :

1. 左边 : 背景定位靠左
2. 中间 :x轴方向平铺
3. 右边 :背景定位靠右