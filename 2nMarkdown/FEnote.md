# 移动端基础概念

改自一篇笔记摘要……

## 基础

- pixel
- Viewport
- Viewport Meta
- Viewport dome

## 移动web布局

- 响应式布局
- Flex 弹性布局

### Flexbox

自动填充整个容器

	display:-webkit-flex;
	flex:num;

注，还应该把原宽度变为0，flex-

	justify-content:center;
	align-items:center;
	//不定宽高 水平垂直居中


### Flex弹性盒模型

方向：flex-direction

取值：row/column

换行：

	-webkit-flex-wrap:
	flex-wrap:
	flex-flow:

justify-content：横向排版

align-self:子元素各自的排班

align-items

- 旧版 Flex-box
- 新版 Flex

## 响应式设计：

- 百分比布局
- 弹性图片
- 重新布局，显示与隐藏

多行文本溢出

	.intwoline {
		display:-webkit-box !inportant;
		overflow:hidden;

		text-overflow:ellipsis;
		word-break:break-all;

		-webkit-box-orient:vertical;
		-webkit-line-clamp:2;
	}

## 篇一

### 像素

在web前端开发领域，像素有以下两层含义：

1. 设备像素：设备屏幕的物理像素，对于任何设备来讲物理像素的数量是固定的；
2. CSS像素：这是一个抽象的像素概念，它是为web开发者创造的。

**当你给元素设置了`width: 200px` 时，这个元素的宽度跨越了200个CSS像素。** 但是它并不一定跨越200个设备像素，至于会跨越多少个设备像素，就取决于**手机屏幕的特性和用户的缩放**了

1. web前端领域，像素分为**设备像素**和**CSS像素**；
2. 在缩放比例为1:1的时候一个CSS像素的大小等于一个设备像素的大小；
3. 一个CSS像素的大小是可变的，比如用后缩放页面的时候，实际上就是在缩小或放大CSS像素，而设备像素无论大小还是数量都是不变的。

### 视口

**视口是 html 的父元素，所以我们称视口为初始包含块。**

html 元素的百分比是基于视口的。

#### 布局视口

布局视口：移动端CSS布局的依据视口，即CSS布局会根据布局视口来计算。

也就是说，在移动端，视口和浏览器窗口将不在关联，实际上，布局视口要比浏览器窗口大的多(在手机和平板中浏览器布局视口的宽度在768~1024像素之间)

查询：

	document.documentElement.clientWidth
	document.documentElement.clientHeight
	document.body.clientWidth  //慕课

#### 视觉视口：用户正在看到网站的区域

#### 理想视口：这是我们最需要关注的视口

	<meta name="viewport" content="width=device-width" />

上面这行代码告诉手机浏览器要把布局视口设为理想视口

总结：

1. 在PC端，布局视口就是浏览器窗口；
2. 在移动端，视口被分为两个：布局视口、视觉视口；
3. 移动端还有一个理想视口，它是布局视口的理想尺寸，即理想的布局视口。（注：理想视口的尺寸因设备和浏览器的不同而不同，但这对于我们来说无所谓）；
4. 可以将布局视口的宽度设为理想视口。

心得：

1. 初始布局视口有680~1024那么大；
2. 理想视口则较小，虽然未必等于视觉视口。例如 iphone5 是320*568；
3. CSS布局是基于布局视口的；
4. 通过meta将布局视口的宽度设为理想视口后，CSS布局的视口也变小了；
2. 在PC端，布局视口就是浏览器窗口，所以不用设置meta；
2. 在手机端，为了让两个（近似地）相等，所以设置meta。


### 设备像素比(Device Pixel Ratio 简称：DPR)

设备像素比的计算公式，公式成立的大前提：**缩放比例为1**

设备像素比(DPR) = 设备像素个数 / 理想视口CSS像素个数(device-width)

与理想视口一样，设备像素比对于不同的设备是不同的

### 缩放：缩小放大的是CSS像素。

CSS像素的大小是可变的，而缩放从技术实现的角度来讲，就是放大或缩小CSS像素的过程。

当你用双指缩放页面的时候，实际上是在放大或缩小CSS像素。

### 媒体查询

1. 检测媒体的类型，比如 screen, tv 等；
2. 检测布局视口的特性，比如视口的宽高分辨率等；
3. 特性相关查询，比如检测浏览器是否支持某某特性（这一点不讨论，因为它被目前浏览器支持的功能对于web开发来讲很无用）

