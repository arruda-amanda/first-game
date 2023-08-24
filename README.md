# Dog game

<div>
    <a href="https://www.loom.com/share/f9f7c01fdedd497eaf172be22252f000">
      <p>p5.js | Dog game</p>
    </a>
    <a href="https://www.loom.com/share/f9f7c01fdedd497eaf172be22252f000">
      <img style="max-width:300px;" src="https://cdn.loom.com/sessions/thumbnails/f9f7c01fdedd497eaf172be22252f000-1692852246940-with-play.gif">
    </a>
  </div>

# p5js library
  This is the initial game I created using JavaScript, utilizing the p5.js library from p5js.org. P5.js serves as a JavaScript framework for artistic coding, aiming to democratize and foster inclusivity in coding for everyone. Additionally, I employed CSS and HTML to handle the visual components of the game.

# #1
  To begin, I established the canvas as the backdrop for the game's activities and uploaded the necessary images essential for the game's functionality.

```
function setup() {
  createCanvas(576, 576);
  dog = loadImage('dog.png');
  grass = loadImage('grass.png');
}
```

# #2
  Afterwards, I proceeded to illustrate all the components that are intended to emerge within the game, simultaneously positioning them accurately on the canvas.

 ```
  background(173,216,230);
  for(let i = 0; i < 9; i++){
    for(let j = 0; j < 9; j++){
     image(grass, tamanho * i, tamanho * j, tamanho, tamanho);   
    }
  }
  image(dog, andarX, andarY, tamanho, tamanho);
 ```

# #3
  To enable seamless movement, I crafted a function responsible for instructing the keyboard about the ensuing actions upon pressing a key. Furthermore, I instituted limitations on the movements to ensure the icon's visibility by preventing its vanishing when traversing the boundaries of the canvas.

```
function draw() {
  if(andarX < 0){
    andarX = 0
  }
  if(andarY < 0){
    andarY = 0
  }
  if(andarX > tamanho * 8){
    andarX = tamanho * 8
  }
  if(andarY > tamanho * 8){
    andarY = tamanho * 8
  }


function keyPressed(){
  if(keyIsDown(UP_ARROW)){
    andarY -= velocidade
  }
  if(keyIsDown(DOWN_ARROW)){
    andarY += velocidade
  }
  if(keyIsDown(LEFT_ARROW)){
    andarX -= velocidade
  }
  if(keyIsDown(RIGHT_ARROW)){
    andarX += velocidade
  }
}
```

# #4 
  Upon engaging in gameplay for a brief period, one eventually encounters the conclusion. As a response, I designed a message that extends congratulations upon reaching this endpoint, explicitly declaring victory.

 ```
  if(andarX === tamanho * 8 && andarY === tamanho *8){
      rect(160, 160, 256, 256)
    textSize(35)
      text("Vitória!!", 220, 300)
      restart = createButton('Reiniciar')
      restart.mousePressed(reset)
      noLoop()              
     }
}
```
# #5
  Should you opt to initiate the game anew, I devised a reset function primed to trigger upon clicking the restart button. This button materializes as soon as the game culminates, affording you the opportunity to swiftly return to the game's inception point.

  ```
function reset(){
  andarX = 0
  andarY = 0
  restart.remove()
  loop()
}
```
# The End

  Crafting this game from the ground up proved to be an enjoyable and enlightening journey, especially considering my prior lack of exposure to coding or development. P5.js offers an insightful glimpse into the world of coding and its operational mechanisms, making it accessible for newcomers. If you're inclined to experiment or even partake in the game itself, feel free to explore it through the provided link below.

<div>
   <a href="https://editor.p5js.org/amanda.arruda/full/Y-rQPgAUn">
      <p>Play Dog game!</p>
    </a>
</div>
