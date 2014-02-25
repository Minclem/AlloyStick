
	<!doctype html>
	<html lang="en">
	<head>
		<meta charset="UTF-8">
		<title>骨骼动画Demo</title>
		<style type="text/css" media="screen">
			html, body { background-color: #666666;}
			body { margin:0; padding:0; overflow:hidden; }
		</style>

	</head>
	<body>
		<canvas id="canvas" width="800px" height="600px">抱歉，你的浏览器不支持canvas，建议你使用Chrome浏览器，杜绝360浏览器。</canvas>
		<img src="./data/texture.png" id="xiaoxiaoImg" style="display:none;">
	</body>

	<!-- 注意这里的js加载顺序，先加载游戏引擎，再加载资源js-->
	<script src='./js/alloystick_v0.35h.js'></script>
	<script src='./data/xx_resource.js'></script>
	<script>
	var demoApp = function(){
		
		var canvas = document.getElementById('canvas'),
			textureImg = document.getElementById('xiaoxiaoImg');

		var stage = new alloyge.Stage(canvas.getContext('2d'));
		var	player = new alloysk.Armature('xiaoxiao',textureImg);

		// animationName ,totalFrames,transitionFrame,isLoop
		player.playTo('roll',100,15,true);
		player.setPos(300,300);	
		player.setEaseType(false);

		stage.addObj(player);
		// 启动FPS监听器 (辅助功能 非必须)
		alloyge.monitorFPS(stage);  

		// 开始场景里的动画，并且可以传入callback循环调用
		stage.start();

	}

	window.onload = demoApp;
		
	</script>

	</html>