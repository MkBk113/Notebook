# 基础认知

### 引入方式

- 行内式
- 内嵌式
- 外联式

## 基础选择器

### 标签选择器

结构: **标签名 { css属性名：属性值； }**

作用：通过标签名，找到页面中所有这类标签，设置样式

注意点:

- 标签选择器选择的是一类标签，而不是单独某一个
- 标签选择器无论嵌套关系有多深，都能找到对应的标签

### 类选择器

结构: **.类名 { css属性名：属性值； }**

作用：通过类名，找到页面中所有带有这个类名的标签，设置样式

注意点：

1. 所有标签上都有class属性，class属性的属性值称为类名（类似于名字）
2. 类名可以由数字、字母、下划线、中划线组成，但不能以数字或者中划线开头
3. 一个标签可以同时有多个类名，类名之间以空格隔开
4. 类名可以重复，一个类选择器可以同时选中多个标签

### id选择器

结构：**id属性值 { css属性名：属性值； }**

作用：通过id属性值，找到页面中带有这个id属性值的标签，设置样式

注意点：

1. 所有标签上都有id属性
2. id属性值类似于身份证号码，在一个页面中是唯一的，不可重复的！
3. 一个标签上只能有一个id属性值
4. 一个id选择器只能选中一个标签

### 类与id的区别

class类名与id属性值的区别

- **class类名相当于姓名，可以重复，一个标签可以同时有多个class类名**
- **id属性值相当于身份证号码，不可重复，一个标签只能有一个id属性值**



类选择器与id选择器的区别

- **类选择器以 . 开**
- **id选择器以 # 开头**



实际开发的情况

- **类选择器用的最多**

- **id一般配合js使用，除非特殊情况，否则不要使用id设置样式**

- **实际开发中会遇到冗余代码的抽取 （可以将一些公共的代码抽取到一个公共的类中去）**

### 通配符选择器

结构: **{ css属性名：属性值； }**

作用：找到页面中所有的标签，设置样式

注意点:

1. 开发中使用极少，只会在极特殊情况下才会用到
2. 用于去除标签默认的margin和padding

## 字体和文本样式

### 字体大小

属性名：`font-size`
取值：`数字 + px`
注意点：

1. 谷歌浏览器默认文字大小是`16px`
2. 单位需要设置，否则无效

### 字体粗细

属性名：`font-weight`

取值:

| 效果 |  取值  |
| ---- | :----: |
| 正常 | normal |
| 加粗 |  bold  |
| 正常 |  400   |
| 加粗 |  700   |

注意点：

1. 不是所有字体都提供了九种粗细，因此部分取值页面中无变化
2. 实际开发中以：正常、加粗两种取值使用最多。

### 字体样式(是否倾斜)

属性名：`font-style`

取值：

- ``正常（默认值）：normal``
- `倾斜：italic`

### 常见字体系列(了解)

无衬线字体（sans-serif）

特点：文字笔画粗细均匀，并且首尾无装饰
场景：**网页中大多采用无衬线字体**
常见该系列字体：**黑体、Arial**

衬线字体（serif）
特点：文字笔画粗细不均，并且首尾有笔锋装饰
场景：**报刊书籍中应用广泛**
常见该系列字体：**宋体、Times New Roman**

等宽字体（monospace）
特点：每个字母或文字的宽度相等
场景：**一般用于程序代码编写，有利于代码的阅读和编写**
常见该系列字体 **Consolas、fira code**

### 字体系列 font-family

属性名：**font-family**

常见取值：**具体字体1,具体字体2,具体字体3,具体字体4,...,字体系列**

- 具体字体："Microsoft YaHei"、微软雅黑、黑体、宋体、楷体等……
- 字体系列：sans-serif、serif、monospace等……

渲染规则:

1. 从左往右按照顺序查找，如果电脑中未安装该字体，则显示下一个字体
2. 如果都不支持，此时会根据操作系统，显示最后字体系列的默认字体

注意点:

1. 如果字体名称中存在多个单词，推荐使用引号包裹
2. 最后一项 **字体系列不需要引号包裹**
3. 网页开发时，尽量使用系统常见自带字体，保证不同用户浏览网页都可以正确显示

### 层叠性

如果给同一个标签设置了相同的属性，此时样式会层叠（覆盖），写在**最下面的会生效**

### 字体font相关属性的连写

取值: `font : style weight size family;`

省略要求: **只能省略前两个，如果省略了相当于设置了默认值**

### 文本缩进

