# 1、什么是JavaScript

JavaScript是当下最流行的脚本语言



# 2、快速入门

## 2.1、引入JavaScript

### 2.11 内部引入

```javascript
<script>
        alert('hello world!');
</script>
```

### 2.22 外部引入

```javascript
<!--script外部引用 必须成对出现-->
<script src="js/script.js"></script>
```



测试代码

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <!--在script标签内写JavaScript代码-->
    <!--<script>
        alert('hello world!');
    </script>-->

    <!--script外部引用 必须成对出现-->
    <script src="js/script.js"></script>
</head>
<body>

</body>
</html>
```



## 2.2、基本语法内容

- 如何调试
    - F12 console控制台，编写JavaScript代码
    - F12 console控制台 console.log()
    - 逐步debug F12 source
    - application 保存web数据

![image-20220112131411015](E:\FulllStack\JavaScript\FullStack\note-images\1.png)

- elements 查看html css文件
- console 控制台，调试js代码
- source 打断点
- network 抓包
- application 保存web数据



```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>基本语法</title>
    <!--
    严格区分大小写
    在浏览器的控制台打印变量 console.log()
    -->
    <script>
        /*定义变量*/

        var score = 60;

        /*条件控制*/
        if(score >= 70 && score <= 80) {
            alert('70分');
        } else if (score < 70){
            alert('不合格');
        } else {
            alert('other');
        }

    </script>
</head>
<body>

</body>
</html>
```



## 2.3、 数据类型

- 数值
- 文本
- 图形
- 音频
- 视频



**变量**

- 不以数字开头

```javascript
var ob
```





**number** -- js中不区分整数、小数

```javascript
123 //整数123
123.1 //浮点数123.1
1.23e3 //科学计数法
-99 //负数
NaN // not a number
Infinity //表示无限大
```

**字符串**

```javascript
'ab'
"ab"
```



**布尔值 **true false

**逻辑运算**

```javascript
&& //两个都真才是真
    
   
|| //一个是真就是真
    

! // 真的话是假 假的话是真
```

**比较运算** 不使用==

```javascript
=
== (类型不一样，值一样也为真)
=== (绝对等于)
```

须知

- NaN 与所有的数值都不相等，包括自己

- 只能通过isNaN(NaN)来判断是否是NaN

- 浮点数问题

  ```javascript
  console.log(1/3 === 1 - 2/3)
  ```

  结果为false，尽量避免使用浮点数比较，存在精度问题

  若用到了，用Math.abs(1/3 - (1-2/3)) < 0.000000001 来判断



**null和undefined**

- null 空指针
- undefined 为定义的



**数组**

一系列相同元素的集合

```javascript
var arr = [1,2,3,'1a',null true	]
new Array(1,2,3,'1a',null true )
```

- 如果数组下标越界，会输出undefined



**对象**

对象是大括号，数组是中括号

```javascript
var person{
    name: sichenyong,
    age: 21,
    tags: ['handsome','boy']
}
```

- 取值用object. eg：person.name



## 2.4、 严格检查模式

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

  <script>
      /*
      *  写script时 加上 'use strict'
      * */
    //全局
    /*var i = 1;*/

    /*
    * 局部
    * */
      'use strict'
    let i = 1;
  </script>
</head>
<body>

</body>
</html>
```



# 3、数据类型

## 3.1、字符串

1. 正常字符串用''或""包括

2. 转义字符

   ```javascript
   \'
   \n /*换行*/
   \t /*一个tab的距离*/
   \u4e2d /*unicode字符 \u**** */
   \x41 Ascll字符
   ```



3. 多行字符串编写

   ```javascript
   /*tab键上面的 可以多行编写*/
   
           var msg = `nihao
   
          woshi
          hao
          ren`;
   ```



4. 模板字符串

   ```javascript
   /*模板字符串*/
           let name = 'sichenyong';
           let age = 19;
   
           let info = `你好啊, ${age}岁的${name}`;
   
           console.log(info)
   ```



5. 字符串长度

   ```javascript
   str.length
   ```



6. 字符串的可变性

   不可变！

7. 大小写转换

   ```javascript
   str.toUpperCase() /*大写*/
   str.toLowerCase() /*小写*/
   ```

8. 获取指定字符的下标

   ```javascript
   str.indexof('s'); /*获取s在str中的位置
   ```

9. 截取字符串 substring(a,b) [a,b)

   ```javascript
   str.substring(x) /*截取从x开始的字符串*/
   str.substring(a,b) /*截取从a开始到b-1的字符串*/
   ```



## 3.2、数组

**Array可以包含任意的数据类型**

```javascript
var arr = [1,2,3,4]
```

1. 长度

   ```javascript
   arr.length
   ```

   长度可变 arr.length = ??  长度变为 ??， 若长度过小 元素就会丢失

2. indexof 通过元素获取其所在位置

   ```javascript
   arr.indexof(2)
   ```

   字符串的1与数字1是不同的

3. **slice()** 截取Array的一部分，返回一个新的数组 类似于string中的substring

4. push，pop （尾部）

   ```javascript
   arr.push(x); //压入数组最后端
   arr.pop(); //弹出数组最后一个元素
   ```

5. shift unshift (头部)

   ```javascript
   arr.unshift(x); //头部插入
   arr.shift(x); //头部弹出
   ```

6. 排序

   ```javascript
   arr.sort()
   ```

7. 元素反转

   ```javascript
   arr.reverse()
   ```

8. concat(arrayname)

   ```javascript
   str.concat([1,2]); /*并没有修改原数组，只是会返回一个新的数组*/
   ```

9. 连接符join(x)

   打印拼接数组，使用特定的字符连接

10. 多维数组

    ```javascript
    arr = [[1,2],[3,4],['5','6']];
    
    console.log(arr[0][1])
    2
    ```



3.3、对象

若干键值对

JavaScript中所有的**键**都是**字符串**，所有的**值**都是**任意对象**

```javascript
var 对象名 = {
    属性名: 属性值,
    属性名: 属性值,
    ······
    属性名: 属性值
}

var person = {
            name: "司称勇",
            age: 18,
            score: 30
        }
```

js中的对象是由 {}表示

1. 对象赋值

   ```javascript
   person.age = 21;
   ```

2. 使用一个不存在的对象属性 不会报错

   ```javascript
   person.haha
   undefined
   ```

3. 动态删除属性，通过delete

   ```javascript
   delete 对象名.属性名
   ```

4. 动态添加属性

   ```javascript
   对象名.新的属性名 = 属性值
   ```

5. 判断属性值是否在对象中 xxx in xxx

   ```javascript
   person['age'] = 21;
   
   'age' in person
   
   out-- true
   
   'toString' in person /**person的父类中有toString**/
   out-- true
   ```

6. 判断一个属性是否是这个对象自身拥有的 hasOwnProperty()

   ```javascript
   person.hasOwnProperty('toString')
   
   out-- false
   ```

   