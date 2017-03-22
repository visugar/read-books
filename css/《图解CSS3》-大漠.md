# 图解CSS3 - 大漠

读后小笔记

tag：此笔记适合查阅，记录的大部分属于平时想不起来用的一些很便利的属性。**很多属性都需要做兼容**

### 第一章

1. 渐进增强与优雅降级
> 在设计的时候，先考虑低端设备用户是否能看到所有的内容，然后再此基础之上为高端用户进行设计，不仅为高端用户提供一个完美的应用，也要为不同性能级别设备的用户设计不同级别的不那么完美的应用，这成为“优雅降级”。

### 第二章 选择器

 1. 通配选择器
 
最常用：*{margin: 0;padding: 0;}

2. 元素选择器
3. ID选择器
4. 类选择器
5. 群组选择器（多个选择器放在一起用逗号隔开）
6. 层次选择器

```
E F 后代选择器： 选中所要被包含在E中的F元素
E>F 子选择器： 选中E的直接子元素
E+F 相邻兄弟选择器： 选中紧邻E的F元素
E~F 通用选择器： 选中E后面的所有兄弟F元素 （需要在同一个父元素下）
```

7. 动态伪类选择器
```
:link
:visited
:hover
:active
```

8. 目标伪类选择器
```
:target 
```

9. 语言伪类选择器
10. UI元素状态类选择器
```
E:checked 选中状态
E:enabled 启用状态
E:disabled 不可用状态
```

11. 结构伪类选择器
```
E:first-child     →    第一个子元素E
E:last-child      →    最后一个子元素E
E:root            →    E所在文档的根元素，即为html
E F:nth-child(n)  →    选中父元素下的第n个子元素F  n还可以是2n+1等这类表达式  ood(奇数) even(偶数)
E F:nth-last-child(n)→ 选中倒数第n个子元素F
E:nth-of-type(n)   →   选中父元素中具有指定类型的第n个E元素
E:nth-last-of-type(n)→ 选中父元素中具有指定类型的倒数第n个E元素
E:first-of-type    →   选中父元素中具有指定类型的第一个E元素
E:last-of-type     →   选中父元素中具有指定类型的最后一个E元素
E:only-child       →   选中只有一个子元素且为E的E元素
E:only-of-type     →   选中只包含一个同类型的子元素，且该子元素为E
E:empty            →   选中没有子元素的元素
```
> 注、选中前3个元素的方法 : E:nth-child(-n+4)

12. 否定伪类元素
```
E:not(F)  所以除F外的E元素
例：input:not([type=submit]){...} 
```

13. 伪元素
```
：befor        用于清除浮动等
：after
::first-line   第一行文本
::first-letter 第一个字母
::befor        给链接添加icon等方面   即追加元素
::after
::section      被用户选中的内容
```

14. 属性选择器
```
E[attr]       选中具有attr属性的E元素
E[attr=val]   选中具有attr属性且属性值为val的E元素
E[attr|=val]  选中具有attr属性且属性值以val开头的元素 例：p[lang=en],  lang= 'en-us'
E[attr~=val]  选中具有attr属性，attr属性为多个空格分开，val为其中的一个单词  例：[class~=sport]  class='title sport'
E[attr*=val]  选中具有attr属性，且属性值的任意位置包含val
E[attr^=val]  选中具有attr属性，且属性值是以val开头
E[attr$=val]  选中具有attr属性，且属性值是以val开头
```

### 第三章 边框
1. **border-image** (边框背景图片)

> border-image :none | <image> [ <number> | <percentage> ]{1,4} [/ <border-width>{1,4}]? [ stretch | repeat | round ]{0,2}

2. **border-radius** (圆角)

> border-radius:none | <length> {1,4} [/<length>{1,4}]?

3. **box-shadow** (盒子阴影效果)

> box-shadow:none | [ <length> <length> <length>?<length>?  || <color> ] [, <length> <length> <length>? <length>? || <color> ]+

或

> box-shadow:none | [ inest||outset  x-offset y-offset blur-radius spread-radius color ],[ inest||outset x-offset y-offset blur-radius spread-radius color ]


### 第四章 背景
1. **background-color** (背景颜色)
> background-color: transparent || <color>

2. **background-image** (背景图片)
> background-image:none || <url>

3. **background-repeat** (背景图片展示方式)
> background-repea:repeat || repeat-x || repeat-y || no-repeat

4. **background-attachment** (背景图片是固定还是滚动)
> background-attachment:scorll || fixed

5. **background-position** (背景图片的位置)
> background-position: <percentage> || <length> || [ left | center | right] [,top | center | bottom ]

