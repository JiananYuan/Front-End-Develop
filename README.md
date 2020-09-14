# Web前端开发笔记
# JavaScript Web 开发技术 (第2版)
<br>

## 第一章  JavaScript及其Web开发语言

实现页面的实时响应、动态呈现、人机交互的描述技术就是js脚本的主要功能，是目前最流行的页面脚本描述工具。
  
脚本语言的特征：容易使用，解释实现，运行方便，交叉使用，通信功能强大。
  
  客户端应用的三种形式：
  
  1）利用<body>标记中的<onload>属性直接使用js语句 
	
    <body onload = JavaScript:document.write("jsjsjsjs")></body>
  
  2）利用script标记中的language属性直接使用js代码 

	<body>
		<script type="text/javascript">
			document.write("<br>dskjfhjk");
  		</script>
	</body>
  
  3) 引用

    <script src = "link.js"><script>

<br>

## 第二章  语法基础
    
  强制类型转换符：Number和String
  
#### 对话框：
  
  警示对话框：

    <script type="text/javascript">
	
		flag = alert("alarm: ");
	
		if(flag) document.write("confirm");
	
		else     document.write("cancel");
	
  	</script>

  确认对话框：

    <script type="text/javascript">
	
		var flag = confirm("请指定您所在的学院：计算机学院 / 软件学院 ");
		
		school = flag ? "计算机学院" : "软件学院";
		
		document.write("您所在的学院是：" + school);
		
	</script>

  输入对话框：

    <script type="text/javascript">
	
		var school = prompt("请指定您所在的学院：","请在此输入学院名称");
		
		document.write("您所在学院是：" + school);
		
	</script>
	
  	

  内置函数：

	eval("...") // 计算字符串表达式的值
	parseInt() // 字符串到数值的进制转换
	
<br>

## 第三章 流程控制

  数组相关：

	var a = new Array() // 声明一维数组
	
  函数相关：

	<script language = "JavaScript">
		function comp(k) {
			var rec = 0;
			for(var i = 1;i <= k; i++) rec += i;
			return rec;
		}
		var c = comp(7);
		document.write("answer is: " + c);
	</script>
	
	
<br>

## 第四章 对象编程

	<!DOCTYPE html>
	<html>
		<head>
			<title>js</title>
		</head>
		<body>
			<script language = "JavaScript">
				function MyFun() {
					var tm = new Date();
					var y = tm.getFullYear();
					var mth = tm.getMonth()+1;
					var d = tm.getDate();
					var h = tm.getHours();
					var m = tm.getMinutes();
					var s = tm.getSeconds();
					document.write("<h1>今天是：" + y + "年" + mth + "月" + d + "日");
					document.write("<h1>现在是：" + h + "时" + m + "分" + s + "秒");
				}
				MyFun();
			</script>
		</body>
	</html>

<br>

## 第五章 事件处理

  函数调用实现事件句柄
	
	<!DOCTYPE html>
	<html>
	<head>
		<title>js</title>
		<meta charset="utf-8">
		<script type="text/javascript">
			function func() {
				window.status = "欢迎访问计算机科学与工程学院主页";
			}
		</script>
	</head>
	<body>
		<a href="http://csse.szu.edu.cn/cn/index.html" onmouseover="func()">
			点此进入计算机学院
		</a>
	</body>
	</html>

  窗口事件

  鼠标事件

	<!DOCTYPE html>
	<html>
	<head>
		<title>js</title>
	</head>
	<body><pre>
		<form name = "form1">
			<input type="button" value="鼠标  位置" onclick = "alert('鼠标X  位置:' + window.event.screenX);">
		</form>
	</pre></body>
	</html>
--------------------------
	<!DOCTYPE html>
	<html>
	<head>
		<title>js</title>
		<script type="text/javascript">
			function getMousePosition() {
				document.form1.text1.value = "鼠标位置：第" + window.event.x + "行，" + window.event.y + "列";
			}
		</script>
	</head>
	<body onmousedown="getMousePosition()">
		<pre>
			<form name = "form1">
				<input type="text" name="text1" size = 28>
			</form>
		</pre>
	
	</body>
	</html>
