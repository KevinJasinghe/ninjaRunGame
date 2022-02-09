//Kevin Jasinghe
// November 3rd, 2020
//Final Project Computer Science Class

//backround
var backStart = createSprite(200, 200);
backStart.setAnimation("city_1");
var back = createSprite(200, 200);
back.setAnimation("back");
var back2 = createSprite(600, 200);
back2.setAnimation("back");
//image to show at starting
var startNinja = createSprite(50, 50);
startNinja.setAnimation("ninjaJetFlame");
startNinja.scale = 0.5;
var startNinja2 = createSprite(350, 50);
startNinja2.setAnimation("ninjaFlameLeft");
startNinja2.scale = 0.5;
//User's character
var ninja = createSprite(60, 350);
ninja.setAnimation("ninja");
ninja.scale = 0.5;



//Enemy Character
var enemy = createSprite(1000, 325);

enemy.setAnimation("enemyNinja");
enemy.scale = 0.5;
//Display enemy on instructions
var enemy2 = createSprite(340, 315);
enemy2.setAnimation("enemyNinja");
enemy2.scale = 0.6;

//Shuriken
var shur = createSprite(75, 200);
shur.setAnimation("shuriken");
//display shuriken for instructions
var shur2 = createSprite(200, 200);
shur2.setAnimation("shuriken");

//coin
var coin = createSprite(200, 265);
coin.setAnimation("coin");
coin.scale = 0.5;
//coin for when ninja is hit
var coindrop = createSprite(200, 200);
coindrop.setAnimation("coin");
coindrop.scale = 0.5;

//Progress bar
var progBar = createSprite(200, 20);
progBar.setAnimation("progressBar");
progBar.scale = 3;

//Icon on the progress bar
var icon = createSprite(60, 20);
icon.setAnimation("icon");
icon.scale = 0.3;

//jump animation
var jump = createSprite(260, 315);
jump.setAnimation("ninjaRole");
jump.scale = 0.5;

//variable to control whether jetpack is on
var jet = 0;
//variables to set the animation of jetpack
var check = 0;
var check2 = 0;
//shuriken variables
var shurCooldown = -10;
var shurNumber = 5;
//decide if enemy is touching
var touchEnemy = "no";
//decode if shuriken is touching
var touchShur = "no";
//to dedice whether user's character is in air or not
var air = 0;
//fuel control variables
var fuel = 150;
var fuelRecharge = 0;
var rechargeTime = 0;
//Points
var score = 0;
//health
var health = 100;

//Screen
var screen = 1;
//to decide if user got a perferct score
var perfect = "yes";
//to show instructions
var instruc = "no";
//see whether intructions showing
var show = "no"


function drawScreen1(){
  textSize(40);
  fill("red");
  text("Welcome to", 80, 150);
  text("Ninja Blast", 90, 200);
  textSize(20);
  fill("lightGreen");
  text("by Kevin Jasinghe", 230, 380);
  fill("yellow");
  text("Press 'n' to continue", 100, 300);
  startNinja.visible = true;
  startNinja2.visible = true;
  backStart.visible = true;
  back.visible = false;
  coin.visible = false;
  jump.visible = false;
  icon.visible = false;
  progBar.visible = false;
  coindrop.visible = false;
  enemy2.visible = false;
  shur.visible = false;
  shur2.visible = false;
  ninja.visible = false;
}