属性名：`text-indent`

取值: 

- 数字+`px`
- 数字+`em`（推荐：1em = 当前标签的font-size的大小）

### 文本水平对齐方式

属性名：`text-align`

| 属性值 |   效果   |
| :----: | :------: |
|  left  |  左对齐  |
| center | 居中对齐 |
| right  |  右对齐  |

如果需要让文本水平居中，text-align属性给**文本所在标签（文本的父元素）**设置

### 文本修饰

属性名：`text-decoration`

|    属性值    |       效果       |
| :----------: | :--------------: |
|  underline   |   下划线(常用)   |
| line-through |  删除线(不常用)  |
|   overline   | 上划线(几乎不用) |
|     none     |     无装饰线     |

开发中会使用 `text-decoration : none `; 清除a标签默认的下划线

### 行高

属性名：`line-height`

取值: 

- 数字+px
- 倍数（当前标签font-size的倍数）

应用：

1. 让**单行文本**垂直居中可以设置` line-height : 文字父元素高度`
2. 网页精准布局时，会设置 `line-height : 1 `可以取消上下间距

行高与font连写的注意点：

- 如果同时设置了行高和font连写，注意覆盖问题
- font : style weight size/line-height family ;

### 颜色常见取值

![image-20220719124841404](assets/3531513221.png ':size=50%')

### rgba透明表示方法

**a的取值范围：0~1**

**1:完全不透明**

**0:完全透明**

**`rgba ( 0 , 0 , 0 , 0.5 ) 可以省略写成 rgba ( 0 , 0 , 0 , .5 )`**

## Chrome调试工具

![image-20220719124716543](assets/359647573.png ':size=50%')

![image-20220719132638201](assets/3557202731.png ':size=50%')

## 选择器进阶

### 后代选择器：空格

选择器语法：**选择器1 选择器2 { css }**

结果: 在选择器1所找到标签的后代（儿子、孙子、重孙子…）中，找到满足选择器2的标签，设置样式

### 子代选择器：>

选择器语法  **选择器1 > 选择器2 { css }**

结果：在选择器1所找到标签的子代（儿子）中，找到满足选择器2的标签，设置样式

### 并集选择器：,

选择器语法： **选择器1 ， 选择器2 { css }**

结果：找到 选择器1 和 选择器2 选中的标签，设置样式

### 交集选择器：紧挨着

选择器语法： **选择器1选择器2 { css }**

结果: （既又原则）找到页面中 既 能被选择器1选中，又 能被选择器2选中的标签，设置样式

### Emmet语法

![](assets/272475721.png ':size=50%')

### hover伪类选择器

选择器语法：`选择器:hover { css }`

作用：选中鼠标悬停在元素上的状态，设置样式

## 背景相关属性

### 背景颜色

属性名：`background-color（bgc）`

注意点：

- 背景颜色默认值是透明： rgba(0,0,0,0) 、transparent
- 背景颜色不会影响盒子大小，并且还能看清盒子的大小和位置，一般在布局中会习惯先给盒子设置背景颜色

### 背景图片

属性名：`background-image（bgi）`

注意点：

- 背景图片中url中可以省略引号
- 背景图片默认是在水平和垂直方向平铺的
- 背景图片仅仅是指给盒子起到装饰效果，类似于背景颜色，是不能撑开盒子的

### 背景平铺

属性名：`background-repeat（bgr）`

![](assets/1808294319.png ':size=50%')

### 背景位置

属性名：`background-position（bgp）`

![](assets/1442990889.png ':size=50%')

**方位名词取值和坐标取值可以混使用，第一个取值表示水平，第二个取值表示垂直**

### 背景相关属性连写

属性名：`background（bg）`

书写顺序:  `background：color image repeat position`

### background连写拓展

![](assets/670039339.png ':size=50%')

注意点：

- background-size和background连写同时设置时，需要注意覆盖问题

解决：

要么单独的样式写连写的下面

要么单独的样式写在连写的里面

### img标签和背景图片的区别

需求：需要在网页中展示一张图片的效果？

方法一：直接写上img标签即可

- img标签是一个标签，不设置宽高默认会以原尺寸显示

方法二：div标签 + 背景图片

- 需要设置div的宽高，因为背景图片只是装饰的CSS样式，不能撑开div标签

## 	元素显示模式

### 块级元素

属性：`display：block`

显示特点：

1. 独占一行（一行只能显示一个）
2. 宽度默认是父元素的宽度，高度默认由内容撑开
3. 可以设置宽高

