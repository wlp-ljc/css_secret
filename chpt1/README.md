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

**rgb定于背景**

```css
		.bac-rgb {
			background: rgb(255,135,3);
		}
		.bac-rgb-2 {
			background: rgb(135,255,3);
		}
```



![rgb背景](../imgs/rgb.png)