# 1.长文本用…代替

```` css
{

 word-break: break-all;

  overflow: hidden;

  text-overflow: ellipsis;

  display: -webkit-box;

  -webkit-box-orient: vertical;

  -webkit-line-clamp:1;     //显示几行

}
````



# 2.animation动画

animation-delay:动画开始的延迟时间，秒和毫秒    2s   200ms

animation-durnation:动画周期的时间，秒和毫秒

animation-fill-mode:动画结束后的样式，forwards使用元素的结束属性值

animation-iteration-count:动画播放的次数，n或者infinite

animation-timing-function:动画速度曲线

​			linear:开始和结束具有相同的速度

​			ease:缓慢的开始，然后块，结束慢

​			ease-in:缓慢的开始

​			ease-out:结束缓慢

​			ease-in-out:具有缓慢的开始和结束

​			cubic-bezier(n,n,n,n):立方贝塞尔函数，n是0到1的取值



# 3.calc函数的使用

## 	动态计算长度值

height: calc(100vh - 100rpx)





# 4.transform过渡



## translate( ) rotate( ) scale( )

## ① translate( x,y)：位移

## ② rotate( 30deg)：旋转 顺时针旋转30度

## ③ scale(2,4)：放大 宽度为原来的2倍，高度为原来的4倍



# 5.scss的使用



## ①scss混合器

使用@mixin定义混合器 ,可以使用参数

使用@include引用混合器

@mixin buju($a:column,$b:center,$c:center){

  display: flex;

  flex-direction: $a;

  justify-content: $b;

  align-items: $c;

}

## ②scss选择器继承

@extend 选择器

继承另一个选择器定义的所有样式

## ③插值语句

#{ }  可以在选择器和属性中使用

使用插值语句可以避免变量被运算

## ④ @for循环

@for $i from 1 to 5{

  .item-#{$i}{

​    margin:20px 0px;

​    background-color: yellow;

​    height: 10px * $i;

​    width: 10px * $i;

  }

}

### 可以使用to 和 through

to不包括右边的值，through包括左边的值

## ⑤@if判断

​    @if $i == 1{background-color: yellow;}

​    @else if $i == 2{background-color: blue;}

​    @else if $i == 3{background-color: red;}

​    @else {background-color: gray;}

## ⑥ 函数指令

@function add($n){

  @return $n * 10;

}

.box{

  height: add(10px);

  width: 100px;

  background-color: white;

  margin:50px;

}

#### 注意：scss中的运算可以带单位

## ⑦Math函数

### random（N）：返回一个1到N之间的整数



## ⑧ 数组函数

### nth( 数组，下标)：获取数组中的值，下标从1开始计数

$a:blue red yellow;

.box{

  height: 400px;

  width: 100px;

  background-color: nth($a,2);    //red

  margin:50px;

}

# 6.filter滤镜

## blur( Xpx)：高斯模糊

X数值越大，元素越模糊

## brightness(X%)：亮度

0%为全黑，100%为无变化，超过100%越来越亮

## grayscale( %)：灰度

0为无变化，1为完全变成灰度图谱

## invert( )：反转图像

0为无变化，1为完全反转

## sepia( )：将图像变成深褐色

## saturate( )：饱和度

100%无变化，100%以下色彩变淡，以上色彩变浓



# 7.inherit关键字的使用

inherit 关键字指定一个属性应从父元素继承它的值。

div{

​	background:url( 'xxx') no-repeat;

​	div{

​	background:inherit

​	}

}

# 8.clip-path裁剪路径

## clip-path: polygon(50% 0,75% 0%,75% 10%,50% 10%);

polygon( )：多边形裁剪  顺时针  最少需要定义三个点

## clip-path：inset(20% 50% 50% 20%)

clip-path: inset(0 0 500px 400px);

inset( )：矩形裁剪 上 右 下 左



# 9.在小程序中使用scss

* 安装vscode插件EasySass

* 修改setting.json

  ````  javascript
  //对EasySass的配置，此段配置去掉则默认生成一个css文件和一个压缩的min.css文件
    "easysass.formats": [
      {
        "format": "expanded", //格式，expanded不压缩，compressed压缩
        "extension": ".wxss" //输出文件的后缀,小程序可以写'wxss'
      },
      // {
      //   "format": "compressed",
      //   "extension": ".min.css"
      // }
    ],
  ````

  * 新建.scss文件，保存后自动生成wxss文件

  



