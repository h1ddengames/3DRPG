# 3DRPG

A 3D Third-Person Role Playing Game created using Unity 2019.3.0f3.

## How to use this project

If you want to download this project in order to extend/modify it yourself or if you would like to create a build for OS other than Windows, follow these instructions:

1. Clone or download this project using the green icon near the top of this page.
2. Unzip the project files if downloaded.
3. Open the project in Unity using the Unity Hub.
4. On Unity Hub, select Projects.
5. Then select Add.
6. On the file explorer, find the project you cloned or downloaded then click Select Folder.
7. On Unity Hub, click on 3DRPG in the Projects section.
8. Once the project is open, expand the scenes folder and open the Default scene.

OR

1. Download the .unitypackage file from the releases section of this repository.
2. Open a new project and import the .unitypackage file by going to Assets -> Import Package -> Custom Package.
3. Select the .unitypackage file that was downloaded from step 1.
4. Expand the scenes folder and open the Default scene.

## Important assets obtained from Asset Store and other areas

- Character models and animations were found here: https://www.mixamo.com/
- Third Person Character controller found here: https://www.youtube.com/watch?v=ocLZNRasU64&list=PLFt_AvWsXl0djuNM22htmz3BUtHHtOh7v

## Important code helpers being used in this project

- NaughtyAttributes - Used for Attributes in the Unity Inspector found here: https://github.com/dbrizov/NaughtyAttributes
- unity3d-reorderable-list - Used for reorderable lists in the Unity Inspector found here: https://github.com/rotorz/unity3d-reorderable-list
- Serialized Dictionary Lite - Used to see dictionaries in the Unity Inspector found here: https://assetstore.unity.com/packages/tools/utilities/serialized-dictionary-lite-110992

## Important notes for Unity 2019.3.0f3

### Models From Blender

- When importing models from Blender, always use the following commands: A > R > X > -90 > CTRL + A > Apply rotation and scale. When Unity imports this fbx or blend file, it will add +90 on the X axis making it 0 in the inspector which is what we need to be able to paint the object on the terrain.

### Input System

- Input.GetKeyDown() and Input.GetKeyUp() will only return true on the frame that the KeyCode given is pressed down and unpressed respectively. If you want to know if a key is being held down use Input.GetKey()

### Terrain

- You cannot use PolyBrush with the Unity Terrain System.
- You cannot have random tree rotation with a tree that does not have a LOD group component.

### Post Processing

- In order to use Post Processing while using the URP (Universal Render Pipeline):
  1. Go to Window -> Package Manager.
  2. Click on Advanced -> Show Preview Packages.
  3. Scroll down to Post Processing.
  4. Click Install.
  5. Go to the Main Camera in the scene and open the Rendering tab under the Camera component.
  6. Enable Post Processing.
  7. Click on Add Component -> Volume.
  8. Create a new profile or use an existing one.
  9. Add Override -> Whatever Post Processing effect you want until you achieve the look you're trying to achive for your game.

### Script Templates

- In order to create a custom script template go to the following location: C:\Program Files\Unity\Hub\Editor\2019.3.0b11\Editor\Data\Resources\ScriptTemplates
- Open the file 81-C# Script-NewBehaviourScript.cs.txt
- Replace the contents with the script template you'd like to use.
- Here is the script template I use:

    ```c#
    using System.Collections;
    using System.Collections.Generic;
    using UnityEngine;

    namespace h1ddengames {
        public class #SCRIPTNAME# : MonoBehaviour {
            #region Exposed Fields

            #endregion

            #region Private Fields

            #endregion

            #region Getters/Setters

            #endregion

            #region Unity Methods
            void Start() {
                #NOTRIM#
            }

            void Update() {
                #NOTRIM#
            }
            #endregion

            #region My Methods

            #endregion

            #region Helper Methods

            #endregion
        }
    }
    ```