代表标签:   div、p、h系列、ul、li、dl、dt、dd、form、header、nav、footer……

### 行内元素

属性：`display：inline`

显示特点：

1. 一行可以显示多个
2. 宽度和高度默认由内容撑开
3. 不可以设置宽高

代表标签： a、span 、b、u、i、s、strong、ins、em、del……

### 行内块元素

属性：`display：inline-block`

显示特点：

1. 一行可以显示多个
2. 可以设置宽高

代表标签：

input、textarea、button、select……

特殊情况：img标签有行内块元素特点，但是Chrome调试工具中显示结果是inline

### HTML嵌套规范注意点

块级元素一般作为大容器，可以嵌套：文本、块级元素、行内元素、行内块元素等等……

但是：**p标签中不要嵌套div、p、h等块级元素**

a标签内部可以嵌套任意元素

但是：**a标签不能嵌套a标签**

### 居中方法总结

![image-20220719131652634](assets/1461623093.png ':size=50%')

## CSS三大特性

### 继承性

特性：子元素有默认继承父元素样式的特点（子承父业）

可以继承的常见属性：

color
font-style、font-weight、font-size、font-family
text-indent、text-align
line-height**

### （拓展）继承失效的特殊情况

如果元素有浏览器默认样式，此时继承性依然存在，但是优先显示浏览器的默认样式

1. a标签的color会继承失效
- 其实color属性继承下来了，但是被浏览器默认设置的样式给覆盖掉了
2. h系列标签的font-size会继承失效
- 其实font-size属性继承下来了，但是被浏览器默认设置的样式给覆盖掉了
3. div的高度不能继承，但是宽度有类似于继承的效果
- 宽度属性不能继承，但是div有独占一行的特性

### 层叠性

给同一个标签设置**不同**的样式 → 此时样式会层叠叠加 → 会**共同作用**在标签上

给同一个标签设置**相同**的样式 → 此时样式会层叠覆盖 → 最终写在**最后**的样式会生效

当样式冲突时，只有当选择器优先级相同时，才能通过层叠性判断结果

### 优先级

– 当同一个元素指定多个选择器，就会有优先级的产生

- 选择器相同，则执行层叠性
- 选择器不同，则按权重

| 选择器                   | 权重       |
| ------------------------ | ---------- |
| 继承或者 *               | 0，0，0，0 |
| 元素选择器（标签选择器） | 0，0，0，1 |
| 类选择器，伪类选择器     | 0，0，1，0 |
| ID选择器                 | 0，1，0，0 |
| 行内样式style=""         | 1，0，0，0 |
| ！important重要的        | 无穷大     |

- 类选择器权重为10
- 伪类选择器权重为10
- ID选择器权重为100

#### 优先级注意点

- 等级判断是从左到右，如果某一位数值相同，则判断下一位数值
- 继承的权重是0
- 权重可以叠加，但是永远不会有进位

#### 权重的叠加

- 权重叠加：如果是复合选择器，则会有权重的叠加，需要计算权重

```css
<head>
<style>
     li {
        color:green;
     }
/* li 的权重是 0,0,0,1  */
     ul li{
        color :red;
     }
/* 复合选择器权重叠加，ul li权重 0,0,0,1 + 0,0,0,1 =0,0,0,2 */
.nav li{
    color:pink;
}
/*  .nav li 权重 0,0,1,0 + 0,0,0,1 = 0,0,1,1 */
<style>
</head>
<body>
    <ul  class="nav">
          <li>大猪蹄子</li>
          <li>大肘子</li>
          <li>猪尾巴</li>
      
    </ul>
</body>
```

1. `div ul li`----------> 0,0,0,3
2. `.nav ul li` -------------->0,0,1,2
3. `a:hover` ---------------->0,0,1,1 /* 伪类选择器*/
4. `.nav a`-------------------->0,0,1,1

## 盒子模型

### 盒子模型组成部分

内容区域：content
边框区域：border
内边距区域：padding
外边距区域：margin**

### 边框

![](assets/1910901024.png ':size=50%')

### 边框（border）- 连写形式

例:   border : 10px solid red;

	### 边框（border）- 单方向设置

例:    border - 方位名词

### 盒子实际大小初级计算公式

盒子实际大小初级计算公式：

- 盒子宽度 = 左边框 + 内容宽度 + 右边框
- 盒子高度 = 上边框 + 内容高度 + 下边框