function drawScreen2(){
  //showing images for instructions
  ninja.setAnimation("ninjaJetFlame");
  backStart.visible = false;
  startNinja.visible = false;
  startNinja2.visible = false;
  back.visible = true;
  ninja.visible = true;
  ninja.x = 60;
  ninja.y = 300;
  shur2.visible = true;
  shur2.y = 325;
  shur2.x = 170;
  shur2.scale = 0.75;
  jump.visible = true;
  enemy2.visible = true;
  coin.visible = true;
  //hovering over each image to show instructions
  if (World.mouseX < 115 && World.mouseX > 30 && World.mouseY < 370 && World.mouseY > 273) {
    textSize(30);
    fill("lightgreen");
    text("Jetpack", 140,80);
    textSize(20);
    fill("yellow");
    text("To activate the jetpack, press E", 30, 120);
    text("When the jetpack is activated and you", 30,150);
    text("press space, you will consume fuel and",30,180);
    text("fly through the air", 30, 210);
    text("Note that you only have a limit of 150 fuel", 30,240);
  } else if ((World.mouseX < 183 && World.mouseX > 155 && World.mouseY < 345 && World.mouseY > 312)) {
    textSize(30);
    fill("lightgreen");
    text("Shuriken", 140,80);
    textSize(20);
    fill("yellow");
    text("Press q to throw a shuriken", 30, 120);
    text("If you throw a shuriken at an enemy,", 30,150);
    text("the enemy will disappear",30,180);
    text("Note that you only have a limit of 5", 30, 210);
    text("shurikens", 30,240);
  } else if ((World.mouseX < 287 && World.mouseX > 238 && World.mouseY < 334 && World.mouseY > 280)) {
    textSize(30);
    fill("lightgreen");
    text("Jumping", 140,80);
    textSize(20);
    fill("yellow");
    text("Left click your mouse to jump", 30, 120);
    text("You can avoid enemies and catch coins", 30,150);
    text("when you jump. There is no limit on how",30,180);
    text("many times you can jump", 30, 210);
  } else if ((World.mouseX < 360 && World.mouseX > 337 && World.mouseY < 360 && World.mouseY > 292)) {
    textSize(30);
    fill("lightgreen");
    text("Enemy Ninja", 140,80);
    textSize(20);
    fill("yellow");
    text("These ninja's will appear throughout the", 30, 120);
    text("game. If you collide with one you wil", 30,150);
    text("lose a coin and lose some health",30,180);
    text("If your health drops below zero, you", 30, 210);
    text("will lose the game", 30,240);
  } else if ((World.mouseX < 205 && World.mouseX > 190 && World.mouseY < 270 && World.mouseY > 196)) {
     textSize(30);
    fill("lightgreen");
    text("Coin", 140,80);
    textSize(20);
    fill("yellow");
    text("Coins will appear throughout the", 30, 120);
    text("game. You can collect these coins to", 30,150);
    text("increase your score",30,180);
  } else {
    textSize(30);
    fill("lightgreen");
    text("Ninja Blast Mechanics", 50,80);
    textSize(16);
    fill("yellow");
    text("Press D to move left. Press A to move", 25, 120);
    text("right. Hover over each image to see the", 25,150);
    text("other different mechanics. You goal is to",25,180);
    text("reach the end while collecting as many coins as you", 25, 210);
    text("can", 25, 240);
    text("Press 'n' to play", 125, 390);
  }
}

