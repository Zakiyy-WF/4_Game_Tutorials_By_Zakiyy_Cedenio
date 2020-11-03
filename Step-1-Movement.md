# Movement

This shows how to make a movement script.

Start off by creating a 3D Project as this tutorial will be using 3D dimensions and references

## 1. Create a new scene

Start by creaing a new scene called `Movement`.

You will need shapes in place of game objects and models, to find shapes, right click the `Hierarchy` tab, look for `3D objects` and find `Cube`, click that to add it to your scene

Then scale the cube up using the `Scale tool` by using the R key and then stretching the length and width of the cube with the blue and red boxes. Scale it up to a size you think is appropriate for your scene.

Using the same method as above, add a 3D Capsule and call it `Player`.

## 2. Create a script 

To create a script in Unity you will need to right click the the section under the main screen where it shows you assets and then click `Create`, you will be given a drop down menu where there will be an option that says `C# Script`, click that to start create your script and name it `Player_Movement`

Now this code will allow you to move using one of Unity's character controllers, but first you have to reference it, to do so, right above where it says `void Start` write out ``public CharacterController controller;``. This will reference the character controller that we will be using later down the line.

Press enter to make a new line and wright `public float speed = 12f;`, this tells Unity how fast you want your character to move, as the "12f" means "12 float", a float in Unity is a unit of numeric value that will be used to judge the speed of your chararacter.
