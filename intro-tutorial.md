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

When you have chosen, click Next to see the next instruction.

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

Click into the ``||sprites:Sprites||`` menu, find the ``||sprites: set mySprite position to||`` block, and drag-and-drop it inside the ``||loops:on start||`` loop.

Click on one of the numbers in the ``||sprites: set mySprite position to||`` block to choose the starting position of your character.

~hint What are x and y?
 - x and y are called co-ordinates.
 - x is left and right on the screen.
 - y is up and down on the screen.
 - the bigger x is, the further left your character will start the game.
 - the bigger y is, the further down your character will start the game.
hint~

**Optional**: your character is currently called 'mySprite' - you can rename it if you like.

Choose one of the blocks that includes ``||variables:mySprite||`` and click the small arrow next to the name.

Click ``||variables:rename variable||`` and set a new name - just pick one word with no spaces, or the game will get confused. All of the blocks that effect your character will change.

```blocks
scene.setBackgroundImage(img`.`)
let mySprite = sprites.create(img`.`, SpriteKind.Player)
mySprite.setPosition(20, 100)
```


## Move your character

Click into the ``||controller:Controller||`` menu, find the ``||controller: move mySprite with buttons||`` block, and drag-and-drop it inside the ``||loops:on start||`` loop.

**If you renamed your character earlier** click the small arrow next to ``||variables:mySprite||``, and choose the name you chose from the list. **Do not** ``||variables:rename variable||`` again, pick it from the list.

```blocks
scene.setBackgroundImage(img`.`)
let mySprite = sprites.create(img`.`, SpriteKind.Player)
mySprite.setPosition(20, 100)
controller.moveSprite(mySprite)
```


## Testing time! @showdialog

This is a good place to stop and test your game.

On the small game window, click the 'full screen' button (the square picture).

Practice controlling your player character, then click the same button to get back to the editor.

If something goes wrong, you need to do some debugging!

Check the code for any disconnected blocks, or any exclamation marks. If you need help, ask your workshop leader.


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

**If you renamed your character earlier** click the small arrow next to ``||variables:mySprite||``, and choose the name you chose from the list. **Do not** ``||variables:rename variable||`` again, pick it from the list.

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

This is a good place to stop and test your game.

On the small game window, click the 'full screen' button (the square picture).

Practice running away from the enemy, then click the same button to get back to the editor.

If something goes wrong, you need to do some debugging!

Check the code for any disconnected blocks, or any exclamation marks. If you need help, ask your workshop leader.


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
 - to change how many points you get each time, edit the numebr in the 'change score by' block
hint~

```blocks
game.onUpdateInterval(500, function () {
    info.changeScoreBy(1)
})
```

