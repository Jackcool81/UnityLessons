# Lesson 1 Supplementary Mini-Project: Ball Drop
 
## Clone Ball Drop Template Repository
1. Clone repository: https://github.com/Jackcool81/DropBall.git
2. Add project to Unity Hub and open

## Game Objective: 
- Find your way to the Goal while doding all Destroyer Cylinders on the way
- The Destroyers have a script attached to them that will reset your ball.
- If you miss the Goal your ball is reset 
![UnityLegacy](https://cdn.discordapp.com/attachments/969018400695259199/1005352470618329098/BallDrop.gif)

### How to Play: 
- Use Keyboard Keys "a" and "d" to move left and right
- Use Keyboard Key "r" to reset your ball
- **Note: Select the Ball in the Hierarchy window before clicking the Play button**

## What To Do: 
- Practice using prefabs and components by creating your own level with a Ball, Goal, and Destroyers.

### Step 1: Add a RigidBody Component to Ball:
1. Navigate to the **Prefab** folder located in the asset folder of the Ball Drop Project.
2. Drag in a **Ball** prefab, place it so that it is floating above the ground by a slight amount. 
3. Select the Ball (through the Scene or Heirarchy Window), then in the Inspector window add a RigidBody Component using the **Add Component** button
- **Note** RigidBodies are a component that allows a GameObject (like our sphere) ti react to real time physics (Gravity, Force, Velocity, etc)

### Step 2: Add in Destroyers:
1. Navigate to the **Prefab** folder located in the asset folder of the Ball Drop Project
2. Drag in  a **Destroyer** prefab and place it anywhere on the Ground plane. 
- **Note** You can use the transform component to scale your Destroyers however you want

### Step 3: Add in Goal
1. Navigate to the **Prefab** folder located in the asset folder of the Ball Drop Project
2. Drag in a **Goal** prefab and place it anywhere on the Ground plane. 

## Stretch Goal: Expand your Map
- Try using the **Transform Component** on the ground object to increase the **Z Scale**.
- You can use the camera's **Transform Component** to move the **Z Position** back so you can see your larger map.
- Now you can add more Destroyers or Goals! 
