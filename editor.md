Unity Editor Standards
=================

#Game Objects

* *Always* name your game objects to something meaningful
* If you have a large set of objects in a scene, nest them into an empty game object to act as a folder. Name the folder something meaningful.
* At the uppermost level of a scene, group objects in folder named `[UI]` or `[Enemies]`. Pick names that work well for your game. The brackets will make it so new things added to a scene will pop to the bottom, where you can easily drag it to the appropriate folder.
* Internal game objects (children or sibling objects in heirarchy) can be assigned through the editor interface (drag-and-drop variable assignment), but external objects should be assigned through code in the `Start()` method. For example, rather than assigning the `Terrain` object to the `Player` through the Unity Editor, the `Player` game object should have an attached script that finds `Terrain`, either by name (`GameObject.Find("Terrain")`) or other means.
