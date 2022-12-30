# Lesson 2-10 Exercises

Open Scene8 from Scenes Folder.

## Exercise 2.10.1

For this exercise you are going to create your own Unity Event and attach a function to it that shows Happy Birthday and the Date when you run the game.

1) Open the UnityEventScript which is already connected to the cube. 
2) Inside the UnityEventScript class declare your own Unity Event called **surprise**. 
3) Now inside the cube's inspector locate the Unity Event in the UnityEventScript Component. 
4) Attach the HappyBirthday GameObject to to the Unity Event and select the HappyDay script from the drop down. 
5) This should pop up a list of functions associated with the HappyDay script you want to select the printBday function and run the game!

## Exercise 2.10.2

For this exercise you are going to declare a couple of variables inside your own scriptable object, create a new instance of the scriptable object, assign values to the variables, and finally print them in a seperate script.

1) Open up the AllyUnit Script located in the scripts folder. 
2) Next inside of the AllyUnit class create three new public variables,    
    a) public **string** called *name* <br>
    b) public **int** called *health* <br>
    c) public **float** called *damage*

3) Save the script and head back to the Unity Editor. 
4) Make an instance of this AllyUnit in the project folder, by right clicking into the project window selecting Create->CustomObject->Ally. 
5) Locate the ScriptableObjectExample script and open it up, inside create a public variable to hold the AllyObject. 
6) In the start method use that reference to print out all the variables in AllyObject to the console and run the game! 


