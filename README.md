# Research-Proposal

Using smartphone to navigate inside a building with a most efficient route

## Objectives:
1. Precise location of the user's position within an interior environment. Locate the floor and room the user is currently in.
2. Pathfinding within an interior environment. Users need to travel between different floors. The navigation system should be able to analyse room connection, location of elevator and staircases. Then calculate a shortest path then navigate users to their destination.
3. Display the AR navigation guidance on the smartphone for users.

## AR environment implementation:
Unity Engine (Universal Render Pipeline)
### Platform: 
Android 7.0 or above / IOS 11.0 or above
### AR API: 
AR Foundation
- AR Foundation is a Unity package that allows user to develop AR applications in a multi-platform way within Unity. It can develop the AR environment in Unity then build to Android or IOS platform in Unity editor. It provides an interface to connect with different AR API, for instance Google ARCore, ARKit for IOS, and Windows XR Plugin for Microsoft HoloLens. Developers can develop the AR applcation once, then build to multiple platforms.

## AR develop environment setup on Unity
Tutorial: https://youtu.be/jBRxY2KnrUs

### Universal Render Pipeline
The app will be developed using Universal Render Pipeline. It is a new render pipeline in Unity Engine. The reasons of developing in this render pipeline is because it provides custom render passes for developers to customize the render pipeline, and more lightweight shaders for meshes to render. Therefore it is more flexible to fit in different situation and development purpose. Optimized to execute on low-ended hardware and mobile devices.

### Camera become solid color after build using Universal Render Pipeline
<img src="/Images/52a0c660-765b-4074-91f7-3377c34ebbe4.jpg" width=20% height=20%>
The camera has nothing to show after the app is built on phone using Universal Render Pipeline.

<img src="/Images/screenshot%20(1).png" width=60% height=60%>
Solution: Add AR Background Render Feature to renderer settings.

### Implementation of AR environment in Unity
<img src="/Images/screenshot%20(2).png" width=60% height=60%>
Install package AR Foundation, ARCore XR Plugin (for Android), ARKit XR Plugin (for IOS)

<img src="/Images/settingAn.png" width=60% height=60%>
Setting of Android Platform

<img src="/Images/settingIOS.png" width=60% height=60%>
Setting of IOS Platform

<img src="/Images/screenshot (3).jpg" width=40% height=40%>
Built the demo project by ARFoundation on my Android phone https://github.com/Unity-Technologies/arfoundation-demos
The 3D model will pop up when the AR tracker image is detected

<img src="/Images/screenshot (4).jpg" width=60% height=60%>
Created a new project and tried some basic functions of AR Foundation. It will detect the planes then user can tap the screen to place the 3D model on the AR surface

## Comparison with other existed AR projects
There are many ways to create an AR application now. I have compared different AR environmentation method to using AR Foundation in Unity Engine. Here are 2 projects I have reseached to analyse their advantages and disadvantages.
- [Puzzle Knight (My old AR game)](https://youtu.be/CYOTs3uddwE)
- [DroidAR](https://github.com/bitstars/droidar)

### Puzzle Knight
This is my bachelor's degree's final year project. It is an AR puzzle game. The game is based on AR tracker. It has different trackers represent different levels. When the AR camera tracked the tracker, the corresponding level will be shown.
- Advantages over AR Foundation
  - Faster tracking time 
    - Since it only need to track the AR tracker
    - AR Foundation trackerless tracking has to scan the surrounding environment first, therefore, it takes more time to initialize the AR environment
  - More accurate tracking
    - Using AR tracker, therefore there are more robust image features to track than trackerless tracking
- Disadvantages compare to AR Foundation
  - No depth occlusion
	- Depth occlusion can detect objects in physical world that closer to the AR camera than the virtual 3D model. Then occlude the 3D model to create an illusion that the 3D model is blocked by objects in the real world
  - Lose tracking easily when zoom too close to the tracker
	- It cannot record the AR coordinate of the 3D models, therefore it can only use tracking
	- When the camera zoom too close to the tracker, the camera cannot track all the image features, then it will often lose the tracking.
  - Higher battery consumption
	- Battery drains very fast while playing the game
 
### DroidAR
This is an AR framework for Android. It can be used to develop both tracker and trackerless AR applications. It supports indoor AR tracking and locationbased Gaming.
- Advantages over AR Foundation
  - Old version of DroidAR is opend source
	- Despite DroidAR 2 is closed source, the source code of old DroidAR is fully accessible on GitHub. Developers can debug the API easily.
	- The API can be modified and improved by other developers since it is opened source.
- Disadvantages compare to AR Foundation
  - No depth occlusion, cannot detect depth value.
  - Since it is a relativly old framework, the graphic render quality is not relistic as the current AR API
    - No light estimation, the 3D model cannot match the physical world's lighting
    - Tracking is not stable
  - It is not popular as other AR API. Update is not frequent as Google ARCore or IOS ARkit
    - Difficult to develop new functions in a short period
