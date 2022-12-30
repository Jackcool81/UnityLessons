# Lesson 2-11: Final Project, CubeFall!

Fork the Repo [Here](https://github.com/Jackcool81/CubeFall.git)

You play as a blue cube with the ability to move  left and right on your screen. The objective is to stay alive as long as you can as red blocks are spawned in random places in the sky. If you touch a red block, you are dead and the game will tell you how long you survived! The game will reset automatically to allow you to try again.

![](https://cdn.discordapp.com/attachments/984881858758193182/1053771616099766344/ezgif.com-gif-maker_10.gif)



## Player Movement
---


Open up the CubeGame Scene you will see some things have already been placed, so we will first start off by giving the player movement! For this we will be working in the **Player** script which is in the Scripts Folder under the Project tab. We will make use **Time.deltaTime** to make the movement more fluid throughout the game. As well as the **Input** module that will allow to to check if the player is holding down a certain key.

1. Declare a float called **speed**, Intialize it to **10.0f**
2. In the **Update()** method create an if statement checking if the user is Pressing A (**Use Input.GetKey()** with the parameter being the `KeyCode.A` of the key you want) 
   1. If they are pressing A reassign this object's **transform.position** value to itself plus **(Vector3.left * Time.deltaTime * speed)** to make the cube go left
3. Repeat the process creating an if statement checking if the player is  Pressing D 
   1. If they are pressing D reassign this objects **transform.position** value to itself plus **(Vector3.right * Time.deltaTime * speed)**

## Player Collision
---


In the same player file we will check if the player has been hit by an enemy! If so the player is destroyed and the game restarts. We will be making use of  UnityEvents for triggering the **endGame()** method, **OnCollisionEnter()** method to check for objects that are colliding with the player, and **CompareTag()** method to check if we are colliding with the **"Enemy"** Tag.

1. Start by declaring a public **UnityEvent** called **gameEnd**
2. Provide your player with an **OnCollisionEnter()** method. It should be **private**, with a return type of **void** and Parameter type **Collision** named **other** 
   1. Inside the **OnCollisionEnter()** method check if the other colliding object has the enemy tag (use **CompareTag()** with the string parameter Enemy)
   2. If true Destroy this.gameObject (use **Destroy()**) and Invoke the **gameEnd** Event
3. Inside the UnityEditor under the player inspector add a new function call to the gameEnd Event
4. For that new event attach the **gameHandler** object from the heirarchy as the object (Where it says **None (Object)** ) 
5. For this new object select a function which is under 
**GameControl** -> **gameEnd**

*Note*: The **gameEnd** method which will restart the scene after 5 seconds


## The Spawner 
---


For our game to be truly intresting we need to constantly spawn enemies in a random range! We will be working in a new file called **spawner** which is in the scripts folder. To create an enemy spawner we will make use of **Coroutine** methods calling itself over a period of seconds, the  **Instantiate()** method to create a new enemy prefab, and the **Random** module to deteremine our new enemy position.

1. Create an **IEnumerator** method called **spawnZombie()**
2. Inside the method declare a new variable with type **GameObject** called **zombieCopy** and intialize it to the Instantiate of the GameObject **zombie** (use `Instantiate()`)
3. Access the copy's **transform.position** and assign it to a **new Vector3** where the, 
   * X value is a random range **-27** to **27** (use **Random.Range()**)
   * Y value is **21**
   * Z value is **0**
4. We then need to wait a certain amount of time before we run this function again, so use **yield return new WaitForSeconds(spawnTime)** to wait 3 seconds before spawning another zombie
5. After that line we need To loop this IEnumerator by recalling this coroutine, using **StartCoroutine(spawnZombie())**
6. In the start method call the coroutine 
7. Back in the Unity Editor assign the zombiePrefab to the zombie gameobject variable under the **GameHandler** object's inspector 

## The Timer
---

For the player to know how long they survived we will include a timer that starts running right when you start the game or are reset. It is shown to the player at the end of the game. For this timer we will be working in the **GameControl** script. We will make use of **time.deltaTime** variable to keep an accurate timer. Aswell as GetComponent\<T>() to access the TextMeshPro component to display the timer.

1. Declare two new public variables     
   * One with datatype **float** called **timer** Intialize it to **0f**
   * One with datatype **GameObject** called **winText** 
2. In the `Update()` method Create an if else statement checking if **gameover** is `false` 
   * If so the game has not ended so reassign the **timer** to itself plus `time.deltaTime`
   * Else the game has ended so use `GetComponent<T>()` to get the **TextMeshProUGUI** component of the winText variable and reassign it's text property to be **"Time: " + timer.ToString("#.00")**
3. Back in the Unity Editor under the **GameHandler** object's inspector assign the **winText** variable to the **winText** TextMeshPro object.
