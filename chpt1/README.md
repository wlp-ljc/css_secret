# css secret(css 揭秘)

> 本章主要介绍css3的背景知识

## rgba 和 hsla

​	css2.1，常用的背景颜色有RGB、HEX两种方法。RGB是一种加色模型，主要由红、绿、蓝三原色的光以不同的比例相加，以产生不同的色光。在css常用的方法如rgb(255,255,0)、rgb(23,34,45)。HEX与RGB类似，只不过采用16进制的形式表示颜色，如#FFFF00、#124567等。

​	css3 添加了rgba、hsl和hsla的方法。rgba在rgb的基础上，添加透明度alpha，其中alpha的值取0.0-1.0之间。hsl和hsla是对是对RGB色彩空间中点的两种有关系的表示，它们尝试描述比 RGB 更准确的感知颜色联系，并仍保持在计算上简单。其中色相（H）是色彩的基本属性，就是平常所说的颜色名称，如红色、黄色等，取0-360。饱和度（S）是指色彩的纯度，越高色彩越纯，低则逐渐变灰，取0-100%的数值。亮度（L），取0-100%。hsla在hsl的基础上，添加了透明度alpha。

> 本部分内容参照[w3c](https://www.w3.org/standards/)、[博客园](http://www.cnblogs.com/super-w/archive/2013/01/24/2874632.html)的内容，感谢两位作者。

​	通过一些实例说明rgb、rgba、hsl、hsla、hex的用法。

**定义公共的模块**

```css
      .demo {
			width: 200px;
			height: 200px;
			margin: 10px;
			text-align: center;
			line-height: 200px;
			display: inline-block;
      }
```

## **rgb**

​	css代码定于如下：

```css
		.bac-rgb {
			background: rgb(255,135,3);
		}
		.bac-rgb-2 {
			background: rgb(135,255,3);
		}
```

​	通过浏览器查看div的背景，发现如下图(ps注:background填充content-box 即包含content、padding的内容，不包括margin、border的内容 )

![rgb背景](../imgs/rgb.png)

## **rgba**

​	css代码定义如下

```css
		.bac-rgba {
			background: rgba(255,135,3,0.0);
		}
		.bac-rgba-alpha-half {
			background: rgba(255,135,3,0.5);
		}
		.bac-rgba-alpha {
			background: rgba(255,135,3,1.0);
		}
```

​	通过浏览器查看显示的div，发现alpha为0时，背景完全透明，为0.5时，背景颜色有一定的虚化，为1时，与rgb显示相同。

![rgba](../imgs/rgba.png)

## hex

​	css代码如下

```css
		.bac-hex {
			background: #FF8703;
		}
		.bac-hex-2 {
			background: #87FF03;
		}
```

​	通过浏览器查看显示的div，与rgb显示定义相同。

![hex](../imgs/hex.png)

## hsl

​	rgb与hsl的转换方法可参加[csdn博客]([颜色空间RGB与HSV(HSL)的转换](http://blog.csdn.net/jiangxinyu/article/details/8000999)), 将rgb中的代码转换为hsl，css代码如下([在线转换](http://tools.jb51.net/color/rgb_hex_hsl))

```css
		.bac-hsl {
			background: hsl(31, 100.0%, 50.6%);
		}
		.bac-hsl-2 {
			background: hsl(89, 100.0%, 50.6%));
		}
```

​	显示内如如下图，hsl与rgb转换后，两者的显示背景是相同的。

![hsl](../imgs/hsl.png)

## hsla

​	hsla是在hsl的基础上，添加了透明度，css代码如下

```css
		.bac-hsla {
			background: hsla(31, 100.0%, 50.6%, 0.0);
		}
		.bac-hsla-alpha-half {
			background: hsla(89, 100.0%, 50.6%, 0.5);
		}
		.bac-hsla-alpha {
			background: hsla(89, 100.0%, 50.6%, 1);
		}
```

​	显示如下图，与rgba的背景颜色是相同的

![hsla](../imgs/hsla.png)

## 几种方法的使用方式

| 方法名称 |     使用方法      |                   参数说明                   |
| :--: | :-----------: | :--------------------------------------: |
| rgb  |  rgb(r,g,b)   |           红、绿、蓝三原色的值，默认取0-255            |
| rgba | rgba(r,g,b,a) |                a透明度，默认0-1                |
| hex  |     #RGB      |        红、绿、蓝三原色的值。默认000000-FFFFFF        |
| hsl  |  hsl(h,s,l)   | h取0-360 0-120 红 120-240 绿 240-360 蓝，s\l 0%-100% |
| hsla | hsla(h,s,l,a) |                a透明度，默认0-1                |

