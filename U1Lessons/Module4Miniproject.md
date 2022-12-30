# Mini Project: Tic Tac Toe 

## Clone Tic Tac Toe Repository
1. Clone repository: https://github.com/Jackcool81/TicTacToe.git
2. Add project to Unity Hub and open (See L1-1 For information on how to Clone and Open to Unity)

## Game Objective 
1. Standard Tic Tac Toe, a 2 Player game where the players take turns placing where they want their Xs and Os.
2. To win the Player must get three of their symbols in a row Horizontally, Vertically, or Diagonally. 

![](https://media3.giphy.com/media/h8z52GwBaa5svdJQnN/giphy.gif?cid=790b761149ea232760f520cc78dd9568f3c8fbea1140d4d3&rid=giphy.gif&ct=g)


## How to Play
1. Since this project is focused on Unity UI, all you will need to do is click on each button to Place your symbol
2. The turn number changes everytime a button is clicked so that you can easily take turns between two players

## What your doing
- Practice working with Unity UI, creating panels, buttons, and manipulating various UI Components

## Step by Step

### Step 0: TicTac Prefab 
1. In the Project Window Navigate to the **Assets->Prefabs** Folder
2. In the Folder there will be a Prefab, named **TicTac** this is a empty GameObject with the TicTacToe Script attached to it. Go ahead and drag and drop this object into the **Heirarchy Window** for your Empty Scene
   - **Note** The TicTacToe script will be vital for Setting up all the Buttons in the Game

### Step 1: Set up Background and Canvas

1. Create a Canvas, you can do this by right clicking on the **Heirarchy Window** then from the Drop Down Select **UI->Canvas**
2. Once a Canvas you want to place all you UI elements inside. For our Background create a Panel under the Canvas by right clicking on the Canvas in the Heirarchy then selecting **UI->Panel** 
3. For changing the Panel image, first select the Panel in the **Heirarchy Window** then in the  **Inspector Window** Drag and drop a Background into the source image property (There are defaults in the **Assets->Images** folder)
    - **Note** To change the Transparency of the Panel, select the A (Alpha) Slider and drag it to the right
    -  **Note** To import your own backgrounds refer to L4-1 under "Image Background"

### Step 2: Set Up Game Board
1. Under the Background in the Hierarchy create a Panel by **UI->Panel** this will be our Game Board
2. For changing the color of this Panel, first select the Panel in the **Heirarchy Window** then in the **Inspector Window** select the color property and choose a color on the Wheel
  - **Note** For the Gameboard, the **Rect Transform Component** Anchor Type should be set to the Middle Preset (This will be easier to place the buttons)
  ![](https://cdn.discordapp.com/attachments/969018400695259199/1025179797795639326/unknown.png)
  - **Note** For help changing the color refer to L4-1 under "Colored Background"


### Step 3: Create ButtonHolder 
1. Create an Empty GameObject by right clicking on the GameBoard Panel and selecting **Create Empty** this will be our Button Holder
2. After you created the Button Holder use the Tic Tac Prefab which has the TicTacToe Script attached to it and where it says "Button Holder" drag your ButtonHolder into the Empty Slot.
![](https://cdn.discordapp.com/attachments/969018400695259199/1025194191770357842/ezgif.com-gif-maker_3.gif)
    

### Step 4: Create Buttons

1. Create a Button by right clicking on the Button Holder and selecting **UI->Button**
2. Add an on click function to our button, by selecting it in the Heirarchy and in the **Inspector Window** scroll down to the Button Component where it says "On Click()" hit the "+" button to add a new function. 
3. Connect the Click Method to the **TicTac Prefab** by dragging it into the empty box that says "None GameObject", then select the drop down that says "No Function" Select the Tic Tac Toe script and select the function that says "ButtonClick()"
![](https://cdn.discordapp.com/attachments/969018400695259199/1025188192053366806/ezgif.com-gif-maker_2.gif)
4. Style the Button by Deleting the Text Component under the Button and use the **Rect Transform Component** to make it a Square by changing the **Width** and **Height** Properties
5. Duplicate the button 8 more times then place them in a grid format using the Rect transform **Pos X** and **Pos Y** properties on each button

## Stretch Goal: Add Reset Button
1. Create a Button under the Game Board Panel,through right clicking and selecting the **UI->Button-TextMeshPro**
2. Add an on click function to our Button, by selecting it in the Heirarchy and in the **Inspector Window** scroll down to the Button Component where it says "On Click()" hit the "+" button to add a new function. 
3. Connect the Click Method to the **TicTac Prefab** by dragging it into the empty box that says "None GameObject", then select the drop down that says "No Function" Select the Tic Tac Toe script and select the function that says "Reset()"
4. Change the Button text by Selecting the Text (TMP) Object under the Button in the **Heirarchy Window** then in the **Inspector Window** locate the Text Box property in the **TextMeshPro-Text(UI)** component
   - **Note** For this step it is important that you have all your buttons under an empty GameObject and that it is attached to the TicTacToe Script
