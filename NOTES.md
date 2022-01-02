# 1. CSS导入方式

## 行内样式

```html
<h1 style="color: red">你好</h1>
```

## 内部样式

```html
    <!--内部样式-->
    <style>
        h1{
            color: green;
        }
    </style>
```

## 外部样式

```html
<!--外部样式-->
    <link rel="stylesheet" href="css/style.css">
```

```css
/*外部样式*/
h1{
    color: blue;
}
```

# 2. 三种基本选择器

## 2.1 标签选择器

```html
<style>
      h1{
          color: green;
      }
      p{
          font-size: 90px;
      }
  </style>

<h1>学习</h1>
<p>Java</p>
```

## 2.2 类选择器

- 格式：. + class后面的名称 +{}

```html
	<style>
        /**/
        .nihao{
            color: #7aff5b;
        }
        .hao{
            color: #ffc6ce;
        }
        .nv{
            color: #ff71a1;
        }
    </style>

<h1 class="nihao">你好</h1>
<h1 class="hao">好</h1>
<h1 class="nv">女</h1>
```

## 2.3 id选择器

- 格式：# +id名称 + {}

```html
	<style>
        #nihao{
            color: #ff71a1;
        }
    </style>
<h1 id="nihao">你好</h1>
```

## 2.4 关联

- 优先级 id > class > 标签
- id选择器 全局唯一
- 类选择器可以复用



# 3. 层次选择器

**层次图**

![1.png](notes-images/1.png)

- 后代选择器
- 子类选择器
- 相邻兄弟选择器
- 通用选择器

## 3.1 后代选择器

- 格式：body + 标签类型 + {}
- 作用域：所有该标签

```css
	body p{
            color: #ff91b4;
        }
```

## 3.2 子类选择器

- 格式： body + > + 标签类型
- 作用域：body后的**一代**

```css
body>p{
            background: #ff71a1;
        }
```

## 3.3 相邻兄弟选择器

- 格式： . + class名称 + "+" + 标签类型
- 作用域：class名称所在标签的下一个标签

```css
.active + p{
            background: red;
        }
```

```html
<p class="active">p1</p>
  <p>p2</p>
  <p>p3</p>
```

## 3.4 通用选择器

- 格式：. + class名称 + "~" + 标签类型
- 作用域：class名称所在标签的后面所有标签

```css
.active~p{
            background: antiquewhite;
        }
```

```html
<p class="active">p1</p>
  <p>p2</p>
  <p>p3</p>
```



# 4. 结构伪类选择器

- 格式：标签类型 + ":" + 条件

- 例子

- body

  ```html
  <body>
    <p>p1</p>
    <p>p2</p>
    <p>p3</p>
  
    <ul>
        <li>li1</li>
        <li>li2</li>
        <li>li3</li>
    </ul>
  </body>
  ```

- 选中第一个li

  ```css
  /*选中ul中的第一个li*/
          ul li:first-child{
              background: aquamarine;
              color: #ff71a1;
          }
  ```

- 选中最后一个li

  ```css
  /*选中ul中的最后一个li*/
          ul li:last-child{
              background: #71a7ff;
              color: #ffc6ce;
          }
  ```

- 选中body中的第一个元素

    - 第一种

        - nth 选中当前类型的父层

        - p:nth-child(x) 选中p类型的父层，父层的第x个的孩子是p标签才生效

  ```css
   p:nth-child(1){
              background: antiquewhite;
          }
  ```

    - 第二种

        - p: nth-of-type(x) 选中p类型的父层，父层的第x的p标签生效

      ```css
      p:nth-of-type(2){
                  background: #ffc6ce;
              }
      ```



# 5. 属性选择器（常用）

id +class 结合 = 属性选择器

- 几种等于符号
    - **=** --> 绝对等于
    - *= --> 通配符
    - ^= -->  通配符 前缀等于xx
    - $= --> 通配符 后缀等于xx

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>属性选择器</title>

    <style>
        .demo a{
            float: left;
            display: block;
            height: 50px;
            width: 100px;
            border-radius: 10px;
            background: #831626;
            text-align: center;
            color: aqua;
            text-decoration: none;/*取消下划线*/
            margin-right: 5px; /*每个border右移*/
            font: bold 20px/50px Arial; /*字体大小/行高*/
        }

        /*
            = -- 绝对等于
            *= -- 通配符
            ^= -- 以这个开头
            $= -- 以这个结尾
        */

        /* 选中带有id属性的元素 (id所在标签)[]{}
            本例子中为 a[id]{}
        */
        /*a[id] {

        }*/

        /*选中id属性为first的标签
          (id标签所在)[id=first]{}
          本例子中为 a[id=first]{}
        */
        /*a[id=first] {

        }*/

        /*选中class属性中含有links的标签
        (class所在标签)[class*="xxxx"]{}
        本例子中为 a[class*="links"]{}
        */
        /*a[class*="links"] {
            background: blue;
        }*/

        /*选中href中 以http开头的
            正则表达式中用^=
        */
        /*a[href^=http] {
            color: red;
        }*/
        
        /*选中href中以html结尾的*/
        a[href$=html] {
            background: #ffc6ce;
        }
    </style>

