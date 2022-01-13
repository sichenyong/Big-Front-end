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



## 3.3、对象

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




## 3.4、流程控制

1、if判断

```javascript
var age = 3;
if (age > 3) {
     alert('haha');
} else {
     alert('ku');
}
```

2、while循环

```javascript
while(age < 100) {
            age = age + 1;
            console.log(age);
        }

do {
    age = age + 1;
    console.log(age);
}while(age < 100) 
```

3、for循环

```javascript
for (let i = 1; i <= age; i++) {
            console.log(age);
        }
```

4、数组循环 (forEach & for)

```javascript
/**forEach**/
var age = [1,2,3,4,5,6,7,8,9];
        age.forEach(function (value) {
            console.log(value);
        })

/**for 循环**/
/**下标**/
for (let num in age) {
            console.log(age[num]);
        }
/**具体值**/
for (let num of age) {
            console.log(num);
        }
```



## 3.5、map set

### 3.51、map

```javascript
var map = new Map([['Tom',99],['Jerry',100]]);

var name = map.get('Tom'); // 通过key获取value

map.set('admin',999); //设置键值对

map.delete('admin'); //删除键值对

console.log(name);
```

### 3.52、set

```javascript
var set = new Set([3,1,1,1,1]); // 可以去重
console.log(set);

set.add(2); //添加一个
set.delete(1); //删除一个
set.has(3); //查询是否在set中
```



## 3.6、iterator

遍历数组

```javascript
var arr = [1,2,3];
        for (let num of arr) {
            console.log(num);
        }
```

遍历map

```javascript
var map = new Map([['Tom',99],['Jerry',100]]);
        for (let x of map) {
            console.log(x);
        }
```

遍历set

```javascript
var set = new Set([5,6,7]);

        for (let x of set) {
            console.log(x);
        }
```

# 4、函数及面向对象

## 4.1、函数定义

- typeof x -- 获取x的类型

> 定义方式一

绝对值函数

```javascript
function function_name(xxx) {
    
    return xxx;
}
```

执行到return代表函数结束，若没有执行return，函数执行完也会返回结果，undefined

> 定义方式二

```javascript
var function_name = function(xxx) {
    return xxx;
}
```

funciton(x){....}是一个匿名函数，但是可以把结果赋值给abs，通过abs就可以调用函数！

> 调用函数

```javascript
function_name(xx);
```

javascript可以传任意个参数，也可以不传递参数

不存在参数的时候异常处理

```javascript
function abs(x) {
            if (typeof x != 'number') {
                throw 'not a number!';
            } else if (x > 0) {
                return x;
            } else return -x;
       }
```

> ```
> arguments
> ```

arguments是js免费赠送的关键字，是传递进来的所有参数，是一个**数组**

> rest

ES6引入的新特性，获取除了已定义的参数之外的所有参数

以前

```javascript
function aaa(a, b) {
            console.log('a = ' + a);
            console.log('b = ' + b);

            if (arguments.length>2) {
                for (let i = 2; i < arguments.length; i++) {

                }
            }
        }
```

现在    --固定格式(...rest)且必须放在最后面

```javascript
function aaa(a, b,...rest) {
            console.log('a = ' + a);
            console.log('b = ' + b);
            console.log('rest = ' + rest);
        }
```

## 4.2、变量的作用域

在JavaScript中，var定义的变量是有作用域的

若在函数体中声明，函数体外不可用， 若非要想用，可以研究闭包

```javascript
function scy() {
        var x = 1;

        x = x + 1;
    }
    x = x + 2; //Uncaught ReferenceError: x is not defined
```

若在两个函数中使用了相同的变量名，只要在函数内部就不冲突



内部函数可以访问外面的函数的成员，反之不行

```javascript
function scy() {
        var x = 1;

        //内部函数可以访问外面的函数的成员，反之不行
        function  scy1() {
            var y = x + 1;
        }
        var z = y + 1; //Uncaught ReferenceError: y is not defined
    }
```

假设内部成员函数变量和外部成员变量相同时，重名！

```javascript
function scy() {
        var x = 1;

        //内部函数可以访问外面的函数的成员，反之不行
        function  scy1() {
            var x = 'a';
            console.log('内部x = ' + x); //内部x = a
        }
        scy1();
        console.log('外部x = ' + x); //外部x = z
    }
```

函数查找变量从自身函数开始，假设外部存在同名函数变量，则内部函数会屏蔽外部函数的变量



> 提升变量的作用域

```javascript
function scy() {
        var x = 'x' + y;
        console.log(x); //xundefined

        var y = 'y';
    }
```

结果：xundefined

说明js自动提升了y的声明，但是不会赋值；

```javascript
function scy() {
    	var y;
        var x = 'x' + y;
        console.log(x); //xundefined

        y = 'y';
    }
```

因此 在写JavaScript时，将所有变量定义都放在函数的头部，便于代码维护



> 全局函数

```javascript
//全局变量
var x = 1;

        function f() {
            console.log(x);
        }
        f();
        console.log(x);
```

> 全局对象window

```javascript
var x = 'xxx';
        alert(x);
        alert(window.x); // 默认所有全局变量都会自动绑定在window对象下
```

alert本是也是window变量

```javascript
var x = 'xxx';
        alert(x);
        //window.alert(window.x); // 默认所有全局变量都会自动绑定在window对象下
        var old_alert = window.alert;
        //old_alert(x);

        window.alert = function () {

        }
        window.alert(123); //alert失效

        window.alert = old_alert;
        window.alert(1234);
```

JavaScript实际上只有一个全局作用域，任何变量(函数也可以视为变量), 假设没有在函数作用范围内，就会向外查找，如果在全局作用域都没找到，会报错ReferenceError

> 规范

由于我们的所有全局变量都会绑定到我们的window上，不同的js文件，使用相同的全局变量，如何能减少冲突？

```javascript
var Sichenyong = {};

        Sichenyong.name = 'sichenyong';
        Sichenyong.add = function (a,b) {
            return a + b;
        }
```



将自己用到的全部代码全部放入自己定义的唯一空间名字中，降低全局命名冲突问题~



> 局部作用域 let

```javascript
//var
function aaa() {
            for (var i = 0; i < 100; i++) {
                console.log(i)
            }
            console.log(i + 1); //101, i出了作用域还能用
        }

        aaa();
```



```javascript
//let
function aaa() {
            for (let i = 0; i < 100; i++) {
                console.log(i)
            }
            console.log(i + 1); //i is not defined
        }

        aaa();
```



> 常量const

在ES6之前怎么定义常量？ 全部用大写字母定义的变量就是常量

```javascript
var PI = '3.14';
console.log(PI);
PI = 'aaa';
console.log(PI); //可以改的
```

ES6

```javascript
const PI = '3.14';
console.log(PI);
PI = 'aaa'; //这里会报错
console.log(PI); //Uncaught TypeError: Assignment to constant variable.
```
