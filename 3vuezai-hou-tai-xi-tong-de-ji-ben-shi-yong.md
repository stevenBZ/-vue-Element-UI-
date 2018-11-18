# vue 在后台系统的基本使用

### 一、基本使用形式-单文件组件

单文件组件是包含了视图模版、数据、业务逻辑和样式的综合文件。

从形式上看，单文件组件包含三个部分，&lt;template&gt;模版、&lt;script&gt;代码逻辑 、&lt;style&gt;样式。

使用单文件组件来构建页面，我们需要合理拆分组件来保持代码的可读性

![](/assets/import2.png)

### 二、模板基本语法

Vue.js使用了基于HTML的模板语法，允许开发者声明式地将DOM绑定到底层Vue实例的数据。



常用的数据绑定方式 ：

1、插值

使用双大括号的文本插值 ：

![](/assets/import3.png)

2、v-bind

插值不能作用在HTML特性上，遇到这种情况应该使用v-bind指令 ：

![](/assets/import5.png)

在布尔特性的情况下， 它们的存在即暗示为true，如 ：

![](/assets/import6.png)



指令

指令就是带有 v-前缀的特殊特性，指令的职责是，当表达式的值发生改变时，将其产生的连带影响，响应式地作用于DOM。

常用指令：

1、v-bind 响应式地更新HTML特性：

![](/assets/import7.png)

2、v-on绑定DOM事件

![](/assets/import9.png)

3、v-if/v-show条件渲染

![](/assets/import10.png)

不同的是带有v-show的元素始终会被渲染并保留在DOM中。V-show只是简单地切换元素的CSS属性display。

4、v-for列表渲染

![](/assets/import11.png)

遍历对象

![](/assets/import12.png)

5、v-model

v-bind和v-on的语法糖，在表单控件或者组件上创建双向绑定：

![](/assets/import13.png)



### 三、逻辑代码

在逻辑代码部分我们需要输出一个vue实例

![](/assets/import14.png)

这个实例通常由这以下选项组成。



1、name

指定组件名后允许组件模板递归地调用自身。另外，当使用vue-devtools工具进行调试时，未命名组件将显示成&lt;AnonymousComponent&gt;，不利于调试，通过提供name选项，可以获得更有语义信息的组件树。

2、 data

Vue实例的数据对象。当一个组件被定义时，data必须声明为返回一个初始数据对象的函数。Data返回的对象中的变量与模板中对应的变量会自动进行绑定。这个实例通常由这以下选项组成。

3、props

Props可以是数组或对象，用于接收来自父组件的数据。如：

![](/assets/import16.png)

或

![](/assets/import17.png)

4、created

Vue常用的生命周期钩子，在实例创建完成后被立即调用。在这一步，实例已完成以下配置：数据观测、属性和方法的运算，watch/event事件回调。然而，挂载阶段还没开始。后台系统中，我们一般在这里通过异步请求获取页面的初始数据。

![](/assets/import19.png)

5、mounted



页面元素被挂载到DOM实例后调用的生命周期钩子，当我们需要为某些页面元素添加监听事件或需要针对页面元素添加内容时我们会调用这个方法。

  
![](/assets/import20.png)



6、methods



定义方法的地方，methods将被混入到Vue实例中，可以通过Vm实例访问这些方法，或者在指令表达式中使用。方法中的this自动绑定为Vue实例。

![](/assets/import21.png)

7、watch

观察一个对象，键是需要观察的表达式，值是对应回调函数。当观察的表达式发生变化时触发回调函数。

![](/assets/import23.png)



8、components

在components中引入组件，组件名可以使用短杠形式或者驼峰格式书写。

![](/assets/import24.png)

![](/assets/import25.png)



### 四、样式

1、class的绑定

我们可以传给 v-bind:class 一个对象，以动态地切换class ：

![](/assets/import26.png)

![](/assets/import27.png)

2、style的绑定

![](/assets/import29.png)

![](/assets/import30.png)



3、 有作用域的CSS



当&lt;style&gt;标签有scoped属性时，它的CSS只作用于当前组件中的元素

![](/assets/import31.png)

你可以在一个文件中同时使用带作用域和不带作用域的样式