---
新属性：
6. **background-origin** :背景图片的起始位置 
> background-origin:padding-box || border-box || content-box

7. **background-clip** :定义背景图像的裁剪区域
> background-clip:border-box || padding-box || content-box

8. **background-size**:设置背景图片的尺寸
> background-size:auto || <length> || <percentage> || cover || contain

多背景属性：
CSS3中可以添加多个背景图


### 第五章 CSS3文本

1. **font** : font-style font-weight font-size/line-heiht font-family

2. 其他属性
```
（词与词之间的间距）word-spacing:   normal | length 
（字符之间的间距）  letter-spacing: normal | length
（垂直对齐方式）    vertical-align: baseline(默认值) | sub(上标对齐) | super(下标对齐) | top(顶端对齐) |
                                   bottom(行框底端对齐) | text-bottom(行内文本底端对齐) | 
                                   middle(居中对齐) | 数字 | 百分比
（修饰线）          text-decoration:none(默认值) | underline(下划线) | overline(上划线) |
                                   line-through(删除线) | blink(闪烁线)
（首行缩进）        text-indent：   length | percentage
（文本水平对齐方式）text-align:     left | center | right | justify(两端对其)
（文本大小写）      text-transform：none | uppercase(大写) | lowercase(小写) | capitalize(首字母大写)
（文本间空白符处理）white-space：    normal | nowrap(空白符合并，换行符忽略) |
                                   pre(空白符、换行符保留) | pre-wrap(空白符、换行符保留) | pre-line(空白符合并，换行符保留)
（文本流入方向）    direction：      ltr(默认值左到右) | rtl(右到左) | inherit(继承)
```

3. **text-shadow** ：文字阴影
> text-shadow: color x轴位移 y轴位移 模糊半径blur-radius

4. **text-overflow** :文字溢出
> text-overflow:clip(简单的裁剪) | ellipsis(显示...来代替)

注：一般配合white-space：nowrap和overflow:hidden 一起使用

5. **word-wrap :文本换行
> word-wrap:normal | break-word(将内容在边界内换行，不截断单词)

6. **word-break** :用于长单词
> word-break:normall | break-all(全拆分) | keep-all(不拆分)


### 第六章 颜色特性

1. **opacity** : alphavalue(0~1任意值) || inherit
2. **rgba(r,g,b,a)** (用的多)
3. hsl(色调,饱和度,亮度)
4. hsla(<length>,<percentage>,<percentage>,<opacity>)


### 第七章 CSS盒模型
1. 元素尺寸计算(w3c标准盒模型)
> element 高度 = 内容高度 + 内距 + 边框 + 外距

> element 宽度 = 内容宽度 + 内距 + 边框 + 外距

注：IE6~7则为怪异模式

2. **box-sizing**:content-box | border-box | inherit

3. **overflow-x**:visible | hidden | scorll | auto | no-display | no-content

4. **overflow-y**:visible | hidden | scorll | auto | no-display | no-content
> `no-display`:当内容溢出是不显示元素，此时类似于元素添加了display：none声明

> `no-content`:当内容溢出是不显示内容，此时类似于添加了visibility：hidden声明一样

5.**resize**（改变元素大小）
> resize: none | both | horizontal | vertical | inherit

> `both`:用户可以拖动元素，同时可以修改元素宽度和高度

> `horizontal`:可以拖动，可以修改宽度，但是不能修改高度

> `vertical` :可以拖动，可以修改高度，但是不能修改宽度


6. **outline**

> outline:[outline-color] || [outline-style] || [outline-width] || [outlime-offset](偏移像素值+/-) || inherit

outline和border的区别：
表面上是一样的，但实际上并不相同，border属于盒模型的一部分，而outline创建在外轮廓，是画在一个框“上面”，不会影响该框的大小，也不会破坏网页布局，outline不能设置单独边框，且始终闭合。outline创建的外轮廓线可能是非矩形的。

### 第八章 Flexbox布局