![QQ截图20220719160001](assets/3862459117.png ':size=50%')

### 内边距（padding）- 取值

![image-20220719160100730](assets/2835709840.png ':size=50%')

**规则：从上开始赋值，然后顺时针赋值，如果没有赋值的，看对面的！！**

### 内边距（padding）- 单方向设置

属性名：padding - 方位名词

属性值：数字 + px

### 不会撑大盒子的特殊情况

不会撑大盒子的特殊情况（块级元素）

1. 如果子盒子没有设置宽度，此时宽度默认是父盒子的宽度
2. 此时给子盒子设置左右的padding或者左右的border，此时不会撑大子盒子

### CSS3盒模型（自动内减）

给盒子设置属性 `box-sizing : border-box `; 即可

### 外边距（margin）- 取值

![image-20220719160445126](assets/2835709840.png ':size=50%')

**记忆规则：从上开始赋值，然后顺时针赋值，如果没有赋值的，看对面的！！**

### 外边距（margin） - 单方向设置

属性名：margin - 方位名词

属性值：数字 + px

### margin单方向设置的应用

![image-20220719160613849](assets/3013294541.png ':size=50%')

### 清除默认内外边距

浏览器会默认给部分标签设置默认的margin和padding，但一般在项目开始前需要先清除这些标签默认的
margin和padding，后续自己设置

### 外边距正常情况

**<font color=red>水平方向</font>**

![](assets/387308293.png ':size=50%')

### 外边距折叠现象 – ① 合并现象

**<font color=red>垂直方向</font>**

![](assets/2314003273.png ':size=50%')

### 外边距折叠现象 – ② 塌陷现象

**<font color=red>互相嵌套</font> 的 <font color=red>块级元素</font>，子元素的 <font color=red>margin-top</font> 会作用在父元素上**

![](assets/2586926536.png ':size=50%')

解决方案:

1. 给父元素设置border-top 或者 padding-top（分隔父子元素的margin-top）
2. 给父元素设置overflow：hidden
3. 转换成行内块元素
4. 设置浮动

### 行内元素的margin和padding无效情况

<font color=red>行内元素 margin padding</font>

1. 水平方向的margin和padding布局中有效
2. 垂直方向的margin和padding布局中无效！

## 结构伪类选择器

### 选择器

![](assets/1200919740.png ':size=50%')

n的注意点：

1. n为：0、1、2、3、4、5、6、……
2. 通过n可以组成常见公式

![](assets/3711104036.png ':size=50%')

### （拓展）结构伪类选择器的易错点

![](assets/4042142659.png ':size=50%')

**想改变第一个a元素 应当找ul里面第一个li元素 而不是ul li 里面第一个a元素**

### （了解）nth-of-type结构伪类选择器

![image-20220719171654796](assets/60198022.png ':size=50%')

**区别：**

- :nth-child → 直接在所有孩子中数个数
- :nth-of-type → 先通过该 类型 找到符合的一堆子元素，然后在这一堆子元素中数个数

## 伪元素

伪元素：一般页面中的非主体内容可以使用伪元素

**区别：**

- 元素：HTML 设置的标签
- 伪元素：由 CSS 模拟出的标签效果

<img src="assets/1178899608.png ':size=50%'" style="zoom: 67%;" />

**注意点：**

**必须设置content属性才能生效**

**伪元素默认是行内元素**

## 标准流

标准流中块级元素的排版规则是？

- 从上往下、垂直布局、独占一行

标准流中行内元素或行内块元素的排版规则是？

- 从左往右、水平布局、空间不够自动折行

## 浮动

### 浮动的作用

早期的作用：**图文环绕**

现在的作用：**网页布局**

### 浮动的代码

![****](assets/434731677.png ':size=50%')

### 浮动特点

1. 浮动元素会脱离标准流（简称：脱标），在标准流中不占位置

   - 相当于从地面飘到了空中

2. 浮动元素比标准流高半个级别，可以覆盖标准流中的元素

3. 浮动找浮动，下一个浮动元素会在上一个浮动元素后面左右浮动

4. 浮动元素会受到上面元素边界的影响

5. 浮动元素有特殊的显示效果

   - 一行可以显示多个
   - 可以设置宽高
   

注意点：

浮动的元素不能通过text-align:center或者margin:0 auto，让浮动元素本身水平居中

## 清除浮动

### 清除浮动含义

- 清除浮动带来的影响
- 影响：如果子元素浮动了，此时子元素不能撑开父元素

### 清除浮动的目的

