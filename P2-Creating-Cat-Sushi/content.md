---
title: "Creating our character and obstacles"
slug: creating-cat-sushi
---

**Adding Artwork**

<!--TODO: ADD ART PARK LINK-->
To get started, [download our art pack](). Add the art pack you just downloaded to your SpriteBuilder project by first unpacking the archive, then drag the folder onto the File View in SpriteBuilder (lower left area where you can see files & folders):

<!--MAKE THIS A GIF?-->
![](./SpriteBuilder_Assets.png)

**Create the Character**

Now that we have art, create a new *CCB-File* (File > New > File) named `Character.ccb` of type `Sprite`:

![](./SpriteBuilder_CreateNewSprite.png)

Set its *sprite frame property* to `assets/character1.png`.

Now set the *anchor point* to `(1, 0)` so that it is positioned relative to its bottom-right corner. We'll see how this makes things easier when we setup the *MainScene*. When you're done, it should look like this:

![](./SpriteBuilder_Cattributes.png)

We also want to set its *custom class property* to `Character` so that it looks for `Character.swift` when we create it later.

![](./SpriteBuilder_ChangeCustomClass.png)

Now it's time to create the obstacles!

**Create an Obstacle Piece**

Create a *CCB-File* named `Piece.ccb` of type `CCNode`. We want to create a CCNode so that we can have more control over its animations later on in the tutorial.

Set the root nodes *content size* to `(105, 60)` and its *anchor point* to `(0.5, 0)`. These properties will make it easy for us to build a stack of sushi from code. You should also set its *custom class* to `Piece`, just like you did for `Character.ccb` above.

Drag in `roll.png` from the your assets as a child of the root. Also drag in two `chopstick.png` from the resources as a child of *roll*. Name one `right` and the other `left`.

Your timeline should look like this:

![](./SpriteBuilder_Piece_Messy.png)

It's time to position our sprites correctly! Set the roll's *anchor point* to `(0, 0)`. This should position it correctly within the root node's bounding box.

![](./SpriteBuilder_Piece_Roll.png)


Now select the left chopstick. Set its *position* to `(0, 50)` and its *anchor point* to `(1, 0.5)`.

![](./SpriteBuilder_Piece_Left.png)

Also create a `doc root var` code connection to `left` so that we can access it in code later.

![](./SpriteBuilder_Piece_Left_CC.png)

Finally let's setup the right chopstick. Set its *reference corner* to the `bottom-right`. This changes which corner its *position* is based upon. Set its *position* to `(0, 50)`. Also set its *anchor point* to `(0, 0.5)` and check *Flip X*.

![](./SpriteBuilder_Piece_Right.png)

Simply flipping the chopstick sprite allows us to use the same asset for both chopsticks and save a little bit of memory. Now create a `doc root var` code connection to `right`.

The obstacle should now look like this:

![](./SpriteBuilder_Piece_Finish.png)

The last thing we need to do is uncheck the *Visible* box of both chopsticks. We'll programmatically turn branches on/off while generating the level.

Let's move on to setting up the *MainScene* in the next step!
