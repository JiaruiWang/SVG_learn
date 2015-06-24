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


##SVG坐标系


##坐标变换