需要父元素有高度，从而不影响其他网页元素的布局

### 清除浮动方法

#### ① 直接设置父元素高度

优点：简单粗暴，方便

缺点：有些布局中不能固定父元素高度。如：新闻列表、京东推荐模块

#### ② 额外标签法

1. 在父元素内容的最后添加一个块级元素
2. 给添加的块级元素设置 `clear:both`

缺点：会在页面中添加额外的标签，会让页面的HTML结构变得复杂

#### ③ 单伪元素清除法

**基本写法**

![](assets/2036908012.png ':size=50%')

**补充写法**

![](assets/733909360.png ':size=50%')

**优点：项目中使用，直接给标签加类即可清除浮动**

#### ④ 双伪元素清除法

**操作:**

![](assets/4107389662.png ':size=50%')

**优点：项目中使用，直接给标签加类即可清除浮动**

#### ⑤ 给父元素设置overflow : hidden

**优点：方便**

## （拓展补充）BFC的介绍

块格式化上下文（Block Formatting Context）：BFC

- 是Web页面的可视CSS渲染的一部分，是块盒子的布局过程发生的区域，也是浮动元素与其他元素交互的区域。

创建BFC方法：

- html标签是BFC盒子
- 浮动元素是BFC盒子
- 行内块元素是BFC盒子
- overflow属性取值不为visible。如：auto、hidden…
- ......

BFC盒子常见特点：

- BFC盒子会默认包裹住内部子元素（标准流、浮动）→ 应用：清除浮动
- BFC盒子本身与子元素之间不存在margin的塌陷现象 → 应用：解决margin的塌陷
- **......**

## 定位

### 网页常见布局方式

标准流

1. 块级元素独占一行 → 垂直布局
2. 行内元素/行内块元素一行显示多个 → 水平布局

浮动

1. 可以让原本垂直布局的 **块级元素变成水平布局**

定位

1. 可以让元素自由的摆放在网页的任意位置
2. 一般用于 **盒子之间的层叠情况**

### 使用定位的步骤

#### 设置定位方式

属性名：position

![](assets/1240351708.png ':size=50%')

#### **设置偏移值**

偏移值设置分为两个方向，**水平和垂直方向各选一个使用即可**

选取的原则一般是就近原则 （离哪边近用哪个）

![image-20220719174811258](assets/3676305668.png ':size=50%')

### 静态定位

介绍：静态定位是默认值，就是之前认识的标准流。

注意点：

1. 静态定位就是之前标准流，不能通过方位属性进行移动
2. 之后说的定位不包括静态定位，一般特指后几种：相对、绝对、固定

### 相对定位

介绍：相对于自己之前的位置进行移动

特点：

1. 需要配合方位属性实现移动
2. 相对于自己原来位置进行移动
3. 在页面中占位置 → 没有脱标

应用场景：

1. 配合绝对定位组CP（子绝父相）
2. 用于小范围的移动

### 绝对定位

介绍：拼爹型定位，相对于非静态定位的父元素进行定位移动

特点：

1. 需要配合方位属性实现移动
2. 默认相对于浏览器可视区域进行移动
3. 在页面中不占位置 → 已经脱标

应用场景：

配合绝对定位组CP（子绝父相）

### 绝对定位到底相对于谁进行偏移

1. 祖先元素中没有定位 → 默认相对于浏览器进行移动
2. 祖先元素中有定位 → 相对于 **最近的 有定位** 的祖先元素进行移动

### 子绝父相水平垂直居中

1. 子绝父相
2. 让子盒子往右走大盒子一半

   - left：50%
3. 让子盒子往下走大盒子一半
   - top：50%
4. 让子盒子往左+往上走自己的一半
   - transform：translate(-50%，-50%)；

### 固定定位

介绍：死心眼型定位，相对于浏览器进行定位移动

特点：

1. 需要配合方位属性实现移动

2. 相对于浏览器可视区域进行移动

3. 在页面中不占位置 → 已经脱标

应用场景：让盒子固定在屏幕中的某个位置

### 定位小总结

![image-20220719192511409](assets/709686703.png ':size=50%')

   ### 元素层级问题

不同布局方式元素的层级关系：

- 标准流 < 浮动 < 定位

不同定位之间的层级关系：

- 相对、绝对、固定默认层级相同
- 此时HTML中写在下面的元素层级更高，会覆盖上面的元素(谁写在HTML后面 谁层级更高)

### 更改定位元素的层级

**`属性名：z-index`**

