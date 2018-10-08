# 

# CSS各种选择器的用法：**

## **简单选择器：（type、id、calss）**

### ***1.TYPE选择器***

红色，实心边框为1像素

![solid](E:\html\project1\project2\solid.png)

### ***2.ID选择器***

如果想要直接定位到某一个元素，直接对这个元素进行样式的修改或添加

首先在html中，给这个元素添加一个id取值，这个id取值是唯一的

如图：

![id1](E:\html\project1\project2\id1.png)

# **ID选择器的语法用#表示**

然后在前面的样式设置里填写#+ID取值+{}

如图：



![id2](E:\html\project1\project2\id2.png)

### 3.calss选择器

如果想要突出一些重点内容，有多个优势或亮点，，并且不在同一个地方，

首先设置好想要突出的重点的样式效果，如：

红色、加粗、斜体、加下划线等效果

![calss1](E:\html\project1\project2\calss1.png)

然后找到想要突出的重点，在元素里设置class取值，如图（有多个突出重点，可以设置多个）

![class2](E:\html\project1\project2\class2.png)

最后在设置样式里添加 ”.+class取值“

![class3](E:\html\project1\project2\class3.png)



另外一种情况是class有两个取值，它不像ID取值只有一个唯一值，class可以取多个值，如图：

![class4](E:\html\project1\project2\class4.png)

样式设置为：

![](E:\html\project1\project2\class5.png)



表示class取值既有important又有abc的样式，，，

最后的得到的效果，只有设置了这两个取值的，才会显示出  红色，加粗、斜体、加下划线、还有背景色为黄色

如图：

![](E:\html\project1\project2\class6.png)



## 属性选择器：

如何出现下图的效果

![](E:\html\project1\project2\lable.png)

###### 如何让一个文本框处于禁用的状态，鼠标移动到禁用文本框时显示的是一个禁用符？

首先要添加文本框，<lable>留言：<input type="text"></input>

然后将文本框启用禁用状态,在type=”text“后加disabled,即：

<lable>留言：<input type="text" disabled></input>

然后在样式设置里设置

input[disabled]{

cursor:not-allowed;

}

![](E:\html\project1\project2\lable2.png)

如图所示：

即可出现。

对于文档内链接的样式设置，如何设置全部文档内的文档类链接的样式。

a [href="#"]    这个表示设置的只有一个文档内链接为”href=“#”   ”的样式设置

a [href^="#"]   这个表示设置的是全部文档内链接的样式设置

如图：

![](E:\html\project1\project2\lable3.png)

# 

# CSS中上下文选择器的表达式

一、e1 e2：表达的意思是我要选择e1后面的元素e2

二、e1>e2：表达的意思是我要选择e1选择器的一个子元素e2

三、e1~e2:表达的意思是我要选择e1中后续兄弟元素e2（必须满足两个条件：一、e1和e2必须是兄弟元素，二、e1和e2有一个先后关系）

四、e1+e2：表达的是我选择e1的后续的紧邻兄弟元素e2（必须满足三个条件：一、e1和e2必须是兄弟元素，二、e1和e2有一个先后关系 三、e1和e2是紧邻关系）

五、* ，星号可以作为一个通配符

例如1：![](E:\html\project1\project2\li1.png)

这个相当于e1空格e2

也就是选择的是ol元素中所有的li类型选择器（不管是第一代li还是第三代的li  ，只要是li元素都会被选中）

如图；![](E:\html\project1\project2\li3.png)



例如2:

![](E:\html\project1\project2\li2.png)

这个相当于e1>e2

也就是选择的是ol元素中的子元素，即只有第一代li元素，没有第三代li元素

如图：![](E:\html\project1\project2\li4.png)





例如3：

如果要选择的是ol#bad-sun中包含的后代元素li，但其不是ol#bad-sun的子元素li

等价于要选择的是  第二代后代元素、第三代后代元素。。。中的li元素

![](E:\html\project1\project2\li5.png)

其表达式为ol#bad-sun>*{}



# 伪类选择器：

## 第一种：结构化的伪类选择器

包含的表达式有：

### e:first-child 意思是选择的是e元素，只有它是父元素的第一个子元素的时候

例如：我们只想选择图片中的父元素ol的第一个li子元素时

![](E:\html\project1\project2\li4.png)



这时我会想到刚才的上下文选择器中的ol#bad-sun>li

我们将其改为：ol#bad-sun>li:first-child{}

这时就可实现选的只有第一个li的子元素

如图：![](E:\html\project1\project2\e1.png)

效果为![](E:\html\project1\project2\e2.png)

### 同理：e:last-child

### 拓展可得：nth-child(n)

例如：ol#bad-sun>li: nth-child(2)    即可选择的是以ol为最外层的元素的第一代的第二个子元素

#### 最常见的应用是：对表格的多行进行一个交替的背景色的展示

![](E:\html\project1\project2\e3.png)



## 第二种：UI伪类选择器

ui伪选择器用于处于某种交互状态的时候

在这些处于某种特殊交互状态的时候才具有

a元素：区分链接用户点击过的和没有被点击过的，即用户访问过的和没有访问过的样式是不一样的

## 对于访问过的用：a:vivsted

对已经访问过的超链接添加一个样式效果，以区分是否被用户访问过

如图：![](E:\html\project1\project2\e4.png)



## 没有访问过的用：a:link

### e:hover

意思是当前处于这个鼠标的这个悬停状态，也就是说当鼠标移动当e元素上方时，这个e元素就会被选中，当鼠标挪开的时候，e元素就不会被选中。

应用：对于链接的是

### a:hover

，当鼠标移动到带有链接的文字时，该文字就有样式的变化（如果我希望当鼠标移动到连接式，我看到的是有文字和背景颜色的变化）变化为蓝底白字

如图：![](E:\html\project1\project2\e5.png)

e:foucs：表单

e:checked:单选框和复选按钮

e:active：激活或未被激活的样式变化

e:target: