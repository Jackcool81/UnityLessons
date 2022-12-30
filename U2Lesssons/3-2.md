# Lesson 3-2: Stay in the Zone 
The goal of the game is for the player to have the player run around the level and try to get into the spherical zone before time runs out. As the game goes on, the zone becomes smaller and the time gets shorter. The game ends when the player cannot reach the zone in time.

![](https://cdn.discordapp.com/attachments/984881858758193182/1051964740185899249/ezgif.com-gif-maker22.gif)

### What you will use **Triggers and Colliders!**
---

For this exercise, we will be working on triggers and colliders to build up the Stay in the Zone mini-game. *Refer to Lesson 2-7 for more information on Triggers and Colliders.* 

*General Code Structure*, Triggers and Colliders are just special **methods** that get called from unity whenever two objects with colliders interact with eachother. 
```csharp
    private void OnCollisionEnter(Collision other){
        //checks if the other object is a player object
        if(other.collider.CompareTag("Player")){
            //sets the player Parent to this object
            other.transform.SetParent(this.transform);
        }
    }

    private void OnTriggerEnter(Collider other){
        if(other.CompareTag("Player")){
            //sets this objects parent to the Player
            this.transform.SetParent(other.transform);
        }
    }

```

## Check Trigger Zone
---

The main objective for the player is to enter a zone before time runs out. To accomplish this, we will go into the **ZoneScript** and add the OnTrigger methods. Here is what each will need to accomplish:

* In the **OnTriggerEnter**: Check if what entered the zone trigger was the player object (use other.CompareTag("Player"))
     * If the player object has entered the zone, 
        1. Set the boolean **playerInside** to true 
        2. Call **SetZoneHelper()** with the parameter of true
        3. Set the **timer** equal to **stayTimer**.

* In the **OnTriggerStay()**: Create an if statement that checks if the **playerInside** variable is true
   * If **playerInside** is true, 
      1. Then reduce the **timer** by Time.deltaTime. 
   * Create a seperate conditional checking if  **timer** is less than or equal to 0 
      1. If true, Call **ZoneSuccess()**.

* **OnTriggerExit()**: Check if the object leaving is the player
  * If player object is leaving the object then, 
       1. Set **playerInside** to false 
       2. Call **SetZoneHelper()** with the parameter of false
       3. Set **timer** equal to **stayTimer**.


## Check Platform Collider
---

Sometimes the zone will spawn somewhere that is a bit out of reach, which requires you to use moving platforms to reach it. Platforms will move automatically back and forth, but when the player touch it, we want it to go fast to reach the zone quickly. Go ahead and open up the **MovingPlatform** script. Below the **Update()** method, you will see the functions to implement.

Note: For parenting objects, use the **transform.SetParent()** method.

* **OnCollisionEnter()**: Add a conditional checking if the object colliding has the tag "Player". (use other.collider.CompareTag("Player"))
    * If the player object has collided with the platform, 
        1. Set the **playerOnPlatform** variable to true
        2. Parent the transform (use transform.SetParent()) of the other object to **this.transform**.

* **OnCollisionStay()**: Check if **playerOnPlatform** is true, which means the player is still colliding with the platform. 
     * If the player object is still colliding then, 
       1. Call **MovePlatform()** with the parameter **superSpeed**. (ex MovePlatform(superSpeed))

* **OnCollisionExit()**: Add a conditional checking if the object colliding has the tag "Player". 
    * If the player object has left the platform, 
         1. Set the **playerOnPlatform** variable to false
         2. Parent the transform of the other object to **null**.

After completing this, you can add some moving platforms to the level. Make sure to specify a starting and ending point.