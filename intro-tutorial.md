# Science Oxford - Introduction to MakeCode Arcade

## Introduction @showdialog

This tutorial will help you to create a game.

In this game, you will have a player character, which will be chased by an enemy character.

The longer you manage to run away, the higher your score!

During the tutorial, you will only have a few blocks available to use, but there are lots of other things you can add in once you are finished.



## Choose a theme

Where do you want your game to be set?

Click into the ``||scene:Scene||`` menu, find the ``||scene:set background image||`` block, and drag-and-drop it inside the ``||loops:on start||`` loop.

Click the grey box in the ``||scene:set background image||`` block to choose your background image. You can draw your own, or click into the Gallery to pick a background.

Click Done on the bottom right to get back to the code editor and see your chosen picture in the game.

When you have finished, click Next on the tutorial to see the next instruction.

```blocks
scene.setBackgroundImage(img`.`)
```



## Choose a player character

Who, or what, do you want your player character to be?

Click into the ``||sprites:Sprites||`` menu, find the ``||variables: set mySprite to||`` block, and drag-and-drop it inside the ``||loops:on start||`` loop.

Click the grey box in the ``||variables: set mySprite to||`` block to choose your character's image. You can draw your own, or click into the Gallery to pick one.

```blocks
scene.setBackgroundImage(img`.`)
let mySprite = sprites.create(img`.`, SpriteKind.Player)
```


## Adjust your player character

Your new character starts the game right in the middle of the screen - this might not be the best place to start.

Click into the ``||sprites:Sprites||`` menu, find the ``||sprites:set mySprite position to||`` block, and drag-and-drop it inside the ``||loops:on start||`` loop.

Click on one of the numbers in the ``||sprites:set mySprite position to||`` block to choose the starting position of your character.

~hint What are x and y?
 - x and y are called co-ordinates.
 - x is left and right on the screen.
 - y is up and down on the screen.
 - the bigger x is, the further left your character will start the game.
 - the bigger y is, the further down your character will start the game.
hint~

~hint Optional extra coding - rename your sprites
 - your character is currently called 'mySprite' - you can rename it to something more memorable.
 - choose one of the blocks that includes the words 'mySprite' and click the small arrow next to the name.
 - click 'rename variable' and set a new name.
 - use one word with no spaces, or the game will get confused!
 - all of the blocks that effect your character will change to use the new name
hint~

```blocks
scene.setBackgroundImage(img`.`)
let mySprite = sprites.create(img`.`, SpriteKind.Player)
mySprite.setPosition(20, 100)
```


## Move your character

Click into the ``||controller:Controller||`` menu, find the ``||controller:move mySprite with buttons||`` block, and drag-and-drop it inside the ``||loops:on start||`` loop.

~hint If you renamed your character earlier
 - click the small arrow next to 'mySprite', and choose the name you chose from the list.
 - Do not 'rename variable' again, pick it from the list.
hint~

```blocks
scene.setBackgroundImage(img`.`)
let mySprite = sprites.create(img`.`, SpriteKind.Player)
mySprite.setPosition(20, 100)
controller.moveSprite(mySprite)
```


## Testing time! @showdialog