[参考阅读链接](https://segmentfault.com/a/1190000002910324)

1. **display** (父元素)
> display: flex （块级伸缩容器） | inline-flex （内联伸缩容器）

2. **flex-direction** (父元素)
> flex-direction: row | roe-reverse | column | column-reverse
> + row : 默认值（ltr时从左向右，rtl时从右向左）
> + row-reverse : 与row相反
> + colum : 从上到下
> + column-reverse : 从下到上


3. **flex-wrap** (父元素) 
> flex-wrap : nowrap | wrap | wrap-reverse
> + nowrap : 伸缩容易内单行显示，即不换行
> + wrap : 伸缩容器内多行显示，ltr排版时，伸缩项目从左向右排列；rtl排版上的伸缩项目从右向左排列
> + wrap-reverse : 伸缩容器内多行显示，与wrap相反

4. **flex-flow** (父元素)
> flex-flow : <'flex-direction'> || <'flex-wrap'>
> + 缩写方式

5. **justify-content** （父元素）
> justify-content : flex-start | flex-end | center | space-between | space-around
> + flex-start : 伸缩项目向一行的起始位置靠齐
> + flex-end : 伸缩项目向一行的结束位置靠齐
> + center : 伸缩项目向一行的中间位置靠齐
> + space-between : 伸缩项目会平均的分布在行里，第一个伸缩项目在一行的起始位置，最后一个伸缩项目在一行中的最终位置
> + space-around : 伸缩项目会平均的分布在行里，两端保留一般的空间

6. **align-items** (父元素)(侧轴方向的对齐方式)
> align-items : flex-start | flex-end | center | baseline | stretch
> + flex-start : 伸缩项目外边距紧靠侧轴起始边
> + flex-end : 伸缩项目外边距紧靠侧轴终点边
> + center : 伸缩项目在侧轴上居中放置，类似于垂直居中的效果
> + baseline : 伸缩项目根据伸缩项目的基线对齐
> + strtch : 默认值，伸缩项目拉伸填充整个伸缩容器

7. **align-self** (子元素)　（单个伸缩项目的对齐方式）
> 如果伸缩项目的任一个侧轴上的外边距为auto，则align-self没有效果，如果align-self的值为auto，则其计算值为伸缩项目的伸缩容器的align-items值，如果该伸缩项目没有伸缩容器，则计算值为stretch

8. **align-content** (父元素) (会改变flex-wrap的行为，它对齐的是伸缩行，当侧轴还有额外控件是，用来调节伸缩行的对齐方式)
> align-content : flex-start | flex-end | center | space-between | space-around | stretch
> + flex-start ：各行向伸缩容器的起点位置堆叠
> + flex-satrt : 各行向伸缩容器的结束位置堆叠
> + center : 各行向伸缩容器的中间位置堆叠
> + space-between : 各行在伸缩容器中平均分布
> + space-around : 各行在伸缩容器中平均分布，在两头各有一半的空间
> + stetch : 默认值，各行将会伸展以占用额外的空间

9. **flex**　(父元素)
> flex : none | {<'flex-grow'> <'flex-shrink'>? || <'flex-basis'>]  （初始值：0 1 main-size）
> + flex-grow : <number> （初始值为0） 伸展因子
> + flex-shrink : <number>  （初始值为1 负值生效） 收缩因子
> + flex-basis : <length> 设置收缩项目的初始宽/高 （默认值为auto）

10. **order** (子元素)
> order : <number>
> + 将伸缩项目分到有序号的组来控制伸缩项目的顺序。(有负值)


### 第九章 CSS3 多列布局

1. **多列布局**
> + columns
> + **column-width** :　定义每列宽度
> + **column-count** : 定义分列列数
> + **column-gap** : 定义列间距
> + **column-rule** : 定义列边框
> + **column-span** : 定义多列布局中子元素跨列效果
> + **column-fill** : 控制每列的列高效果

2. **columns** 多列布局属性语法
> columns: <column-width>(列宽) || <column-count>(列数)
> + （此处列宽类似于min-width）

3. **column-width** (可单独使用)
> column-width : auto | <length> （只能为正，不能为负）

4. **column-count**
> column-count : auto | <integer>(正数值)

5. **column-rule** 设置列之间的分割线
> column-rule : <column-rule-width> | <column-rule-style> | <column-rule-color>
> + 注：分割线大于列间距，则列分割线消失。

6. **column-span** 子元素能横跨多少列
> column-span : none(不能横跨) | all(横跨全部列)
> + 设为all的情况多用于文章标题

7. **column-fill** 设置列高度属性
> column-fill : auto | balance
> + auto : 默认值 随内容自动变化
> + balance : 根据内容最多的一列的高度进行统一


### 第十章 CSS3 渐变

1. **线性**：background-image : linear-gradient([ <point> || <angle> ,]? <stop>,<stop>[,<stop>]*)  
> ....这里内容有点不好描述，略过....
> + 可用于记事本纸张的效果

2. **放射性*** ：background-image : radial-gradient()
3. > ....这里内容也是有点不好描述，略过....
 

### 第十一章 CSS3 变形

1. **transform** 变形、

2. **2D transform**
> transform : none | <transform-function> [<transform-function>]*
> + transform-function  2D的方法：
> +     translate() (移动 translateX()/translateY())
> +     scale() (缩放 scaleX()/scaleY())
> +     rotate() (旋转元素)
> +     skew() (倾斜 skewX()/skewY())
> +     matrix() (定义矩阵变形，基于X轴和Y周坐标重新定位元素位置)

3. **3D transform**
> + transform-function 3D方法：
> +     translate3d() (移动 translateX()/translateY()/translateZ())
> +     scale3d() (缩放 scaleX()/scaleY()/scaleZ())
> +     rotate3d(<number>,<number>,<number>,<angle>) (旋转元素 rotateX(<angle>)/rotateY(<angle>)/rotateZ(<angle>))

4. **transform-origin** 中心点
> transform-origin : <length> | <percent> | [ left | center | right | top | bottom ]
> + 例：transform-origin : 50% 50%; (默认值)

5. **transform-style** 
> transform-style : flat | preserve-3d
> + flat : 2D
> + preserve-3d : 3D

6. **perspective** 透视效果
> perspective : none | <length> 值越小，效果越明显
> + 也可以运用在 transform：perspective(length)
> + 注：单独用在一个3d空间是对整个空间有效，设置在单个元素上则对单个元素有效

7. **perspective-origin** 眼睛看过去的地方
> perspective-origin : {1,3} 也可以是left/center/top/bottom/right等值
> + perspective-origin : 50% 50%;

> perspective 和 perspective-origin 都设置在父元素上

8. **backface-visibility** 
> backface-visibility : visible | hidden
> + **visible** : 默认值，反面可见
> + **hidden** : 反面可见


### 第十二章 CSS3过渡

1. **transition** 过渡
> transition : <transition-property> || <transition-duration> || <transition-timing-function> || <transition-delay> || *
> + **transition-property** : 动画名称(css属性/all)
> + **transition-duration** : 动画时间
> + **transition-timing-function** : ease(默认 慢快慢) | linear(匀速) | ease-in(先慢) | ease-out(后慢) | ease-in-out(慢快慢（弧度大）) | cubic-bezier(<number>,<number>,<number>,<number>) | step-start | step-end | steps(<integer>[start | end]) 
> + **transition-delay** : 延迟时间

> + 注： 过渡效果需要用:hover、:active、 :checked等触发！
> + 媒体查询触发
> + 还可以结合:target等属性完成导航栏点击或其他状态的动画


### 第十三章 CSS3动画

1. **animation**
> animation : <animation-name> || <animation-duriation> ||  <animation-timing-function> || <animation-delay> || <animation-iteration-count> || <animation-direction> || <animation-play-state> || <animation-fill-mode>
> + **animation-name** : 动画名称
> + **animation-duriation** : 动画播放时间
> + **animation-timing-function** : ease(默认 慢快慢) | linear(匀速) | ease-in(先慢) | ease-out(后慢) | ease-in-out(慢快慢（弧度大）) | cubic-bezier(<number>,<number>,<number>,<number>) | step-start | step-end | steps(<integer>[start | end])
> + **animation-delay** : <number> 动画延迟时间
> + **animation-iteration-count** :infinite(默认 无限) | <number> 循环播放次数 
> + **animation-direction** : normal(正方向) | reverse(反方向) | alternate(往返) | alternate-reverse(相反的往返) 动画播放方向
> + **animation-play-state** : running | paused 动画播放状态 
> + **animation-fill-mode** : none(不设置) | backwards(开始保持第一帧) | forwards(结束保持最后一帧) | both(两者都要) 设置动画最后一帧状态

> 例: animation : abc(名称) 2s(时间) ease(速度) 0s(延迟) 1(次数) normal(方向) running(状态) none(帧)

2. **animation需要配合@keyframes**
> 规则：
```
@keyframes abc(动画名称){
    from{
        ....css样式
    }
    to{
        ....css样式
    }
}
```
或者
```
@keyframes abc{
    0%{
        ....css样式
    }
    percentage{
        ...多个百分数...css样式
    }
    100%{
        ....css样式
    }
}
```

### 第十四章 媒体特性与Responsive设计

1. **Media Type** 设备类型
> + all : 所有设备
> + braille : 盲人用点字法触觉回馈设备
> + embossed : 盲文打印机
> + handheld : 便携设备
> + print : 打印或打印预览
> + projection : 各种投影设备
> + screen : 电脑显示器
> + speech : 语音或音频合成器
> + tv : 电视机类型设备
> + tty : 使用固定密度字母的媒介

2. **@media** 的使用
```
@media screen {
    ...css样式...
}
```
或者
```
@media screen and (min-width:600px) and (...){
    ...css样式...
}
```

### 第十五章 嵌入web字体

1. @font-face
```
@font-face{
    font-family:<font-name>
    src:url("...")
}
```