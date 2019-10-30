# sui

文档流
脱里文档流
html实质：3维的， 有z轴
重叠:z-index
默认：绝对定位、fix会显示在最上层, 文档流会显示在最下层
```
属性选择器
^=
$=
~= 包含
|=
*= 也是包含，范围更广，eg 选择所有属性带disable字符串的元素
```
子孙后代： 子就是子(a>b), 后代 （a b）

兄弟: 相邻兄弟，通用兄弟

- `a + b` : 只对a后面紧跟的那一个元素有效 
- `a~b`: 会匹配a后面所有的符合b条件的兄弟元素

交集选择器:

```
<!-- HTML -->
<div class="menu">
    <a class="menu-item">菜单1</a>
    <a class="menu-item active">菜单2</a>
    <a class="menu-item">菜单3</a>
    <a class="menu-item">菜单4</a>
</div>
```
```
// CSS
.menu-item{
    background: #ccc;
    color: #000;
}
.menu-item.active{
    background: #aaa;
    color: #fff;
}
```
并集选择器:

```css
// CSS
h1{
    margin: 0;
    padding: 0;
}
h2{
    margin: 0;
    padding: 0;
}
h3{
    margin: 0;
    padding: 0;
}
```
等价于
```
// CSS
h1,h2,h3{
    margin: 0;
    padding: 0;
}
```

伪类选择器, 语法： `elemnet:伪类名称` eg:

```css
a:{
    text-decoration: none;
}
a:hover{
    text-decoration: underline;
}
```

<table>
    <tr>
        <td>标记状态的伪类</td>
        <td>meaning</td>
    </tr>
    <tr>
        <td>:link</td>
        <td>获取未访问的超链接</td>
    </tr>
    <tr>
        <td>:visited</td>
        <td>获取访问过的超链接</td>
    </tr>
    <tr>
        <td>:hover</td>
        <td>选择鼠标悬停的元素</td>
    </tr>
    <tr>
        <td>:active</td>
        <td>选择点中的元素</td>
    </tr>
    <tr>
        <td>:focus</td>
        <td>选择获取焦点的元素</td>
    </tr>
</table>
<div></div>
<table>
    <tr>
        <td>筛选功能的伪类</td>
        <td>meaning</td>
    </tr>
    <tr>
        <td>:empty</td>
        <td>选取没有子元素的元素</td>
    </tr>
    <tr>
        <td>:checked</td>
        <td>选取勾选状态的input元素，只对radio和checkbox生效</td>
    </tr>
    <tr>
        <td>:disabled</td>
        <td>选取禁用的表单元素</td>
    </tr>
    <tr>
        <td>:first-child</td>
        <td>选取当前选择器下第一个元素</td>
    </tr>
    <tr>
        <td>:last-child</td>
        <td>选取当前选择器下最后一个元素</td>
    </tr>
    <tr>
        <td>:nth-child(an+b)</td>
        <td>选取指定位置的元素，n从0开始；用于快速给表格上色</td>
    </tr>
    <tr>
        <td>:nth-last-child(an+b)</td>
        <td>与nth-child功能一样，只不过倒着数</td>
    </tr>
    <tr>
        <td>:only-child</td>
        <td>选取唯一子元素</td>
    </tr>
    <tr>
        <td>:only-of-type</td>
        <td>选取唯一的某个类型的元素</td>
    </tr>
</table>

<table>
    <tr>
        <td>伪元素选择器</td>
        <td>meaning</td>
    </tr>
    <tr>
        <td>::first-line</td>
        <td>为某元素的第一行文字添加样式，对内联元素无效</td>
    </tr>
    <tr>
        <td>::first-letter</td>
        <td>为某元素文字的首字母或第一个字使用样式，对内联元素无效</td>
    </tr>
    <tr>
        <td>::before</td>
        <td>在某个元素之前插入一些内容</td>
    </tr>
    <tr>
        <td>::after</td>
        <td>在某个元素之后插入一些内容</td>
    </tr>
    <tr>
        <td>::selection</td>
        <td>为光标选中的元素添加样式</td>
    </tr>
</table>

tips:

1. 为元素选择器构造的元素是虚拟的，所有不能用js来操控
2. 如果同时使用了before和first-letter两个伪类，第一个是要从before里的内容开始算的，如果before里面的内容是一个非文本内容，那first-letter也会作用在这个非文本内容元素上，但是不一定生效
3. first-line和first-letter不适用于内联元素，在内联元素里2个都会失效
4. 在css3中，规定伪类用单个的`:`表示，伪元素用2个冒号`::`表示。但实际上除了`::selection`,其他4个伪元素选择器在css2中都存在且用的是`:`单引号，为了向下兼容，现在浏览器中的伪元素单引号，双引号都ok，在没有兼容的情况下，建议大家都按照css3标准来开发

### font-size vs line-height

![](../imgs/1.png)

![](../imgs/2.png)

### 良好的css书写规范
- 注释
- 属性

### 屏幕适配，字体统一
不同分辨率下html: font-size: xxrem

### 字体图标
http://fontawesome.dashgame.com/

