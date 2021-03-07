# 学习笔记
## 寻路算法 （为了熟悉广度优先搜索，了解算法可视化）

### localStorage序列化 
1. 使用 JSON.parse() 方法将数据转换为 JavaScript 对象。
2. 使用 JSON.stringify() 方法将 JavaScript 对象转换为字符串。
3. localStorage 和 sessionStorage 属性允许在浏览器中存储 key/value 对的数据。
4. localStorage 用于长久保存整个网站的数据，保存的数据没有过期时间，直到手动去删除。
5. localStorage 属性是只读的。

### DOM事件监听
1. HTML DOM 事件允许Javascript在HTML文档元素中注册不同事件处理程序。
2. 事件通常与函数结合使用，函数不会在事件发生前被执行！
    ```
    onclick     	当用户点击某个对象时调用的事件句柄。	
    oncontextmenu	在用户点击鼠标右键打开上下文菜单时触发
    onmousedown 	鼠标按钮被按下。
    onmousemove	    鼠标被移动。
    preventDefault()	通知浏览器不要执行与事件关联的默认动作。
    addEventListener()	允许在目标事件中注册监听事件(IE8 = attachEvent())
    ```

### JavaScript鼠标事件

1. mousemove方法
    > 当鼠标指针在指定的元素中移动时，就会发生 mousemove 事件。
    mousemove() 方法触发 mousemove 事件，或添加当发生 mousemove 事件时运行的函数。
    注意：用户把鼠标移动一个像素，就会发生一次 mousemove 事件。处理所有 mousemove 事件会耗费系统资源。请谨慎使用该事件。
2. mousedown() 方法
    > 当鼠标指针移动到元素上方，并按下鼠标左键时，会发生 mousedown 事件。
    mousedown() 方法触发 mousedown 事件，或添加当发生 mousedown 事件时运行的函数。
    提示：该方法通常与 mouseup() 方法一起使用。
3. mouseup() 方法
    > 当鼠标指针移动到元素上方，并松开鼠标左键时，会发生 mouseup 事件。
    mouseup() 方法触发 mouseup 事件，或添加当发生 mouseup 事件时运行的函数。
    提示：该方法通常与 mousedown() 方法一起使用
4. contextmenu() 
    > 单击右键触发 contextmenu 事件
    函数用于添加事件处理程序到 contextmenu 事件。
    注意：.contextmenu() 方法只是作为 .on( "contextmenu", handler ) 的一个速记写法，移除该事件可以使用 .off( "contextmenu" ) 。
5. > backgroundColor 属性设置或返回元素的背景颜色。
    老师的代码中是这么使用的  ： 类名.style.backgroundColor

### 寻路问题算法
> 寻路问题更适合广度优先搜索，而不是更为复杂的递归的深度优先搜索

1. 数组方法

```
pop()	删除数组的最后一个元素并返回删除的元素。
push()	向数组的末尾添加一个或更多元素，并返回新的长度。
shift()	删除并返回数组的第一个元素。
unshift()	向数组的开头添加一个或更多元素，并返回新的长度。
 ```

2. 数据结构queue
> 指的是一种数据结构，先进先出 ，一边进一边出，JavaScript里面也有类似的数据结构，
    JavaScript里面的数组就是一个天然的队列，也是一个天然的栈，有上述pop、push和shift、unshift两组方法 
    如果push和shift相对那么它就是一个队列，pop和 unshift联合使用它也是一个队列 ，
    如果pop和push一起使用那它就是一个栈 ，同样shift和unshift也是，但一般我们不用shift和unshift去做栈，因为这样性能可能会变低 


3. 寻路优化
>其实寻路算法中用广度优先搜索并不是最优的解题方法，启发式寻路更好
启发式寻路就是用一个函数来判断这些点扩展的优先级，判断好了优先级就可以有目的的去寻路，
只要它的估值一定小于这个点到终点的路径，那这个启发式寻路就一定可以找到最优路径，这种启发式寻路在计算机领域里面称为 A* ,而不一定能找到最优路径的启发式寻路称为 A。
所以说A* 就是A 寻路的一个特例。


children() 方法返回返回被选元素的所有直接子元素。