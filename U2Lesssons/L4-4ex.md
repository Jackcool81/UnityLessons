# Lesson 4-4 Exercise
In this exercise we will create character input and collision functionality. So have your "Level 1" scene opened up.

## Exercise 4.4.1
---
First, lets create a player movement script. We will use **if statements** in the Update method will check if the user is holding down the move key using the **Input** Module. If so then we will apply force using **AddForce()** to the player object's 2D rigidbody.

1. Create a new C# script and call it `PlayerMovement`. Open the file and inside, declare 3 variables:

   * A private `Rigidbody2D` called rb

   * A public `float` called speed

   * A public `float` called jumpPower

2. In the `Start()` method, make sure that you intialize the **rb** variable to the Rigidbody2D component from the "this" game object. (use `GetComponent<T>()`)

3. Inside the `Update()` method, add two **if statements** checking if the user Inputs a Key (use `Input.GetKey(<x>)`, where `<x>` can be replaced with a KeyCode of your choice `KeyCode.A`, `KeyCode.RightArrow`, `KeyCode.Space`, etc) 
   * Inside each if statement we will add force on the rigidbody. You can do this by calling `AddForce()` on the **rb** variable, the first parameter will be "direction" (e.g. `vector3.right`) times **speed**, and the second is `ForceMode2D.Impulse` to make sure force is done immediately.

## Exercise 4.4.2
---
To have the player jump, we will need to make sure the player is grounded using trigger collision methods.

 1. Declare a private bool called isGrounded. 
 2. Create a public void `OnTriggerEnter2D()` and `OnTriggerExit2D()`
    *  For the `OnTriggerEnter2D()` function turn the isGrounded to true 
    *  For the `OnTriggerExit2D()`  function turn the isGrounded to false.

Below the movement code in `Update()`, we will add the jump key. 

1. Create an **if-statement** which checks if the jump key (e.g. `Spacebar`) is pressed and if isGrounded is true. 
   * If they are both true, add a force to the rigidbody (make sure to use `ForceMode2D.Impulse` to make the jump immediate).

## Exercise 4.4.3
---
Lets also make use of the effectors we just learned about by creating a bool using the Buoyancy Component. This will make it so the player will float. 

1. Create a new 2D Square, and assign it's sprite to whatever you desire 
2. Add a 2D Box Collider to the GameObject, making sure that the effector box is checked as well as the on trigger method
3. Add the Buoyancy Component to this GameObject

## Exercise 4.4.4
---
Add your character to your "Level 1" scene that you made in the previous lesson's exercise (4-3 Exercise). Make sure the player works correctly and that it can navigate along the level.