function activatePieces() {
  //activating the pieces
  back.velocityX = -5;
  back2.velocityX = -5;
  back2.x = 600;
  back2.visible = true;
  enemy.velocityX = -5;
  enemy.visible = true;
  enemy.setAnimation("enemyNinja");
  enemy.x = 1000;
  coin.velocityX = -5;
  coin.visible = true;
  coin.x = 500;
  shur.scale = 0.5;
  shur.y = -20;
  shur.x = 400;
  shur.visible = true;
  progBar.visible = true;
  icon.visible = true;
  icon.x = 60;
  shur2.visible = false;
  enemy2.visible = false;
  jump.visible = false;
  ninja.y = 350;
  ninja.visible = true;
  icon.velocityX = 0.2;
  playSound("sound://category_loops/pulsating_discovery_loop1.mp3", false);
}
function playGame() {
  drawSprites();
  //Scrolling Backround
  if (back.x < -200) {
    back.x = 600;
  }
  if (back2.x < -200) {
    back2.x = 600;
  }
  //move ninja faster left
  if (keyWentDown("d")) {
    ninja.velocityX = 5;
  }
  //move ninja faster right
  if (keyWentDown("a")) {
    ninja.velocityX = -5;
  }
  //prevent ninja from going off screen
  if (ninja.x < 50) {
    ninja.x = 60;
    ninja.velocityX = 0;
  }
  if (ninja.x > 370) {
    ninja.x = 370;
    ninja.velocityX = -2;
  }
  if (ninja.y < 30) {
    ninja.y = 30;
  }
  //ninja jump
  if ((mouseDown("leftButton") && jet != 1) && air == 0) {
    ninja.setAnimation("ninjaRole");
    ninja.y = 290;
    ninja.rotationSpeed = 12;
    ninja.velocityY = -10;
    ninja.velocityX = 2;
    air = 1;
  }
  if (ninja.y < 210 && jet !=1 && air == 1) {
    ninja.velocityY = 5;
    ninja.velocityX = 0;
  }
  
  
  //Jetpack game mechanics
  check = 0;
  check2 = 0;
  //turn on jetpack
  if (keyWentDown("e") && jet == 0 && air == 0 && fuel > 0) {
    ninja.y = 200;
    ninja.setAnimation("ninjaJetFlame");
    ninja.rotation = 1;
    ninja.rotationSpeed = 0;
    jet++;
    check2 = 1;
  }
  //move up with the jetpack
  if (keyDown("space") && jet == 1 && fuel > 0) {
    ninja.setAnimation("ninjaJetFlame");
    ninja.y = ninja.y + -8;
    check = 1;
    fuel = fuel - 1;
  }
  //gravity pulls down
  if (jet == 1 && check == 0) {
    ninja.setAnimation("ninjaJetnoFlame");
    ninja.y = ninja.y + 4;
  }
  //Jetpack fuel
  if (fuel > 0 && instruc == "no") {
    fill("yellow");
    text("Fuel Remaining: " + fuel, 15, 80);
  }
  
  //change ninja to running animation when on ground
  if (ninja.y > 300) {
    jet = 0;
    air = 0;
    ninja.velocityY = 0;
    ninja.setAnimation("ninja");
    ninja.rotation = 0;
    ninja.rotationSpeed = 0;
    ninja.y = 350;
  }
  
  
  //Cooldown on throwing shurikens and how many shurikens remain
  if (World.seconds > shurCooldown + 2 && shurNumber > 0 && keyWentDown("q")) {
    shur.rotationSpeed = 22;
    shur.velocityX = 10;
    shurCooldown = World.seconds;
    shur.x = ninja.x;
    shur.y = ninja.y;
    shur.visible = true;
    shurNumber--;
    playSound("sound://category_transition/ball_throw_bowl_12.mp3", false);
  }
  if (shur.x > 410) {
    shur.y = 50;
  }
  
  //Coin locations
  if (coin.x < -5) {
    coin.x = 450;
    coin.y = randomNumber(100, 370);
    perfect = "no";
  }
  if (ninja.isTouching(coin)) {
    score++;
    coin.x = 450;
    coin.y = randomNumber(100, 370);
    playSound("sound://category_bell/notification_4.mp3", false);
  }
 
  //Enemy Ninja location
  if (enemy.x < -5) {
    enemy.setAnimation("enemyNinja");
    enemy.x = randomNumber(1000, 1500 );
    enemy.y = 325;
    touchEnemy="no";
    touchShur = "no";
  }
  //does swing anmiation and loses coin if ninja collides with enemy
  if (ninja.overlap(enemy)&& touchEnemy=="no" && touchShur == "no" && ninja.y > 300 && ninja.x <= enemy.x) {
    score--;  
    enemy.setAnimation("enemyNinjaSwing");
    playSound("sound://category_hits/8bit_splat.mp3", false);
    touchEnemy="yes";
    coindrop.visible = true;
    coindrop.x = ninja.x;
    coindrop.y = ninja.y;
    coindrop.velocityX = -5;
    coindrop.velocityY = 1;
    perfect = "no";
    health = health - randomNumber(25, 50);
  }
  //gets rid of enemy ninja if shuriken colides with enemy
  if (shur.overlap(enemy) && touchShur == "no") {
    enemy.setAnimation("poof");
    shur.visible = false;
    shur.y = 100;
    touchShur = "yes";
    playSound("sound://category_poof/puzzle_game_click_fire_poof_04.mp3", false);
  }
  
  //Showing the shuriken number and score
  if (screen == 4 && instruc == "no") {
    fill("yellow");
    text("Coins Collected " + score, 15, 50);
    fill("yellow");
    text("Shurikens Remaing: " + shurNumber, 15, 65);
    fill("yellow");
    text("Health " + health, 325, 50);
  }
  //if you lose all your health game over
  if (health <= 0) {
    screen = 0;
  }
  //when you reach the end game over
  if (icon.x >= 322) {
    screen = 0;
  }
}
function gameOver() {
  //stopping music
  stopSound("sound://category_loops/pulsating_discovery_loop1.mp3");
  //hiding all images
  back.x = 200;
  back2.visible = false;
  back.velocityX = 0;
  back2.velocityX = 0;
  ninja.visible = false;
  enemy.visible = false;
  enemy.x = 1000;
  coin.visible = false;
  coindrop.visible = false;
  coin.y = 800;
  icon.visible = false;
  progBar.visible = false;
  background("black");
  //if you got all coins, perfect win, then normal win, then loss
  if (perfect == "yes" && icon.x >= 322) {
    fill("yellow");
    textSize(25);
    text("You have reached the end!", 35, 100);
    text("Congratulations! You got a perfect", 35, 150);
    text("perfect score", 0, 15);
  } else if ((perfect == "no" && icon.x >= 322)) {
    fill("yellow");
    textSize(25);
    text("You have reached the end!", 35, 100);
    text("You got a score of " + score, 35, 150);
  } else if ((health <= 0)) {
    fill("red");
    textSize(25);
    text("You lost too many health points", 35, 100);
    text("and died!", 35, 125);
    text("You got a score of " + score, 30, 240);
  }
  fill("lightgreen");
  textSize(35);
  text("Press 'h' to play again", 25, 370);
  //reseting variables for play again
  if (keyWentDown("h")) {
    screen = 1;
    fuel = 150;
    shurNumber = 5;
    score = 0;
    health = 100;
  }
}
function draw() {
  drawSprites();
  if (keyWentDown("n")) {
    screen++;
  }
  if (screen == 0) {
    gameOver();
  } else if (screen == 1) {
    drawScreen1();
  } else if (screen == 2) {
    drawScreen2();
  } else if (screen == 3) {
    activatePieces();
    screen++;
  } else {
    playGame();
  }
}