**属性值：数字  数字越大 层级越高**

## 装饰

### 垂直对齐方式

`属性名：vertical-align`

![](assets/1243506940.png ':size=50%')

### （拓展）项目中 vertical-align 可以解决的问题

1. 文本框和表单按钮无法对齐问题
2. input和img无法对齐问题
3. div中的文本框，文本框无法贴顶问题
4. div不设高度由img标签撑开，此时img标签下面会存在额外间隙问题
5. 使用line-height让img标签垂直居中问题

注意点：

学习浮动之后，不推荐使用行内块元素让div一行中显示，因为可能会出现垂直对齐问题

推荐优先使用浮动完成效果

### 光标类型

场景：设置鼠标光标在元素上时显示的样式

属性名：`cursor`

![](assets/4175399556.png ':size=50%')

### 边框圆角

`属性名：border-radius`

常见取值：数字+px 、百分比

![](assets/3409791197.png ':size=50%')

**赋值规则：从左上角开始赋值，然后顺时针赋值，没有赋值的看对角！**

### 边框圆角的常见应用

画一个正圆：

1. 盒子必须是正方形
2. 设置边框圆角为盒子宽高的一半 → border-radius:50%

![](assets/4038718463.png ':size=50%')

胶囊按钮：

1. 盒子要求是长方形
2. 设置 → border-radius：盒子高度的一半

![](assets/423236215.png ':size=50%')

### 溢出部分显示效果

`属性名：overflow`

![](assets/2449122529.png ':size=50%')

### 元素本身隐藏

1. `visibility：hidden `隐藏元素本身，并且在网页中 **占位置**
2. `display：none `隐藏元素本身，并且在网页中 **不占位置**

注意点：

- 开发中经常会通过 display属性完成元素的显示隐藏切换
- display：none；（隐藏）、 display：block；（显示）

### （拓展）元素整体透明度

`属性名：opacity`

属性值：0~1之间的数字

- 1：表示完全不透明
- 0：表示完全透明

注意点：

opacity会让元素整体透明，包括里面的内容，如：文字、子元素等……

### （拓展）边框合并

场景：让相邻表格边框进行合并，得到细线边框效果

代码：`border-collapse：collapse；`

![](assets/2295434158.png ':size=50%')

![](assets/1446087502.png ':size=50%')

### （拓展）用CSS画三角形技巧（面试题）

1. 设置一个盒子
2. 设置四周不同颜色的边框
3. 将盒子宽高设置为0，仅保留边框
4. 得到四个三角形，选择其中一个后，其他三角形（边框）设置颜色为透明

![](assets/2632337384.png ':size=50%')

![](assets/294538762.png ':size=50%')

## 选择器拓展

### 链接伪类选择器

场景：常用于选中超链接的不同状态

![](assets/1777678800.png ':size=50%')

**如果同时实现以上四种伪类状态效果，需要按照LVHA书写**

### 焦点伪类选择器

场景：用于选中元素获取焦点时状态，常用于表单控件

![](assets/3020534464.png ':size=50%')

**表单控件获取焦点时默认会显示外部轮廓线**

### 属性选择器

场景：通过元素上的HTML属性来选择元素，常用于选择 input 标签

![](assets/3705259507.png ':size=50%')

![](assets/2315853533.png ':size=50%')

选中页面中所有的文本框，使用属性选择器如何实现呢？

**`input[type="text"] { }`**

## 精灵图

精灵图的使用步骤:

1. 创建一个盒子
2. 设置盒子大小为小图片大小
3. 设置精灵图为盒子的背景图片
4. 将小图片左上角坐标 **取负值**，设置给盒子的`background-position：x y`

## 背景图片大小

**语法：background-size：宽度 高度；**

![](assets/801605212.png ':size=50%')

## 文字阴影

**属性名：text-shadow**

![](assets/252703459.png ':size=50%')

**阴影可以叠加设置，每组阴影取值之间以逗号隔开**

## 盒子阴影

**属性名：box-shadow**

![](assets/154809408.png ':size=50%')

## 过渡

**属性名：transition**

![](assets/3502972801.png ':size=50%')

注意点：

1. 过渡需要：默认状态 和 hover状态样式不同，才能有过渡效果
2. transition属性给需要过渡的元素本身加
3. transition属性设置在不同状态中，效果不同的

- 给默认状态设置，鼠标移入移出都有过渡效果
- 给hover状态设置，鼠标移入有过渡效果，移出没有过渡效果