--------------------------

	<!DOCTYPE html>
	<html>
	<head>
		<title>js</title>
		<script type="text/javascript">
			function display(str) {
				document.form1.prompt.value = str;
			}
		</script>
	</head>
	<body>
	<pre>
		<form name = "form1">
			<input type="prompt" name="prompt" size = 50>
		</form>
		请选择链接：
		<a href="www.163.com" onmouseover="display('first link')"> 163 </a>
		<a href="www.baidu.com" onmouseover="display('second link')"> Baidu </a>
		<a href="www.google.com" onmouseover="display('third link')"> Google </a>
		
	</pre>
	</body>
	</html>
-------------------------

	<!DOCTYPE html>
	<html>
	<head>
		<title>js</title>
		<script type="text/javascript">
			var cnt = 0;
			function func() {
				cnt++;
				document.form1.text1.value = "click for " + cnt + " times";
			}
		</script>
	</head>
	<body>
		<form name = "form1">
			<p><input type="text" name="text1" value = "0"></p>
			<p><input type="button" name="button1" value = "click" onclick="func()"></p>
		</form>
	</body>
	</html>
---------------------------
	<!DOCTYPE html>
	<html>
	<head>
		<title>js</title>
		<script type="text/javascript">
			var kwd = "";
			function whichKwd(event) {
				kwd += "\n" + window.event.keyCode;
			}
			function btnClick() {
				if(kwd == "") {
					window.alert("没有按键");
				} else {
					window.alert("已经按键" + kwd);
					kwd = "";
				}
			}
		</script>
	</head>
	<body onkeyup="whichKwd(event)"><pre>
		<form>
			<input type="button" name="button1" value = "跟踪按键" onclick="btnClick
			()">
		</form></pre>
	</body>
	</html>
---------------------------
表单事件

onchange
<br><br>

----------------

submit

	<!DOCTYPE html>
	<html>
	<head>
		<title>js</title>
		<script type="text/javascript">
			function checkData() {
				var str = document.form1.text1.value;
				str = parseInt(str);
				if(str > 0 && str < 10) {
					alert("pass");
					return true;
				} else {
					alert("refuse");
					return false;
				}
			}
		</script>
	</head>
	<body>
		<pre>
			<form name = "form1" method = "post" onsubmit = "checkData()">
				<p>
					请输入1-9之间的数字：
					<input type="text" name = "text1" value = "0" size = 13>
				</p>
				<input type="submit">
			</form>
		</pre>
	</body>
	</html>

---------------------

blur

	<!DOCTYPE html>
	<html>
	<head>
		<title>js</title>
		<script type="text/javascript">
			function upCase() {
				var x = document.getElementById("text1").value;
				document.getElementById("text1").value = x.toUpperCase();
			}
		</script>
	</head>
	<body>
	input string:<br>
	<input type="text" id = "text1" size = 40 onblur = "upCase()" />
	</body>
	</html>

--------------------
focus

	<!DOCTYPE html>
	<html>
	<head>
		<title>js</title>
		<script language = "JavaScript">
			function check() {
				if(document.form1.text12.value.length != 8) {
					alert("wrong");
					document.form1.text12.focus();
					document.form1.text12.select();
					return false;
				}
				return true;
			}
		</script>
	</head>
	<body>
	<pre>
		<form name = "form1" method = post onsubmit = "check()">
			<p>用户姓名：<input name = "text11"></p>
			<p>电话号码：<input name = "text12" onfocus = "check()"></p>
			<p><input name="submit" type="submit" value = "send"></p>
		</form>
	</pre>
	</body>
	</html>

---------------------

error事件

	<!DOCTYPE html>
	<html>
	<head>
		<title>js</title>
		<meta charset="utf-8">
		<script type="text/javascript">
			function handleError(msg,url,line) {
				var s = "错误消息:\t" + msg + "\n错误文档:\t" + url + "\n错误行号:\t" + line
				alert(s)
			}
		</script>
	</head>
	<body>
	<pre>
		<h4>error occurs</h4>
		<script type="text/javascript">
			window.onerror = handleError;
		</script>
		<form>
			<img src="error" src = "pic.jpg" onclick = "oper()">
		</form>
	</pre>
	</body>
	</html>


<br>

## 第六章 window对象集

constructing...


<br>

## 第七章 document对象集


constructing...

<br>

## 第八章 form对象

constructing...


<br>

## 第九章 hidden对象与cookie

constructing...


<br>

## 第十章 文件处理

constructing...


<br>

## 第十一章 网页特效

constructing...


<br>

## 第十二章 高级应用

constructing...