On the small game window, click the 'full screen' button (the square picture).
![Full screen button](https://raw.githubusercontent.com/Isioviel/arcade-introductiontutorial/a44665c29cc484ead76de9241f5d2919607050e9/images/fullscreen.PNG)

Practice controlling your player character, then click the same button to get back to the editor.

If something goes wrong, you need to do some debugging!

Check the code for disconnected blocks, or exclamation marks. If you need help, ask your workshop leader.


## Add an enemy

Who, or what, do you want your enemy character to be?

Click into the ``||sprites:Sprites||`` menu, find another ``||variables: set mySprite to||`` block, and drag-and-drop it inside the ``||loops:on start||`` loop.

The end of this block, says ``||sprites:of kind Player||``. Click the small arrow next to ``||sprites:Player||``, and change it to ``||sprites:Enemy||``.

Like you did for your player character, create or choose an image for your enemy.

```blocks
scene.setBackgroundImage(img`.`)
let mySprite = sprites.create(img`.`, SpriteKind.Player)
mySprite.setPosition(20, 100)
controller.moveSprite(mySprite)
let mySprite2 = sprites.create(img`.`, SpriteKind.Enemy)
```


## Set the enemy's position

Where should the enemy start the game?

Click into the ``||sprites:Sprites||`` menu, find another ``||sprites: set mySprite position to||`` block, and drag-and-drop it inside the ``||loops:on start||`` loop.

Click the small arrow next to ``||variables:mySprite||`` and make sure that it is the name of your enemy - this is probably ``||variables:mySprite2||``.

Set enemy start position - remember that it will start to chase you soon, so if it starts too close to the player, the game will be very difficult!

```blocks
scene.setBackgroundImage(img`.`)
let mySprite = sprites.create(img`.`, SpriteKind.Player)
mySprite.setPosition(20, 100)
controller.moveSprite(mySprite)
let mySprite2 = sprites.create(img`.`, SpriteKind.Enemy)
mySprite.setPosition(140, 100)
```


## Set the enemy to follow your player

Click into the ``||sprites:Sprites||`` menu, find the ``||sprites: set myEnemy follow mySprite||`` block, and drag-and-drop it inside the ``||loops:on start||`` loop.

Click the small arrow next to ``||variables:myEnemy||`` and change it to the name of your enemy - this is probably ``||variables:mySprite2||``.

~hint If you renamed your character earlier
 - click the small arrow next to 'mySprite', and choose the name you chose from the list.
 - Do not 'rename variable' again, pick it from the list.
hint~

```blocks
scene.setBackgroundImage(img`.`)
let mySprite = sprites.create(img`.`, SpriteKind.Player)
mySprite.setPosition(20, 100)
controller.moveSprite(mySprite)
let mySprite2 = sprites.create(img`.`, SpriteKind.Enemy)
mySprite.setPosition(140, 100)
mySprite2.follow(mySprite)
```


## Testing time! @showdialog

On the small game window, click the 'full screen' button (the square picture).
![Full screen button](https://raw.githubusercontent.com/Isioviel/arcade-introductiontutorial/a44665c29cc484ead76de9241f5d2919607050e9/images/fullscreen.PNG)

Practice running away from the enemy, then click the same button to get back to the editor.

If something goes wrong, you need to do some debugging!

Check the code for disconnected blocks, or exclamation marks. If you need help, ask your workshop leader.


## Slow the enemy down

The enemy is quick! It will be very difficult to win the game at the moment.

Click the ``||sprites:+||`` symbol at the end of the ``||sprites:follow||`` block, and reduce the speed of the enemy.

Test out the game, and edit the speed until you are happy with it.

```blocks
scene.setBackgroundImage(img`.`)
let mySprite = sprites.create(img`.`, SpriteKind.Player)
mySprite.setPosition(20, 100)
controller.moveSprite(mySprite)
let mySprite2 = sprites.create(img`.`, SpriteKind.Enemy)
mySprite.setPosition(140, 100)
mySprite2.follow(mySprite, 50)
```


## Add scoring

Now that it is possible to run away from the enemy, you can keep track of the score.

To do this, we need to make a new section of code.

Click the ``||game:Game||`` menu, and find the ``||game:on game update every 500ms||`` block. Drag-and-drop it onto an empty space on the screen.

Click the ``||info:Info||`` menu, find the ``||info:change score by 1||`` block, and drag-and-drop it inside your new ``||game:on game update||`` loop.

Every half a second, you get a point! Test out you game, then decide how often you want to get points, and how many points you want to get.

~hint What to change?
 - to change how often you get points, edit the number in the 'on game update' loop
 - to change how many points you get each time, edit the number in the 'change score by' block
hint~

```blocks
game.onUpdateInterval(500, function () {
    info.changeScoreBy(1)
})
```


## End the game if the enemy catches you

At the moment, the game runs forever. You are going to change it so that if the enemy catches you, the game ends.

Click the ``||sprites:Sprites||`` menu, and choose the ``||sprites:on sprite of kind Player overlaps with sprite of kind Player||`` block. Drag-and-drop it onto an empty space on the screen.

Click the **second** ``||sprites:Player||`` option, and change it to ``||sprites:Enemy||``.

The block now controls what happens when your player sprite overlaps (or touches) an enemy sprite.

Click the ``||game:Game||`` menu, and find ``||game:game over||``. Drag-and-drop this into the ``||sprites:overlap||`` block, and toggle it to **LOSE**.

```blocks
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    game.gameOver(false)
})
```


## Testing time! @showdialog

On the small game window, click the 'full screen' button (the square picture).
![Full screen button](https://raw.githubusercontent.com/Isioviel/arcade-introductiontutorial/a44665c29cc484ead76de9241f5d2919607050e9/images/fullscreen.PNG)

Run away from the enemy as long as you can, then let it catch you. What score do you get?

If something goes wrong, you need to do some debugging!

Check the code for disconnected blocks, or exclamation marks. If you need help, ask your workshop leader.


## Create a start and end to your game

You now have a working game, well done!

Spend some time adding to the game so far, by changing what happens at the start, and when the game ends.

Look through the ``||game:Game||`` and ``||music:Music||`` menus for some ideas.

For example:
- Add a ``||game:Splash||`` block to your ``||loops:on start||`` loop, to show a starting screen.
- Add a ``||game:use effect confetti||`` block to your ``||sprites:overlap||`` loop, after the game ends.

If you are not sure what to do, ask your workshop leader for some ideas.

```ghost
let mySprite = sprites.create(img`.`, SpriteKind.Player)
mySprite.setStayInScreen(true)
game.setGameOverEffect(true, effects.confetti)
game.setGameOverPlayable(true, music.melodyPlayable(music.powerUp), false)
game.setGameOverMessage(true, "GAME OVER!")
game.splash("")
music.play(music.stringPlayable("- - - - - - - - ", 120), music.PlaybackMode.UntilDone)
music.play(music.melodyPlayable(music.baDing), music.PlaybackMode.UntilDone)
music.play(music.createSoundEffect(WaveShape.Sine, 5000, 0, 255, 0, 500, SoundExpressionEffect.None, InterpolationCurve.Linear), music.PlaybackMode.UntilDone)
```


## Final testing! @showdialog

When you click **Done** on the tutorial, you will get access to all of the blocks in MakeCode.

If you would like to see the other options, and try some more complex ideas, click Done.

If you would like to see editing your game using the blocks we have given you so far, do not click Done.


## Continue...

If you would like access to more blocks, click Done to exit the tutorial.