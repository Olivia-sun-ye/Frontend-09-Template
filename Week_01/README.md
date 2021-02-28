## 学习笔记

## CSS
* `display`
  ```
    none	        此元素不会被显示。
    block	        此元素将显示为块级元素，此元素前后会带有换行符。
    inline	        默认。此元素会被显示为内联元素，元素前后没有换行符。
    inline-block	行内块元素。（CSS2.1 新增的值）
    ```

* `boder`
    ```
    border-width	指定边框的宽度
    border-style	指定边框的样式
    border-color	指定边框的颜色
    border:solid 1px white 可以这样缩写
    ```
* `vertical-align`
    >属性设置一个元素的垂直对齐方式。
    >该属性定义行内元素的基线相对于该元素所在行的基线的垂直对齐。允许指定负长度值和百分比值。这会使元素降低而不是升高。在表单元格中，这个属性会设置单元格框中的单元格内容的对齐方式。
    
    ```
    baseline	默认。元素放置在父元素的基线上。
    sub	        垂直对齐文本的下标。
    super	    垂直对齐文本的上标
    top	        把元素的顶端与行中最高元素的顶端对齐
    text-top	把元素的顶端与父元素字体的顶端对齐
    middle	    把此元素放置在父元素的中部。
    bottom	    使元素及其后代元素的底部与整行的底部对齐。
    text-bottom	把元素的底端与父元素字体的底端对齐。
    length	    将元素升高或降低指定的高度，可以是负数。
    %	        使用 "line-height" 属性的百分比值来排列此元素。允许使用负值。
    inherit	    规定应该从父元素继承 vertical-align 属性的值。
    ```
* `text-align`
    ```
    left	把文本排列到左边。默认值：由浏览器决定。
    right	把文本排列到右边。
    center	把文本排列到中间。
    justify	实现两端对齐文本效果。
    inherit	规定应该从父元素继承 text-align 属性的值。
    ```
   
## JavaScrip
*   
    > ES2015(ES6) 新增加了两个重要的 JavaScript 关键字: let 和 const。
    let 声明的变量只在 let 命令所在的代码块内有效。
    const 声明一个只读的常量，一旦声明，常量的值就不能改变。
    在 ES6 之前，JavaScript 只有两种作用域： 全局变量 与 函数内的局部变量

    > var 关键字声明的变量不具备块级作用域的特性，它在 {} 外依然能被访问到
    在 ES6 之前，是没有块级作用域的概念的。ES6 可以使用 let 关键字来实现
    块级作用域。let 声明的变量只在 let 命令所在的代码块 {} 内有效，在 {} 之外不能访问。
    {}指的只有{}没有函数头什么的

    > 在函数体内使用 var 和 let 关键字声明的变量有点类似。它们的作用域都是 局部的
    在函数体外或代码块外使用 var 和 let 关键字声明的变量也有点类似。它们的作用域都是 全局的

    > 在 JavaScript 中, 全局作用域是针对 JavaScript 环境。在 HTML 中, 
    全局作用域是针对 window 对象。使用 var 关键字声明的全局作用域变量属于 window 对象，
    可通过window.变量名 来访问，而使用 let 关键字声明的全局作用域变量不属于 window 对象就不能通过 window.变量名 来访问

    >var 关键字定义的变量可以在使用后声明，也就是变量可以先使用再声明，let不能，需要先声明再使用
    var 关键字声明的变量在任何地方都可以修改：  而let不能直接这样，两者更不能相互串改，let只能这样改：

    > 实例

    ```
    var x = 2;
    var x = 3;
    ```
    ```
    let x = 2;       // 合法
    {
        let x = 3;   // 合法
    }
    {
        let x = 4;   // 合法
    }
    
    ```
* 
    >`document.createElement()`	创建元素节点
    
    >`document.createTextNode()`创建文本节点。(这属于HTML DOM Document对象属性和方法)
    
    >`classList` 属性返回元素的类名，作为 DOMTokenList 对象。该属性用于在元素中添加，
    移除及切换 CSS 类。classList 属性是只读的，但你可以使用 add() 和 remove() 方法修改它。
    
    >`innerText`属性仅返回文本，不包含空格和内部元素标签
    
    >`appendChild()` 方法可向节点的子节点列表的末尾添加新的子节点。

    例子:
    ```
    <ul id="myList1"><li>Coffee</li><li>Tea</li></ul>
    <ul id="myList2"><li>Water</li><li>Milk</li></ul>
    <p id="demo">单击按钮将项目从一个列表移动到另一个列表中</p>
    <button onclick="myFunction()">点我</button>

    <script>
    function myFunction(){
	    var node=document.getElementById("myList2").lastChild;
	    document.getElementById("myList1").appendChild(node);
    }
    </script>
    ```