e.g.

		@media all and (min-width: 321px) and (max-width: 400px){
			.box{
				background: red;
			}
		}

## 篇二

psd原稿的尺寸是按照设备像素设计的；而我们CSS中的样式是基于布局视口的尺寸计算的。

上一篇的公式：

>设备像素比（DPR） = 设备像素个数 / 理想视口像素个数（device-width）

设计稿总宽640px（iPhone5）,dpr=2，所以理想视口device-width=320px.

根据这个比例，在设计稿上测量出来的宽高都进行缩放。

计算机(手机)没办法显示不到一个像素的像素值，计算机(手机)会自动将其补全为一个像素进行显示。

当你在设计稿上测量出来一个奇数值，除以2就会有问题。

另外，篇一提到，不同设备的DPR是不一样的，有1有2有3，甚至2.5，按上面的做法切出来的页面无法在所有设备下完好显示。

### 思路：

如果我们能将布局视口的尺寸设置为和设备像素尺寸相等的话，这样我们就保证了设计图与页面的1:1关系，那么我们就可以直接使用 psd 中测量的尺寸了，然后在其他尺寸的手机中，我们进行等比缩放就ok了。

meta 标签中的`width=device-width`这段代码最终导致的结果是：让布局视口的尺寸等于理想视口的尺寸。

那么如果我们能改变理想视口的尺寸，也就改变了布局视口的尺寸。这就需要用到篇一提到的**缩放**。

上结论：实际上，我们需要缩小的倍数 = 设备像素比的倒数。

动态设置 meta :

	<script>
	var scale = 1 / window.devicePixelRatio;
	document.querySelector('meta[name="viewport"]').setAttribute('content','width=device-width,initial-scale=' + scale + ', maximum-scale=' + scale + ', minimum-scale=' + scale + ', user-scalable=no');
	</script>

### rem

rem是相对尺寸单位，相对于html标签字体大小的单位
e.g. 如果 html 的 font-size = 18px; 那么 1rem = 18px

### 总结

1. 将布局视口大小设为设备像素尺寸：

	var scale = 1 / window.devicePixelRatio;
	document.querySelector('meta[name="viewport"]').setAttribute('content','width=device-width,initial-scale=' + scale + ', maximum-scale=' + scale + ', minimum-scale=' + scale + ', user-scalable=no');

2. 动态设置html字体大小：

	document.documentElement.style.fontSize = document.documentElement.clientWidth / 10 + 'px';

3. 将设计图中的尺寸换算成rem

元素的rem尺寸 = 元素的psd稿测量的像素尺寸 / 动态设置的html标签的font-size值

### 网易版做法总结：

1. 拿到设计图，计算出页面的总宽，为了好计算，取100px的 font-size，如果设计图是 iPhone6 的那么计算出的就是7.5rem，如果页面是 iPhone5 的那么计算出的结果就是6.4rem。

2. 动态设置html标签的font-size值：

		document.documentElement.style.fontSize = document.documentElement.clientWidth / 以rem为单位的页面总宽 + 'px';

e.g.

iPhone6：
	
	document.documentElement.style.fontSize = document.documentElement.clientWidth / 7.5 + 'px';

iPhone5：
	
	document.documentElement.style.fontSize = document.documentElement.clientWidth / 6.4 + 'px';

3. 做页面时测量设计图的px尺寸除以100得到rem尺寸。
4. 和淘宝的做法一样，文字字体大小不要使用rem换算。


## 篇三

概念

### PPI（Pixel Per Inch）

显示设备：屏幕的像素密度

图片相关：打印时的分辨率或打印机的打印精度

在1英寸单位内面积内拥有的像素越多，密度越大，PPI值就越高。

但像素密度的实际意义是什么？它表达的是什么？或高或低对设备显示来说有什么影响？

在LCD显示设备中，每一个像素（pixel，也可以称之为dot）又是由三个子像素(subpixel)红绿蓝组合而成。

显示器上的像素就是物理像素(physical pixel)、设备像素(device pixel)

在浏览器里缩放页面（通过“Ctrl”键加上鼠标滚轮），缩放的是CSS像素。

得出一个非常重要的概念，就是CSS像素从来都只是一个相对值。

回答上面的问题：**PPI中的pixel指的应该是物理像素**

但[维基百科](http://en.wikipedia.org/wiki/Pixel_density)有不同的解释。




























