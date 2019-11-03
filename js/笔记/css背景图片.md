```javascript
行间距：
//设置行高（行间距）
	line-height: 25px;  行高
      p {
            line-height: 25px;
        }
//设置文字水平对齐
	 h3 {
            text-align: center;
        }
//设置段落首行缩进
 单位: em就是一个字的宽度
  p {
            line-height: 25px;
            text-indent: 2em;   // 设置首行空2个汉字
        }
//设置字和字之间的距离
  div {
            letter-spacing: 15px;
        }
//设置单词之间的间距(针对于英文、中文无效)
 p {
            word-spacing: 20px;
        }
```

```javascript
CSS3新特性： 半透明
//1.字体颜色的半透明
 div {
            color: rgba(255, 0, 0, 0.2);
        }
//第四个参数是测试颜色的透明程度的
//2.文字阴影
 text-shadow: 1px 2px 3px rgba(0, 0, 0, 0.4);
           水平距离   垂直距离  模糊距离  阴影颜色
           后面的两个参数可以省略，会有默认值
```

```javascript
CSS样式表可以分为三大类
	在H5中type = "text/css"可以省略不写
	内部样式表：将CSS代码写在HTML页面内部
    行内样式表（内联样式表）：直接通过标签中写style代码
    	行内样式表适合样式比较少的情况
    外部样式表：写在外部文件中
    
```

```javascript
标签的显示模式
	块级元素：每个块元素都会独占一行或者数行，可以对其设置宽度、高度等属性
    	块级元素的四个特点：
			1.总是从新行开始
            2.高度、行高、外边距、以及内边距都可以控制
            3.宽度默认容器是100%
            4.可以容纳内联元素和其他块级元素
    行内元素（inline-level）
		<a> <span> <strong>
       1.和相邻行内元素在一行上
       2.宽、高无效
       3.默认宽度就是它本身的宽度
       4.行内元素只容纳文本和其他行内元素
     连接里面不能再放连接了
     只有文字才可以组成段落 因此<p>里面不能再放块级元素
   行内快元素：(inline-block)
     具有行内元素的特点也有块级元素的特点
     1.和相邻行内元素在一行上，但是之间会有空白缝隙
     2.默认宽度是它本身的宽度
     3.高度、行高、外边距以及内边距是可以控制的
     <img/> <input>  <td>
```

```javascript
显示模式的转换
	display:block/inline/inline-block
```

```javascript
属性选择器
	1.属性选择器可选择含有foot开头的class
    	div[class^=font]{}
    2.属性选择器可选择含有footer结束的class
        div[class$=footer]{}
    3.属性选择器可选择含有任意的字符串的class
        div[class*=foot]{}
```

```javascript
伪元素选择器
	//选择p中的第一个字
   p::first-letter{}
    //选择p中的第一行
   p::first-line{}
   //当鼠标选中的时候改变样式
    p::selection {}
//在div盒子的内部的前面和后面插入内容
   div::before {
       content: "我们"
   }
 //在div盒子的前面插入内容'我们
   div::after {
       content: "你们"
   }
 //在div盒子的后面插入内容'你们
选择器和{}之间必须要有空格
属性名和:之间不能有空格
多个属性应该竖着写
```

```javascript
背景
	颜色： background-color: pink;
    背景图片：  background-image: url(../img/timg.jpg); 
    背景图片是否平铺： background-repeat: repeat-y;
利用方位名词来更改背景图片的位置
方位名词是没有顺序的
 background-position: right top;
如果方位名词只写一个，那么另外一个默认是center
方位名词谁在前，谁在后都是可以的
背景图片的位置：right top指的是图片在盒子的右侧和上侧的位置上
   背景图片是否是滚动的
    background-attachment: fixed;    //设置背景图片不会随着内容而滚动
     background-attachment: scroll;   //设置背景图片是随着内容而滚动的,不设置也是默认这种情况
```

```javascript
背景图片半透明
	 background: rgba(0, 0, 0, 0.5); // 0.5是透明度
更改背景图片的宽度和高度
	//如果是想要更改图片的宽高就直接设置width和height属性就可以了
   // 但是如果是想要改变背景图片的宽高就需要使用 background-size: 100px; 一般只改变宽高其中的一个
  //另外一个就会自适应，如果非要改，很有可能会改变图片缩放失贞
	 background-size: 100px; // 也可以用百分比的方式
 background-size: cover;
//cover:自动调整缩放比例，保证图片始终填满整个背景区域，如果有溢出的部分就会被隐藏，保证背景区域填满
 background-size: contain;
//设置为contain会自动调整缩放比例，保证图片始终完整显示在背景区域，保证图片是完整的
//如果宽度或者是宽度有一个和盒子一样大了，就不再缩放，这样就保证了图片的完整，但是盒子就会有部分的裸漏
//一般用cover比较多
```

```javascript
多背景图效果
	一个元素可以设置多个背景图片
    每组属性之间用逗号分隔
    如果设置的多个背景图之间存在交集，前面的背景图会将后面的背景图盖上
    为了避免背景色将背景图片盖上，背景色通常定义在最后一组
      div {
            width: 1600px;
            height: 500px;
            /* background-color: skyblue; */
            background: url(../img/test.jpg) no-repeat left top,
                        url(../img/test1.jpg) no-repeat right bottom pink;
        }
```

```javascript
凹凸文字效果
	text-shadow: 水平位置  垂直位置 模糊距离  阴影颜色；
     text-shadow: 1px 1px 1px #000
 凸起效果和凹下效果的案例
 	 div:first-child {
            text-shadow: 1px 1px 1px #000
                        ,-1px -1px 1px #fff
                        ;
        }
        div:last-child {
            text-shadow: -1px -1px 1px #000
                        ,1px 1px 1px #fff
                        ;
        }
```

```javascript
a连接会自动带一条下划线
	text-decoration: none;  //取消下划线、取消文本装饰
```