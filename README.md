<h1 align="center">Roll a Ball</h1>
<p align="center">First Unity Tutorial Project</p>

![Unity screenshot](./gameprint.png)
<p align="center">Collect all the yellow rotating cubes rolling a ball</p>

## Steps to run the game from this repository
- [Download Unity here](https://unity.com/download)
- Clone the repository
- Open the project and click on the play button

<h1 align="center">Code your own project</h1>
<p align="center">Here starts a tutorial below to build your own rollaball game</p>

# 1. Setting up the Game
## Create your own Unity Project
- Select Universal Render Pipeline
- File -> New Scene
- New -> Folder -> "Template"
- Put everything in Assets folder (folders and Readme) in the Template folder

## Create a New Scene
- File -> Save As... -> New Folder "Scenes" ("MiniGame" - name of the scene)

## Create a primitive plane
- Menu (or Hierarchy) "Game Object" -> "3D Object" -> "Plane"
- Rename "Plane" to "Ground"
- Select the 3 dots on the "Transform" section on Inspector to Reset the coordinates of the Ground to the Origin Point of the world (0,0,0)
- Re-Scale your Ground

## Create a Player GameObject
- Create the Sphere at 3D Object -> Sphere
- Rename the Sphere to "Player"
- Reset the position to the Origin Point (0,0,0)
- Set the Y position of the Player to not be buried into the Ground

## Adjust the default lighting
- Select the "Directional Light" on Hierarchy and change the color to pure white

## Add Colors with Materials
- Select to create a New Folder in Assets named "Materials"
- Create "Material" inside "Materials" folder
- Rename the Material to "Background"
- Change the Background Material color Base Map
- Change the Metallic Map and the Smoothness
- Drag the Background Material to the Ground on the scene
- Do the same for the Player
- Change the Directional Light Rotation to (50,50,0)

# 2. Moving the Player
## Add a Rigidbody to the Player
- In the Hierarchy select the Player GameObject
- In the Inspector select Add Component and search and select "Rigidbody"

## Install the Input System package to apply forces and move the Player
-  To install the Input System package, into top menu go to "Window" and "Package Manager"
- Select "Packages" tab and select "Unity Registry"
- Find Input System, then select Install to add the Package to your project
- You might see a Warning shows up, select "Yes" to enable the native platform backends for the Unity Input System and Select "Save" your changes to the Scene

Now you're able to use the keyboard inputs!

**If you are making this game for Windows**
## One more step
- In the top menu, go to "File", "Build Settings"
- Change the Architecture to x86_64
- Close the "Build Settings"
**You'll find more about this when you finish your game**

## Add a Player Input component to the sphere
- In the Hierarchy, select the "Player" GameObject
- In the Inspector, select "Add Component", then search for and add "Player Input"
- Go to the Inspector window, in the "Player Input" component, select "Create Actions" and create a new folder called "Input" inside "Assets" folder. Name "InputActions" and save inside "Input" folder that you just created

## Create a new script
- In the "Project" window, click on the Create menu and choose "Folder", rename it as "Scripts"
- Select the "Player" GameObject in the Hierarchy and then use the Add Component button in the Inspector. Search and select "New script" (that way you create and attach a new script in one step)
- Name the new script as "PlayerController"
- Select "Create and Add" or press the Enter key
- Move the file "PlayerController" created into the "Assets" folder to the "Scripts" folder in the Project window
- Select the file "PlayerController" and in the Inspector select "Open"

## Write the OnMove function declaration
- You don't need the Update() function for now, so you can remove it
- Update() is called before rendering a frame, and this is where most of your code will go
- FixedUpdate(), on the other hand, is called just before performing any physics calculations, and this is where your physics code will go
- Add a new line below the first three namespaces (below the line "using UnityEngine;"), write "using UnityEngine.InputSystem;"
- The PlayerInput component will notify the PlayerController script of action happening by calling functions with pre-defined names within your scripts
- You need to be notified whenever the move action happens. The predefined function for the changes in movement controls when pressing WASD or moving the joystick (or the keyboard's arrows) is called OnMove, and you can find it selecting "Player" GameObject in the Hierarchy and visualizing in the Inspector "Player Input" section the functions avaiable
- The computer will read the information of the key pressed and then use that information to move the ball using code in the Update function which you'll write later
- Write into the script code, right after the function Start, the function:
```C#
void OnMove(InputValue movementValue)
{

}
```

## Apply input data to the Player
- Let's use the method Get to get the movement input data from the sphere and store it's a Vector2 variable:
```C#
void OnMove(InputValue movementValue)
{
    Vector2 movementVector = movementValue.Get<Vector2>();
}
```
- The "Player" GameObject uses a Rigidbody and interacts with a physics engine.
- Next, you need to use the variable you just created to add or apply forces to the Rigidbody and move the "Player" GameObject in the scene
- To do this, your PlayerController script will need to access the Rigidbody component and add force to the "Player" GameObject
- First let's create a variable to hold the reference in the script:

```C#
public class PlayerController : MonoBehaviour
{

    private Rigidbody rb; // hold the reference in the script

    // Start is called before the first frame update
    void Start()
    {

    }

    void OnMove(InputValue movementValue)
    {
        Vector2 movementVector = movementValue.Get<Vector2>();
    }
}
```

- The variable is private and not public because you don't need this variable to be accessible from the Inspector or from the other Scripts right now
- Next, inside the Start function, write:

```C#
public class PlayerController : MonoBehaviour
{

    private Rigidbody rb; // hold the reference in the script

    // Start is called before the first frame update
    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    void OnMove(InputValue movementValue)
    {
        Vector2 movementVector = movementValue.Get<Vector2>();
    }
}
```

- This sets the value of the variable "rb" by getting a reference to the Rigidbody component, attached to the Player sphere GameObject
- All of the code in the Start function is called on the first frame that the script is active. This is often the very first frame of the game. So the player will be able to move the sphere straight away


## Built With
- Unity
- Visual Studio
- C#

## Future Updates
- [x] Include "Setting up the Game" section
- [ ] Include "Moving the Player" section - ```diff 
+ in progress 
```
- [ ] Include "Moving the Camera" section
- [ ] Include "Setting up the Play Area" section
- [ ] Include "Creating Collectibles" section
- [ ] Include "Detecting Collisions with Collectibles" section
- [ ] Include "Displaying Score and Text" section
- [ ] Include "Building the Game" section

## Author
**Matheus Magnusson**
[Profile](https://github.com/mathmagson "Matheus Magnusson")

## Credits
**Unity Learn Platform**
[Website](https://learn.unity.com "Unity Learn Platform")

## 🤝 Support
Contributions, issues, and feature requests are welcome!

Give a ⭐️ if you like this project!