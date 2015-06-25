# SVG_learn
##SVG的打开方式
 - 浏览器直接打开
 - `<img>`标签引用
 - 在`HTML`中使用`svg`标签
 - 作为`CSS`背景

##基本图形和属性
- rect, circle, ellipse line polyline polygon
- fill stroke stroke-width transform

##基本API
 - document.createElementNS(ns, tagName)
 - element.appendChild(childElement)
 - element.setAttribute(name, value)
 - element.getAttribute(name)

##SVG的世界，视野，视窗
```
<svg xmlns="..."
  width="800" height="600"
  viewBox="0 0 400 300"
  preserveAspectRatio="xMidYMid meet">
</svg>
```

 - width, height 控制视窗
 - SVG代码 定义世界
 - viewBox, preserveAspectRatio 控制视野

##图形分组
 - `<g>`创建分组
 - 属性继承
 - transform属性定义坐标变换
 - 可以嵌套使用

##SVG坐标系
 - 笛卡尔直角坐标系（Y朝下，顺时针）
 - 原点
 - 互相垂直的两条数轴
 - 角度定义

##四个坐标系
 - 用户坐标系：世界的坐标系（原始）
 - 自身坐标系：每个图形元素或分组独立与生俱来
 - 前驱坐标系：父容器的坐标系
 - 参考坐标系：使用其他坐标系来考究自身的情况时使用

##坐标变换
###线性变换
X' = aX + cY + e
Y' = bx + dY + f
```
a c e
b d f
0 0 1
```
####平移
改变`e`，`f`
####旋转
```
cos() -sin() 0
sin() cos()  0
0 0 1
```
####缩放
改变`a`，`d`
###线性变换列表
后面的变换乘在前面

###`transform`属性
 - `rotate`
 - `translate`
 - `scale`
 - `matrix`


