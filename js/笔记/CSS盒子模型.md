```javascript
CSS三大特性:
	层叠性：指的是浏览器解决冲突的能力，如果同一个属性通过两个相同的选择器设置同一个元素上，那么这个时候就会将另外一个样式层叠掉
    如果 样式冲突，执行的是就近原则
    继承性：
    	子标签会继承父标签的样式
    优先级
    	样式冲突也要看选择器，这个时候需要看选择器的权重的问题
        行内样式表 > ID选择器 > 类选择器  > 标签选择器
```

```javascript
CSS的三大模块
	盒子模型、浮动、定位
    网页布局的实质：盒子模型的拜访过程
```

```javascript
border: 边框宽度 样式 边框颜色
 border-bottom: 1px solid red;
//当设置表格边框的时候，会设置border中的边框的宽度，但是在表格中相邻的边框将会有叠加的效果，想要解决这种问题，border中将会有一个属性
 border-collapse: collapse;  //意思是合并相邻的表格边框
```

```javascript
border属性之圆形边框
	border-radius: 100px;  //设置边框的弧度
//当边框的弧度设置为宽和高的一半的时候，就正好是一个圆形
//如果遇到那种宽度是基数的情况下，就用50%也可以，弧度也可以是一个圆形
 border-radius: 10px 40px;
//当写的是两个值的时候，就是对角线一致
//例如上面的情况：左上角和右下角是10px  右上角和左下角是40px
//如果是三个值，顺时针方向，左上是第一个值、右上和左下是第二个值 右下是第三个值
//4个值就是按照顺时针的方向
```

```javascript
盒子模型指定居中的问题
	指定margin左右为auto 
    但是前提是
     1.盒子必须是块级元素
     2.必须指定盒子的宽度
```

```javascript
盒子模型中容易混淆的问题
1.盒子水平居中和文字水平居中是不一样的
  文字水平居中用的是 text-align = center
  盒子水平居中是margin的水平方向为auto\
2.插入图片和背景图片的区别
  插入图片改变宽度是使用width和height，插入图片更改位置可以使用margin(插入的图片也类似于一个盒子)
  背景图片不会占位置
  背景图片更改大小使用 background-size
  调整位置使用background-position
3.一般情况下，背景图片适合做一些小图标,
    产品展示一般就会使用插入图片了
  
```

```javascript
行内元素是只有左右外边距的，没有上下内外边距的
尽量不给行内元素指定上下的内外边距
```

```javascript
外边距合并的问题
  1.兄弟关系的嵌套
	//注意： 只会出现在垂直的块级盒子的合并，以最大的外边距为准
	如果两个相邻的盒子都设置的相邻边的外边距，那么两个盒子的外边距不会叠加，只会取较大的外边距
    //解决方案：避免出现这种情况，这种情况是可以避开的
  2.父子层级关系的嵌套
     如果是嵌套关系的盒子，想要解决外边距合并的问题，解决方案
     	(1)给外面的盒子加上边框 border: 1px solid red;
        (2)给外面的盒子加上内边距   padding: 1px;
        (3) overflow: hidden;(暂时先记住)
```

