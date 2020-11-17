# Movement

This shows how to make a movement script.

Start off by creating a 3D Project as this tutorial will be using 3D dimensions and references

## 1. Create a new scene

Start by creaing a new scene called `Movement`.

You will need shapes in place of game objects and models, to find shapes, right click the `Hierarchy` tab, look for `3D objects` and find `Cube`, click that to add it to your scene

Then scale the cube up using the `Scale tool` by using the R key and then stretching the length and width of the cube with the blue and red boxes. Scale it up to a size you think is appropriate for your scene.

Using the same method as above, add a 3D Capsule and call it `Player`.

## 2. Create a script 

To create a script in Unity you will need to right click the the section under the main screen where it shows your assets and then click `Create`, you will be given a drop down menu where there will be an option that says `C# Script`, click that to start create your script and name it `Player_Movement`

Now this code will allow you to move using one of Unity's character controllers, but first you have to reference it, you will also need to tell Unity how fast you want your character to move. First, you have to make it a `Public` variable as you want to be able to change it in the `inspector tab` of Unity. Since you want to see the character controller you write it as `public CharacterController controller;` which references the fuction we will be using and the semi colon just means that this code is complete.

Press enter to start a new line and make another public variable, this one will say `public float speed = 12f;`. The "12f" means "12 float", a float in Unity is a unit of numeric value that will be used to judge the speed of your chararacter. Your code should look like this
```
public CharacterController controller;
public float speed = 12f;
``` 

Next you will want to assign directions and keys for each direction you want your character to move in. 

Since we will be using Unity’s character controller, you just reference the axis. First go under `void Update() and inside the curly brackets write:
```
`float x = Input.GetAxis(“Horizontal”);`
```

This allows you to left and right, as those directions are linked to the ‘X’ axis. 
To move forward and backward, you write the same code as above, but replace the “float x” with a “float z” and (“Horizontal”); with (“Vertical”);

Unity’s built in key binding have: A, d, left arrow key and right arrow key under “Horizontal”. Which is why we bound those keys for left and right movement.
They also have the: W, s, up arrow key and down arrow key under “Vertical”. Which is why we bound those keys for forward and backward movement. You should have the below in your code.
```
 float x = Input.GetAxis("Horizontal");
 float z = Input.GetAxis("Vertical");
```

Then write
```
`Vector3 move = transform.right * x + transform.forward * z;
```

`Vector3 move` is us telling Unity that we want the gameobject that this script is attached too to move in the axis we have referenced. “transform.right * x” and transform.forward * z” applies what we have written above.
To finish off our script, we write
```
controller.SimpleMove(move * speed)
```
“Controller” is the type of function we are using. “SimpleMove” applies physics to our object while “move * speed” is just using the numerical amount we set our speed variable at as the movement speed of our character. Our finished script inside the update function should look like this
```
void Update()
    {

        //Gets inputs for both X and Z axis and sets them on WASD or arrow keys
        float x = Input.GetAxis("Horizontal");
        float z = Input.GetAxis("Vertical");

        Vector3 move = transform.right * x + transform.forward * z;

        controller.SimpleMove(move * speed);
    }
```

