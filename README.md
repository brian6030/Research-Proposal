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
