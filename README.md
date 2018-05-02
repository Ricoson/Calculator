

# 简易计算机（主要是对JS代码的六次优化和改写更新）<br>

# 功能：
　　　 # 普通加、减、乘、除、取余、幂、倒数<br>
			<br>
	　　　## 第一次：代码的结构和行为分离<br>
	　　　			具体就是把html结构中绑定事onClick分离出，使用querySelectorAll获取所有运算符在js中实现绑定事件<br>
	　　　<br>
	　　　## 第二次：把所有运算使用循环<br>
	　　　			把使用querySelectorAll获取所有运算符类似数组用for循环遍历，用swith-case判断是哪种运算<br>
	　　　<br>
	　　　## 第三次：提取函数<br>
	　　　			避免程序暴露过多细节，采用函数封装起来，具体是把运算符赋值、计算用函数封装<br>
	　　　<br>
	　　　## 第四次：管理代码<br>
	　　　			把所有的零散全局变量用对象组织起来变成属性，方便管理，<br>
				具体是把计算机所用元素和计算机运算分别放在calculatorElem对象和operation中<br>
	　　　<br>
	　　　## 第五次：OCP(Open Closed Principe)关闭原则<br>
					把switch-case用operate运算函数代替，利用计算机增加新的功能，在operation对象中添加提供新运算的方法addOperation,<br>
				在函数中先判断是否已有该运算，添加链式操作<br>
	　　　<br>
	　　　## 第六次：代码模块化<br>
	　　　			使用匿名函数自调用避免全局作用域污染变量环境，具体就是接受参数将运算结果返回把这个过程封装模块返回<br>
				operate函数然后给外界暴露operate接口,增加取余、幂运算的计算<br>
			<br>	
	　　　## 第七次：完善代码-不明确传多少参数<br>
	　　　			增加计算新功能求倒数，只接受一个参数。具体是使用类数组arguments但是想去掉arguments的第一元素，<br>
				这里使用call让argumengts借用数组的去掉数组第一个元素slice()方法<br>