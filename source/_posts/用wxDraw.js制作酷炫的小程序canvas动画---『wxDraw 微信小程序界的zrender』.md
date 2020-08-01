![wxDraw](http://upload-images.jianshu.io/upload_images/1698086-8d7ff1cb9eb05a0a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


# wxDraw
> 轻量的小程序canvas动画库

## [github](https://github.com/bobiscool/wxDraw)
## [文档](http://project.ueflat.xyz/#/)
## 是什么
canvas 是HTML5的一个重要元素，它能够高效的绘制图形，但是过于底层，且粗糙的Api，导致开发者很难使用它来做较为复杂的图形， 而且它的即时绘制无记忆特性，使得它内部的图形并不支持动画更不支持一切交互事件。
这样的问题出现在所有支持canvas的客户端上同样出现在 **微信小程序**中的canvas中， 由于小程序由**jsCore**支持，并没有**window对象**，并且canvas的Api与标准的canvas的Api**有所出入**，所以市面上绝大部分canvas库**与它无缘**。
而**wxDraw**也就应运而生，专门用于处理小程序上**canvas**的**图形创建**、**图形动画**以及**交互**问题的。

## 特性
- **简单** 不需要你会canvas,会用jQuery就会使用wxDraw。
- **灵活** 所有图形，随时随地都可以进行属性修改、图形添加以及图形销毁。
- **事件支持** 小程序支持的事件只要是合理的都支持。
- **缓动动画支持** wxDraw支持链式调用动画『就像jQuery的animate一样』，并且支持几乎所有的缓动函数图形创建

## 支持图形
这些图形都可以在演示文件里看到 [点这里](https://github.com/bobiscool/wxDraw/tree/master/example)

### rect
```js
var rect = new Shape('rect', {x: 60, y: 60, w: 40, h: 40, fillStyle: "#2FB8AC", rotate: Math.PI/2 },'mix', true);
```
![rect](http://upload-images.jianshu.io/upload_images/1698086-774186a8e6da82f4?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)rect

### circle
```js
let circle = new Shape('circle', { x: 100, y: 100, r: 40, sA: Math.PI/4, fillStyle: "#C0D860", strokeStyle: "#CC333F", rotate: 20, lineWidth: 0, needGra: 'line', gra: [[0, '#00A0B0'], [0.2, '#6A4A3C'], [0.4, '#CC333F'], [0.6, '#EB6841'], [1, '#EDC951']]}, 'fill', true)
```
![](http://upload-images.jianshu.io/upload_images/1698086-8a3fdfaf35ad9b05?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### polygon

```js
let polygon = new Shape('polygon', { x: 200, y: 200, r: 40, sides: 9, //9边形 fillStyle: "#FC354C", rotate: Math.PI / 4 }, 'mix', true)
  ```
![](http://upload-images.jianshu.io/upload_images/1698086-2b0dacf03c1dd50e?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### ellipse
```js
let ellipse = new Shape('ellipse', { x: 200, y: 200, a: 40, b: 100, fillStyle: "#00A0B0", rotate: Math.PI / 7 }, 'mix', true)
```
![](http://upload-images.jianshu.io/upload_images/1698086-91141b090d2cc888?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### cshape 「自定义图形」
```js
let cshape = new Shape('cshape', { rotate: Math.PI / 2, points: [[70, 85], [40, 20], [24, 46], [2, 4], [14, 6], [4, 46]], lineWidth: 5, fillStyle: "#00A0B0", rotate: Math.PI / 7, needGra: 'circle', smooth:false, gra: [[0, '#00A0B0'], [0.2, '#6A4A3C'], [0.4, '#CC333F'], [0.6, '#EB6841'], [1, '#EDC951']] }, 'fill', true)
```
![](http://upload-images.jianshu.io/upload_images/1698086-23afc1fcccfc0315?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### line
```js
let line = new Shape('line', { points:[[240,373],[11,32],[28,423],[12,105],[203,41],[128,0.06]], strokeStyle: "#2FB8AC",lineWidth:1, rotate: 0, needShadow: true,smooth:false }, 'fill', true)
```

![](http://upload-images.jianshu.io/upload_images/1698086-de83c843d407f957?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### text
```js
let text = new Shape('text', { x: 200, y: 200, text: "我是测试文字", fillStyle: "#E6781E", rotate: Math.PI / 3} 'fill', true)
```

![](http://upload-images.jianshu.io/upload_images/1698086-c770b49104458cb3?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## wxDraw创作的动画演示
> 这些动画都可以在演示文件里看到 [点这里](https://github.com/bobiscool/wxDraw/tree/master/example)

### Google

![](http://upload-images.jianshu.io/upload_images/1698086-fd3939ba38769d6c?imageMogr2/auto-orient/strip)

### 贪吃蛇

![](http://upload-images.jianshu.io/upload_images/1698086-f82cf35e9301cd39?imageMogr2/auto-orient/strip)

### logo演绎

![](http://upload-images.jianshu.io/upload_images/1698086-c68a528c3c5cf075?imageMogr2/auto-orient/strip)

### rect舞蹈

![](http://upload-images.jianshu.io/upload_images/1698086-14d2f108db1a76ad?imageMogr2/auto-orient/strip)

### 吃豆人

![](http://upload-images.jianshu.io/upload_images/1698086-662fa2f0130e59ce?imageMogr2/auto-orient/strip)

## wxDraw事件
> 这些事件都可以在演示文件里看到 [点这里](https://github.com/bobiscool/wxDraw/tree/master/example)

支持
- tap
- touchStart
- touchEnd
- touchMove
- longPress
- drag「自定义的事件」

## 事件演示
旁边UI小妹妹亲自示范 😜

![](http://upload-images.jianshu.io/upload_images/1698086-01f9652385ed46e4?imageMogr2/auto-orient/strip)

### 第一视角

![](http://upload-images.jianshu.io/upload_images/1698086-40af26935badf570?imageMogr2/auto-orient/strip)

**是不是特别简单，特别方便！！！来，老铁们! star走一波！！！**

详细文档还请关注
[github](https://github.com/bobiscool/wxDraw)
[文档](http://project.ueflat.xyz/#/)