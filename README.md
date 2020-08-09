<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>随机出现星星</title>
	<script>
	//window.onload=init;
	var count=0;
	var dingshiqi;
	function startGame(){
		var dingshiqi=window.setInterval("star()",500);
	}
	function star(){
		//创建星星
		var obj=document.createElement("img");
		//添加属性
		obj.src="img/8.jpg";
		//随机宽度
		var w=Math.floor(Math.random()*80+20);

		obj.width=w;
		//任何位置
		var x=Math.floor(Math.random()*1166+100);
		var y=Math.floor(Math.random()*500+100);
		//定位坐标
		obj.style.position="absolute";
		obj.style.top=y+"px";
		obj.style.left=x+"px";
		
		
		obj.onclick=removeStar;
		count++;
		if(count>20){
			alert("游戏结束！");
			window.clearInterval(dingshiqi);
			window.reload();
			
			
		}

		//显示在body中
		document.body.appendChild(obj);
		

	}
	//删除星星，count--
	function removeStar(){
		this.parentNode.removeChild(this);
		count--;
			
	}
	function stopGame(){
		alert("暂停游戏");
	}
	</script>
</head>
<body>
	
	<input type="button" value="开始游戏" onclick="startGame()">
	<input type="button" value="暂停游戏" onclick="stopGame()">
</body>
</html>
