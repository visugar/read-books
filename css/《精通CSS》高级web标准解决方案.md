# 《精通CSS》高级web标准解决方案  

> 读后小笔记

tag：适合已经了解了css的相关内容之后，想要进一步增强的同学

### 第一章 
> **基础知识**

1. 尽量用clas （除了唯一存在的部分使用id）
2. 减少重复的词
3. ul外可以不用div包围

### 第四章
> **关于背景图像**
1.**backgroung-position** : (x,y) pixel/percent

当父background-position的设为像素值(20px,20px)时，
则背景图片是从父元素的（20px,20px）的位置开始显示，当设为百分比(20%,20%)的时候则是背景图的(20%,20%)这个点在父元素的(20%,20%)这个位置。

![image](http://note.youdao.com/yws/public/resource/b472221a7f8e76e37c0df837d17c7653/xmlnote/E96FF7906306470E922092762D5994B7/2044)



### 第五章
> **关于a链接**

1. 可以为a链接设置下划线的图片效果（多应用于a标签的伪类）
```
a:link,a:visited{
    color:#666;
    text-decoration:none;
    background:url(...) repeat-x left bottom;
}
```
2. 可以为链接目标设置样式：
```
.comment:target{
    background-color:yellow;
}
或
.comment:target{
    background-image:url(img/fade.gif);
}
```
3. 突出不同类型的链接（设置在链接的右上角）
```
.external{
    background:url(...) no-repeat right top;
    padding-right:10px;
}
```
> 可以使用`a[href^="http:"]{}`来作为样式选择器

> 凸显可以下载的文件`a[href$=".pdf"]`

### 第六章
> **关于列表的样式**

1. 设置前置项目符号(垂直居中)
```
li:{
    background:url(...) no-repeat 0 50%;
}
```

2. tab栏的下拉列表
```
<ul>
    <li><a>Tab1</a>
        <ul>
            <li>下拉列表一</li>
            <li>下拉列表二</li>
            <li>下拉列表三</li>
            ....
        </ul>
    </li>
    <li><a>Tab2</a>
        <ul>
            <li>下拉列表一</li>
            <li>下拉列表二</li>
            <li>下拉列表三</li>
            ....
        </ul>
    </li>
    <li><a>Tab3</a>
        <ul>
            <li>下拉列表一</li>
            <li>下拉列表二</li>
            <li>下拉列表三</li>
            ....
        </ul>
    </li>
    。。。
</ul>
```

### 第七章
> 关于表单和数据表格

1. caption(表格名字)/summary(类似于img的alt)/thead(表头)/tbody(表格主要内容)/tfoot(表尾)
2. col/colgroup (不用)
3. 常用的属性：
> + `border-collapse`:表格边框是否合并
> + `border-spacing`:表格单元之间的距离

4. 设置一个包围框，并将包围标题放在上边框的中间：
```
<fieldest>
    <legend>包围标题</legend>
    。。。内容。。。
</fieldest>
```
5. 将表单名字放在label中表示相关联：
```
<label for='url'>Web Address：</label>
<input type='text' name='url' id='url'>
```
或者
```
<label for='url'>Web Address：
    <input type='text' name='url' id='url'>
</label>

```
> 注：label的for属性要与input的id一致

6. 表单的输入反馈：
```
<label for='url'>Web Address：
<em class='feedback'>Incorrect email address.Please try again</em>
</label>
<input type='text' name='url' id='url'>
```
> 注：em中放入的是反馈，要对其进行css的设置。

### 第八章 布局
> **关于常用的几种布局**

1. **两列布局结构**
```
<body>
    <div class="wrap">
        <div class="header"></div>
        <div class="content">
            <div class="aside"></div>
            <div class="artical"></div>
        </div>
        <div class="footer"></div>
    </div>
```
> 注：布局方式有很多，可以自行尝试

2. **三列布局结构**（这里提到的是另一种）
```
<body>
    <div class="wrap">
        <div class="header">头部</div>
        <div class="content">
            <div class="aside">左</div>
            <div class="artical">
                <div class="main">主要内容</div>
                <div class="primary">右</div>
            </div>
        </div>
        <div class="footer">尾</div>
    </div>
```
如下：

![image](http://note.youdao.com/yws/public/resource/b472221a7f8e76e37c0df837d17c7653/xmlnote/03901DD92F864ED58A200848DD9B3D09/2003)

3. **类似报纸的多栏布局**

在父元素上`colum-count`属性（分成多少栏）


### CSS的bug修复
> **关于css的一些bug**

1. 外边距叠加问题：借助各浏览器调试工具中的layout视图来查看与调整
2. 在应用了float的元素上记得给父元素清除浮动

