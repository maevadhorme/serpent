# Mon premier jeu en Javascript
## TL;DR
> [SNAKE in JS](https://maevadhorme.github.io/serpent/)

## Ma démarche
Je souhaitais apprendre à faire un jeu

Je commence par faire mes recherches sur internet à savoir comment faire mon premier jeu, en mode nostalgie "le Snake" des ancien Nokia 3310. Un jeu relativement simple pour débuter, et je tombe sur Jhon Coder, apprendre à faire le "Jeu du serpent" en Javascript, dont voici l'url des cours Udemy : [https://www.udemy.com/](https://www.udemy.com/)

Je regarde ainsi les vidéo de John Coder à ce sujet.

1. Je les regarder entièrement, une première fois, pour me familiariser avec ce qui va être fait :

 - Cours en javascript
 -  Cours en html
 - Développer le jeu du serpent
 - Jouer au jeu du serpent

2.  Reprendre les vidéos et faire les exercices du cours :

**Coder l’Index.html**
```html
<!DOCTYPE  html>
<html>
	<head>
		<title>Jeu du Serpent</title>
		<script  src="script.js"></script>
	</head>
	<body>
	</body>
</html>
 ```
**Coder le script du jeu en Javascript (script.js)**
 ```bash
**Window Onload**
```
```js
window.onload = function(){
	var  canvasWidth = 900;
	var  canvasHeight = 600;
	var  blockSize = 30;
	var  ctx;
	var  delay = 100;
	var  xCoord = 0;
	var  yCoord = 0;
	var  snakee;
	var  applee;
	var  widthInBlocks = canvasWidth/blockSize;
	var  heightInBlocks = canvasHeight/blockSize;
	var  score;
	var  timeOut;
};
```
```bash
**Fonction refreshCanvas**
  ```
```js
function  refreshCanvas(){
	snakee.advance();
	if (snakee.checkCollision()){ 
		gameOver();
	}
	else {
		if (snakee.isEatingApple(applee)){
			score++;
			snakee.ateApple = true;
			do {
				applee.setNewPosition();
			} while(applee.isOnSnake(snakee));
		}
		ctx.clearRect(0,0,canvasWidth,canvasHeight);
		drawScore();
		snakee.draw();
		applee.draw();
		timeOut = setTimeout(refreshCanvas,delay);
	}
}
```
```bash
**Fonction Restart**
```
```js
function  restart(){
	snakee = new  Snake([[6,4],[5,4],[4,4],[3,4],[2,4]],"right");
	applee = new  Apple([10,10]);
	score = 0;
	clearTimeout(timeOut);
	refreshCanvas();
}
```
```bash
 **Fonction GameOver**
```
```js
function  gameOver(){
	ctx.save();
	ctx.font = "bold 70px sans-serif";
	ctx.fillStyle = "#000";
	ctx.textAlign = "center";
	ctx.textBaseline = "middle";
	ctx.strokeStyle = "white";
	ctx.lineWidth = 5;
	var  centreX = canvasWidth / 2;
	var  centreY = canvasHeight / 2;
	ctx.strokeText("Game Over", centreX, centreY - 180);
	ctx.fillText("Game Over", centreX, centreY - 180);
	ctx.font = "bold 30px sans-serif";
	ctx.strokeText("Appuyer sur la touche Espace pour rejouer", centreX, centreY - 120);
	ctx.fillText("Appuyer sur la touche Espace pour rejouer", centreX, centreY - 120);
	ctx.restore();
}
```
```bash
Et ainsi de suite pour chacune des fonctions nécessaires pour votre jeu !
Si je ne donne pas toutes les fonctions ici, c'est pour vous obligez à chercher aussi les réponses par vous même.
```
4.  Amusez-vous bien :)

> Written with [StackEdit](https://stackedit.io/).