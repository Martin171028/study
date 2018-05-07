# HTML

## 一、win快捷键

```js
Ctrl + Z:撤销上一个操作
Ctrl + Y:还原上一个操作 (sublime上使用有效)
ctrl + W 关闭窗口 
win + E:打开资源管理器	
Win + D : 切换到桌面 (重点记忆)
Win + R：快速运行，打开软件，cmd命令行等
	calc:运行计算器
	mspaint:运行画图工具
F5+右键重新加载+菊花 : 刷新 
Alt + f4:退出程序 
```

## 二、认识网页 (了解)

```js
1. 网页的基本元素: 文字、图片、超链接、视频、音频等等 
2. 网页本质: 代码组合  
3. 浏览器的作用: 将代码解析成网页,供用户访问   (记忆)
```

## 三、五大浏览器介绍

```js
浏览器:是网页运行的平台
五大浏览器 : IE(Edge)  Firefox火狐  Chrome谷歌  Safari  Opera欧鹏  (记忆)
```

> 谷歌 : 访问速度快、用户体验好、开发调试功能齐全

1. 浏览器内核 (了解)

  1.1 定义: 内核（**Rendering Engine**）(记忆)：“渲染引擎”/''浏览器内核”。

1.2 作用 : 将网页代码解析（如[HTML](http://baike.baidu.com/view/692.htm)、[JavaScript](http://baike.baidu.com/view/16168.htm)）并渲染出网页。

#### **1.3 内核的分类：(记忆)**

Trident：ie , [猎豹安全浏览器](http://baike.baidu.com/view/9971135.htm),[360极速浏览器](http://baike.baidu.com/view/4695482.htm),[百度浏览器](http://baike.baidu.com/view/4368758.htm)...

Gecko：Firefox

Webkit：[Safari](http://baike.baidu.com/view/110484.htm)

Blink(Webkit的升级版)：Chrome, Opera

## 四、web标准的三大组成部分

主要包括:   HTML（结构）、CSS（表现）和  JS（行为）三个方面。

## 五、HTML初识

1. HTML的概念

Html : 超级文本标记语言 (HyperText Markup Language) , 在浏览器上运行的一种标记语言。

编写html :  **就是给文本加上含有语义的标签**

2. #### HTML骨架架构 (固定结构)(记忆)

> 作用 : 让结构更加清晰

```html
<html>
	<head>
		<title></title>
	</head>
	<body>
		注意:html 页面上写其他的代码必须写在 body 中
	</body>
</html>
```
斜线:/:闭合的意思

## 六、HTML中的标签(重点)

1. **h 系列的标签 (Header) : 标题**

h1,h2,h3,h4,h5,h6

作用 : **给页面上的文字加上标题的语义**;

效果 :  h1,h2,h3,h4,h5,h6: 将文字放大、加粗.并且逐渐变小。可以**设置宽高,块级元素**（h1标签是最大的。）

注意 : 一个页面只能有一个 h1 标签  , (SEO);

2. p 标签 (Paragraph) : 段落

作用:   **给页面上的一段文字加上段落的语义**

特点：	单独占一行

​		段落间存在间隙

**3. hr 标签 (Horizontal Rule)**

作用: 在页面上显示一条`横线` (没有语义, 用的比较少)

代码: `<hr />`

**4. br标签 (break row=行)(col=列)		(记忆)**

作用：换行。

代码：`<br />`

5. **b u i s 和strong ins em del**

  无语义效果	有语义

  b 	加粗	**strong** 

  u	下划线	**ins**

  i	倾斜	**em**

  s	删除	**del**

**6. img 标签 (图片标签 : image的简写)  [超级重要]**

作用: 在页面中显示一张图片

代码: `<img src="01.gif">`

属性: (还有其他很多, 下面几个必须掌握)

- src:路径
- alt: 图片加载不了, 会显示文字
- title:鼠标悬浮在图片上,介绍这张图片
- width: 宽;      图片宽高只设一个, 另一个等比例缩放
- height: 高;     宽高都设可能会变形, 一般只设一个

**src和herf的区别:**

src:全部加载进来

herf:关联起来

**路径问题-----> 八、路径问题**

#### 7. a 标签 (Anchor ) : 锚  [超级重要]

7.1、 基本用法

a 标签的其他名称:  超链接,  锚链接,a链接,a标签

作用:  一个页面跳转到另一个页面

代码:  `<a href="页面的路径"> </a>`

注意:  

1. 在 a 标签之内必须写上内容, 如果没有内容, 页面上会看不到
2. **a 标签不能嵌套**

7.2、 a 标签的属性

1. href:  a 标签跳转的目标地址

2. target

   (1) _blank:  保留原始页面, 再进行跳转

   (2) _self: 在当前页面, 进行跳转,默认的,不用设置

3. 相关标签 - base 标签

   作用: 可以为页面上所有的 a标签 设置跳转的方式（base标签一般放在title标签下面）

7.3、 a 标签的其他用法

1. 可以不跳转

   - href="#" (跳转到当前页面) 

2. **可以跳转到其他页面**

   ```html
   <a href="文件名#文件名"
   eg:想转到同目录下的名额为success.html文件里名为show的锚点:
      <a href="success.html#show">跳转</a>
   ```

3. 可以在当前页面进行定位

   (1) 设置 a 标签的 href 属性为 `#id名`,

   ```html
   <a href="#id名">点我定位</a>
   ```

   (2) 在页面的指定位置加入一个目标标签( 可以是任意标签 )

   ```html
   <p>目标标签</p>
   ```

   (3) 必须给这个标签加一个 id 名

   ```html
   <p id="id名">我是目标标签</p>
   ```

4. 可以在跳转的页面进行定位

   ```html
   <a href="文件名#id名"></a>
   ```

5. 可以进行下载 ; 

   ```html
   <a herf="文件名">文本</a>
   ```


8. 标签的分类

- 双标签: 有开始, 有结束, 开始和结束之间存在内容

```
<h1>哈哈</h1>
<p>哈哈啊</p>
```

- 单标签: 只有一个标签, 自己闭合自己

```
<hr />  <br />
```

9. 标签的属性

`<img src="01.gif">`

属性为 HTML 元素提供附加信息，img标签中的src就是img标签的一个属性。

## 七、 Sublime 的使用

1. sublime 快捷键

- 新建文件: `ctrl + n`


- 显示侧边菜单: `ctrl + k  ctrl + b`  (按照 ctrl 不要送,再先后点击 k 、b)
- 生成结构代码: `html:5 + tab` 或者 `! + tab`   (前提:必须是后缀.html文件)
- 快速复制一整行 `ctrl + shift + d`
- h1 + tab => <h1></h1>

## 八、路径问题

第一种: 绝对路径(一般不用)

带有盘符的路径: `C:\Users\Mawenxing\Desktop\代码\01.gif`

#### 第二种: 相对路径

页面是一个文件, 图片也是一个文件, 需要在页面上输出图片, 所以需要 **图片相对于文件的路径**

(1) 如果页面与图片同一级目录,  直接文件名引入即可

```html
<img src="2.jpg">
```

(2) 如果图片在同级目录image文件夹下

```html
<img src="image/1.jpg">
```

(3) 如果图片 在页面的 上一级目录

```html
<img src=”../2.jpg” >
```
路径访问原则: 通过 / 可以来到下一级目录, 通过 ../ 可以来到上一级目录

问题: 那么将来我们在实际开发中到底是用绝对路径，还是用相对路径？？

只要不出意外情况都是用相对路径：**因为相对路径的可移植性要强**。



## 九、结构中每个标签的含义

1. #### DOCTYPE : 文档类型

**规范** :  HTML 或 XHTML 规范

`html:xt` XHTML规范, 已经淘汰了, 一些特别老的网站会有,  知道即可

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
```

`html:5`  HTML5规范, 非常的简洁

```
<!DOCTYPE html>
```

2. html 标签

作用: 所有html中标签的一个根节点。

lang: 用来设置当前页面的语言

> en-英文 zh-中文
>
> 英文的意思并不是告诉浏览器,我们这就是纯英文的,而且告诉浏览器我们的内容以英文为主,,提高浏览器的渲染性能

```
<html lang="en">
</html>
```

3. head 标签

作用：用于存放：

title, meta, base, style, script, link

注意:在head标签中我们必须要设置的标签是title, 其他可有可无 

4. body 标签

作用：页面在的主体部分，用于存放页面中的html标签

p, h, a, b, u, i, s, em, del, ins, strong, img

```
<body></body>
```

5. meta 标签

作用: **设置网页的元信息**

注意：meta中设置的所有的内容在页面都不会显示,  在其中可以设置编码格式、样式、关键字等等

设置字符集（编码格式）：

​	`	<meta charset="UTF-8">`

**Charset（字符集的格式）**：UTF-8.

![字符集选择](C:\Users\Marti\Desktop\笔记\笔记内插图\字符集选择.PNG)

 **最常见的字符集**

- utf-8: 国际化的字典, 字体库, 收录是全世界所有的语言中的文字。

  1汉字 = 3个字节

- gbk: 收录了汉字, 还加了港澳台的文字

  1个汉字= 2个字节

 **约定：将来我们在整个学习过程中都用utf-8, ( 国际化 ) ;**

6. title 标签

作用：让页面拥有一个属于自己的标题。

注意：title中的文本在 seo 中占有很大的权重, 不能乱写



## 十、SEO 与 标签语义化

#### 1. SEO : 搜索引擎优化  (记忆)

作用：用来优化网站，使用网站在搜索引擎上的排名靠前

百度自己写的一个程序(爬虫)来收录每个网站的信息。

1. 花钱买排名;缺点：烧钱。

2. 将页面做成静态页面（html）(了解)

3. 发外链（网站就越受欢迎，将来被用户搜索出来的机会就要大）

4. 页面的友好性（语义化规范）：

   标签语义化的应用：每个html标签都有属于自己的语义，有使用标签时候要一定要了解每个标签的语义，合理使用。（**在合适的地方使用合适的标签**。）

#### 2. 语义化的好处   (记忆)**

1. 对搜索引擎的友好（将来网络爬虫进入页面之后可以很方便的得到页面的重要信息。）
2. 提升用户体验 (css加载不出来也能看出重要性)
3. 利于代码的可读、维护、提高开发效率. (网页源代码方便查询)

![SEO优化](C:\Users\Marti\Desktop\笔记\笔记内插图\SEO优化.PNG)

## 十一、列表

#### ul/ol/dl

作用：页面有一些数据需要显示。

无序列表:

- 苹果
- 西瓜

有序列表:

1. 一年级
2. 二年级

**1. 无序列表 ul ( Unordered List )   [重要]**

语义: 一组没有顺序的数据

```html
<ul>
  <li></li>
  <li></li>
</ul>
```

1. 无序
2. ul 要配合li使用,内部只能放 li 标签

3. li 标签是个容器,常见放a标签;


```html
<li><a herf=""></a></li>
```

**2. 有序列表 ol**

语义：一组有顺序的数据。

```html
<ol>
	<li></li>
	<li></li>
</ol>
```

注意: 有序列表中的数据都是由顺序的

**现在一般情况下ul标签用的比较多，ol标签用的比较少。**

**3. 自定义列表 dl**

作用：显示一段数据，格式自己定义

> dt  :  标题
>
> dd :  列表

```html
<dl>
	<dt></dt>
	<dd></dd>	
	<dd></dd>
</dl>
```

## 十二、Html 中空格的合并现象--转译符

特点 : 无论在页面有同时出现多少个空格、缩进、换行,  浏览器在解析的时候,只会当一个空格显示。

结论 :  html中对空格、缩进、换行不敏感, 如果同时出现多个空格、缩进、换行, 页面只把它们当做一个空格解析

**html 中特殊字符对应的 转译符 :**

![zifu](C:\Users\Marti\Desktop\笔记\笔记内插图\zifu.png)

## 十三、 表格 table [难点]

作用：用来将数据以表格形式显示出来。

```js
// 标签认知 : 
<table></table> : 代表 表格
<tr></tr> : 代表一行 (row : 行 )
<td></td> : 代表一个标准单元格
<th></th> : 代表一个表头单元格
```

1.创建表格  (画图)

![table01](C:\Users\Marti\Desktop\笔记\笔记内插图\table01.png)

```html
<table>
	<tr>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td></td>
		<td></td>
	</tr>
</table>
```

| 属性          | 作用                         |
| ----------- | -------------------------- |
| border      | 边框                         |
| width       | 给表格设置宽(高不会等比例变动)           |
| height      | 给表格设置高                     |
| cellspacing | 规定 单元格 与 单元格 之间的空白; 一般为0;  |
| cellpadding | 单元格内部 边框 与 内容 的空白          |
| align       | 对齐方式;left(默认)/center/right |

**虽然我们可以使用table中的标签来设置标签的一些样式，但是最好不要用，因为将来凡是与样式相关内容都是由css来设置的**

#### **2.表格中的其他标签**

> 成绩表格演示 , table>tr>td

| 标签                    | 作用               | 特点                       |
| --------------------- | ---------------- | :----------------------- |
| `<caption></caption>` | 标题标签             | 文字居中;常见嵌套h系列标签;写在table下面 |
| `<thead></thead>`     | 表头标签/表头部分        | 行高自适应                    |
| `<th></th>`           | 起到表头、标题的作用、在tr里面 | 文字加粗居中                   |
| `<tbody></tbody>`     | 表体标签             | 无明显变化                    |
| `<tfoot></tfoot>`     | 表尾标签             | 行高自适应                    |

**3.合并单元格 (左上原则)**

跨行合并：属性: rowspan ，留住最上，删除其他

```html
<tr rowspan:"2"></tr>
```

跨列合并：属性: colspan，留住最左，删除其他

```html
<tr colspan:"2"></tr>
```

注意:" _2_",数字表示合并几个单元格;  写在合并后留下的单元格里

![左上原则](C:\Users\Marti\Desktop\笔记\笔记内插图\左上原则.png)

> **总结** : 在早期的网站开发中，表格的使用非常的泛滥。
>
> 作业:

![table_1](C:\Users\Marti\Desktop\笔记\笔记内插图\table_1.png)

## 三、表单标签  [超级重点]

**表单目的 : 收集用户信息**

**1. input (输入框系列) 基本表单控件**

```html
<input 标签为单标签,  
 type :  用于指定 `不同的控件` 类型  
```

![form_exm](C:\Users\Marti\Desktop\笔记\笔记内插图\form_exm.png)

**2. 输入框 text 、 密码框 password**

```html
输入框: <input type="text" name="username" value="老王啊">   
密码框:
<input type="password" name="password" value="123456" maxlength="6"> 
```

- value 属性设置默认值
- name 属性, 用于获取数据,提交数据给后台   { username : 文本框里的值 }(ajax发送请求数据和获取input数据组成一个键值对)
- maxlength, 设置最大输入值

**3. 单选框 radio 、多选框 checkbox**

1. **单选框 radio**

   ```html
   性别: <input type="radio" name="sex" checked>男 
   	 <input type="radio" name="sex" > 女  
   ```

   - 通过name进行分组, 因为是单选框,只能选一个
   - 设置 checked 属性, 默认选中

2. **多选框 checkbox**

   ```html
   <!-- checkedbox 也可以通过 name 分组, 默认选中 checked -->
   爱好: <input type="checkbox" name="hobby" checked >吸烟
         <input type="checkbox" name="hobby" checked >喝酒
         <input type="checkbox" name="hobby">烫头  
   ```

**4. 文件选择框 file**

​	作用: 选择文件,可以用于文件上传

```html
<input type="file">   单文件上传
<input type="file" multiple>   多文件上传
```

**5. 表单按钮:提交,重置,普通,图片**

1. **提交按钮**  

   ```html
   <input type="submit">
   ```

   作用: 将表单的内容提交

   注意: 需要配合 Form 表单一起使用

2. **重置按钮**

   作用: 可以重置表单内容成默认值

   ```html
   <input type="reset">
   ```

3. **普通按钮** 

   ```html
   <input type="button">    // 配合后面的js使用
   ```

4. **图片按钮**

   作用: 也可以提交表单, 需要设置图片 src 属性

   ```html
   <input type="image" src="a.jpg">
   ```

#### 6.select 下拉菜单

语法格式如下: 

```html
<select>
  <option>选项1</option>
  <option selected>选项2</option>
  <option>选项3</option>
  ...
</select>
```

注意 :  option 中定义selected属性项默认选中。

**7. textarea 控件 (文本域)**

textarea 用于创建多行文本输入框, 他的属性 cols 和 rows 可以调整宽高, 一般用以后的css调整高度

语法如下：

```html
<textarea name='content' cols="每行中的字符数" rows="显示的行数">
  文本内容
</textarea>
```

**8. Form 表单域**

form标签被用于定义表单域, 将各种表单包裹起来, 用于表单提交

语法格式：

```html
<form action="url地址">
  各种表单控件
</form>
```

属性：action 用于指定 处理请求的 服务器url地址。

#### **9. label 标签 [理解 记忆]**

`示例 : 新浪网页注册`

作用： 让 ' 文本 ' 绑定到一个 ' 表单元素 ' 上(简单讲**;在勾选单选框/多选框时,可以点击文本就直接勾选**)

语法：`<label>  我是 label  </label>`

1. 写 for ，值为 id，规定 label 与哪个表单元素绑定

   ```html
   性别 : 
   <input  id="nan" name="sex" type="radio"> <label for="nan">男</label>
   <input  id="nv" name="sex" type="radio"> <label for="id名">女</label>   

   // 步骤 : 1. 先写label,for='id名'
             2. 在给input一个id,
   		 3. 补齐
   ```

2. 不写 for ，默认绑定 label 内的表单控件

   ```html
   <label>
     <input type="radio" name="sex"> 男
   </label>
   ```

## 四、没有语义的布局标签:div/span  [记忆]

Html中大部分的标签都具有语义，所在使用的时候一定要注意。还有一部分标签没有语义，**没有语义**的标签一般只用来**进行布局**。  (**规定一个一个区域空间)**

**1. div:div盒子**

```html
<div>段友出征</div><div>寸草不生</div>
```

特点:   1. W由屏幕宽度解决;    H 自适应

​	    2. 独占一行

**将来我们在进行页面布局的时候用的最多**

**2. span**

```
<span></span>
```

特点：1. W、H由内容来决定，

2. 一行里面可以显示多个。

**能进行布局的除了这些没有语义的标签,,,还有一些有语义的,,,,就是html5 新增的语义标签**

## 五、HTML5新标签与特性 (部分)

**5.1.HTML5新增语义标签(记忆)**

文字：    头部   底部  导航   文章  区块   侧边栏

- **header：定义文档的 ' 头部  '   = 语义(头部) + div**

- **nav：定义 ' 导航 ' 部分  = 语义(导航) + div**

- **footer：定义文档的 ' 底部 '  = 底部语义 + div**

  ------

- article：定义文章内容


- section：定义文档中的区块

- aside：一般用作侧栏

  ![h5新标签](C:\Users\Marti\Desktop\笔记\笔记内插图\h5新标签.png)

**5.2.HTML5 表单 加强(了解)**

> 对于input框，我们之前有text、password、radio、checkbox, file等类型，HTML5新增了很多的类型，具体如下：

| 类型     | 示例                      | 描述                     |
| ------ | ----------------------- | ---------------------- |
| date   | `<input type="date">`   | 日期类型(选日期)              |
| time   | `<input type="time">`   | 时间类型(选时分)              |
| month  | `<input type="month">`  | 月份类型(选月份)              |
| week   | `<input type="week">`   | 星期类型(选星期)              |
| number | `<input type="number">` | 数字类型(只能输数字)            |
| search | `<input type="search">` | 搜索类型(手机端会显示搜索按钮, 更具语义) |
| color  | `<input type="color">`  | 颜色类型(取色器)              |
| range  | `<input type="range">`  | 滑动条类型                  |



#### **5.3.其他表单新属性(记忆)**

| **用法**                                   | **属性**          | **含义**      |
| ---------------------------------------- | --------------- | ----------- |
| `<input type="text" placeholder="请输入用户名">` | **placeholder** | 提示用户输入对应的信息 |
| `<input type="text" autofocus>`          | **autofocus**   | 自动获得焦点      |
| `<input type="file" multiple>`           | **multiple**    | 多文件上传，可选多文件 |

5.4.多媒体标签01 -  audio 音频

- 作用 : 播放音频

- 处理

  ```js
  <!-- 1. 基本属性 
       2. 加载失败 
       3. 兼容性处理  -->
  ```

- 属性 :  

1. autoplay 自动播放,  
2. controls 是否显示播放控件, 
3. loop 循环播放

- 兼容性处理:

  ```html
  <audio loop  controls autoplay>
    <source src="music/music.mp3">
    <source src="music/music.ogg">
    您的版本过低,请升级高级版本 <a href="http://www.baidu.com">点击下载</a>
  </audio>
  ```

**5.5.多媒体标签02 -  video 视频**

autoplay 自动播放    controls 是否显示默认播放控件   loop 循环播放

用法和 audio 相似, 区别: 可以设置宽高
