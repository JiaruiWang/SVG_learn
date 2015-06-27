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

##颜色、渐变和画刷
###RGB和HSL
```
<rect fill="rgb(255, 0, 0)" opacity="0.5" />
<rect stroke="hsla(0, 50%, 60%, 0.5)" />
```

###线性渐变和径向渐变
####线性渐变
```
<svg xmlns="http://www.w3.org/2000/svg">
 <defs>
   <linearGradient id="grad1" x1="0" y1="0" x2="1" y2="1">
    <stop offset="0" stop-color="#1497FC" />
    <stop offset="0.5" stop-color="#AF69BE" />
    <stop offset="1" stop-color="FF8C00" />
   </linearGradient>
 </defs>
 <rect x="100" y="100" fill="url(#grad1)" width="200" height="150" />
</svg>
```

####径向渐变
```
<svg width="640" height="480" xmlns="http://www.w3.org/2000/svg">
 <defs>
  <radialGradient fy="0.34375" fx="0.414063" r="0.53" cy="0.34375" cx="0.414063" id="svg_4">
   <stop stop-opacity="0.6" stop-color="#a0b3d6" offset="0"/>
   <stop stop-opacity="0.8" stop-color="#34538b" offset="1"/>
  </radialGradient>
 </defs>
 <g>
  <title>Layer 1</title>
  <rect id="svg_5" height="480" width="642" y="0" x="0" fill-opacity="1" stroke-width="0" stroke="#000000" fill="url(#svg_4)"/>
 </g>
</svg>
```

###笔刷
```
<svg xmlns="http://www.w3.org/2000/svg">
    <defs>
        <pattern id="p1" x="0" y="0" width="50" height="50" patternUnits="userSpaceOnUse">
            <circle cx="10" cy="10" r="5" fill="red"></circle>
            <polygon points="30 10 60 50 0 50" fill="green"></polygon>
        </pattern>
    </defs>
    <rect x="100" y="100" width="800" height="300" fill="url(#p1)" stroke="blue"></rect>
</svg>
```

##Path
###Path字符串
```
<path d="M0,0L10,20C30-10,40,20,100,100" stroke="red">
```
命令+参数
###命令汇总
 - M	moveto  移动到	(x y)+
 - Z	closepath  关闭路径	(none)
 - L	lineto  画线到	(x y)+
 - H	horizontal lineto  水平线到	x+
 - V	vertical lineto  垂直线到	y+
 - C	curveto  三次贝塞尔曲线到	(x1 y1 x2 y2 x y)+
 - S	smooth curveto  光滑三次贝塞尔曲线到	(x2 y2 x y)+
 - Q	quadratic Bézier curveto  二次贝塞尔曲线到	(x1 y1 x y)+
 - T	smooth quadratic Bézier curveto  光滑二次贝塞尔曲线到	(x y)+
 - A	elliptical arc  椭圆弧	(rx ry x-axis-rotation large-arc-flag sweep-flag x y)+
 - R	Catmull-Rom curveto*  Catmull-Rom曲线	x1 y1 (x y)+

###命令规律
 - 以上所有命令均允许小写字母。大写表示绝对定位，小写表示相对定位。
 - 最后的参数表示最终要到达的位置
 - 上一个命令的结束位置就是下一个命令的开始位置
 - 命令可以重复参数表示重复执行同一条命令


 ##SVG文本
 ###`<text>
  - x和y属性 定位标准
  - dx和dy 字形偏移
  - style 设置样式
  - 没办法换行

###`<tspan>`
 - dy往下传递
 - `<text>` 上再设置就无效了

###垂直居中
 - text-anchor
 - dominant-baseline
 - 模拟




