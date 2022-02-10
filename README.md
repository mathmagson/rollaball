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


## Built With
- Unity
- Visual Studio
- C#

## Future Updates
- [x] Readme "Setting up the Game" section
- [ ] Readme "Moving the Player" section
- [ ] Readme "Moving the Camera" section
- [ ] Readme "Setting up the Play Area" section
- [ ] Readme "Creating Collectibles" section
- [ ] Readme "Detecting Collisions with Collectibles" section
- [ ] Readme "Displaying Score and Text" section
- [ ] Readme "Building the Game" section

## Author
**Matheus Magnusson**
[Profile](https://github.com/mathmagson "Matheus Magnusson")

## Credits
**Unity Learn Platform**
[Website](https://learn.unity.com "Unity Learn Platform")

## 🤝 Support
Contributions, issues, and feature requests are welcome!

Give a ⭐️ if you like this project!