</head>
<body>
    <p class="demo">
        <a href="https://www.baidu.com" class="links item first" id="first">百度</a>
        <a href="http://www.4399.com/" class="links item active" target="_blank" title="test">4399</a>
        <a href="https://www.layuiweb.com/" class="links item">layui</a>
        <a href="https://cn.pornhub.com/" class="links item">pornhub</a>
        <a href="https://txzqw.me/" class="links item">天下足球网</a>
        <a href="https://leetcode-cn.com/?utm_source=LCUS&utm_medium=ip_redirect&utm_campaign=transfer2china" class="links item">leetcode</a>
        <a href="https://getbootstrap.com/" class="links item">bootstrap</a>
        <a href="https://sa-token.dev33.cn/doc/index.html#/" class="links item">sa-token</a>
        <a href="https://www.acwing.com/problem/" class="links item">acwing</a>
        <a href="https://www.thymeleaf.org/doc/tutorials/3.0/usingthymeleaf.html" class="links item first">thymeleaf</a>
    </p>
</body>
</html>
```



# 6. 美化网页



## 6.1 为什么要美化网页

![image-20220102092839571](C:\Users\48272\AppData\Roaming\Typora\typora-user-images\image-20220102092839571.png)



- 重点要突出的字用**span**标签套起来

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>span标签学习</title>
    <style>
        #title1{
            font-size: 40px;
        }
    </style>
</head>
<body>
<span id="title1">全栈</span>学习
</body>
</html>
```

## 6.2 字体样式

```html
<!--
    font-family: 字体
    font-size: 字体大小
    font-weight: 字体粗细
    color: 字体颜色
    -->
    <style>
        body{
            font-family:"Times New Roman", 华文楷体;
        }

        h1{
            font-size: 50px;
            color: #ff71a1;
        }

        .p1{
            font-weight: bold;
        }
    </style>
```



## 6.3 文本样式

1. 颜色 color rgb rgba
2. 文本对齐方式 text-align
3. 首行缩进 text-indent: xem
4. 行高 line-height
5. 装饰 text-decoration(划线)
6. 文本图片水平对齐 vertical-align: middle



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>万古神帝简介</title>

    <!--
    颜色：
        单词
        RGB （RED GREEN BLUE 对应 FF0000 00FF00 0000FF 自己调色）
        RGBA （A为透明度 a一般取值 0~1）
    排版 text-align
        center 居中
        left 左对齐
        right 右对齐
    缩进 text-indent xem
        1em = 一个字符
    行高和块高  一致的时候可以上下居中
        行高 line-height
        块高 height
    划线 text-decoration:
        上划钱 overline
        中划线 line-through
        下划线 underline
    -->
    <style>
        h1{
            color: rgba(63,189,255,0.4);
            text-align: center;
        }
        .p1{
            text-indent: 2em;
        }
        .p3{
            height: 30px;
            line-height: 30px;
        }
        .l1{
            text-decoration: underline;
        }

        .l2{
            text-decoration: line-through;
        }

        .l3{
            text-decoration: overline;
        }

        a{
            text-decoration: none;
        }
    </style>
</head>
<body>

<h1>作品简介</h1>
<hr/>
<p class="p1">
    八百年前，明帝之子张若尘，16岁时被未婚妻池瑶公主杀死，一代天骄，就此陨落。
</p>

<p class="l3">
    八百年后，张若尘重新活了过来，却发现曾经杀死他的未婚妻，已经统一昆仑界，开辟第一中央帝国，号称“池瑶女皇”。
</p>

<p class="l1">
    池瑶女皇——统御天下，威临八方；青春永驻，不死不灭。
</p>

<p class="l2">
    张若尘站在诸皇祠堂外，望着池瑶女皇的神像，心中燃烧起熊熊的仇恨烈焰，“待我重修十三年，敢叫女皇下黄泉”。
</p>
<a href="http://www.b520.cc/8_8187/" target="_blank">详情点击此处</a>

<hr/>
<h1>英文情诗</h1>
<p class="p3">
    Let me not to the marriage of true mindsAdmit impediments.Love is not loveWhich alters when it alteration finds,Or bends with the remover to remove:
</p>



</body>
</html>
```

图片与文字水平对齐

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <!--
    水平对齐 a,b  a向b对齐
    -->
    <style>
        img,span{
            vertical-align: middle;
        }
    </style>
</head>
<body>

<p>
    <img src="images/1.png" alt="文字">
    <span>
        123456789
    </span>
</p>
</body>
</html>
```



