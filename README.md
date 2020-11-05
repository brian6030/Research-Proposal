# Research-Proposal

Using smartphone to navigate inside a building with a most efficient route

## Objectives:
1. Precise location of the user's position within an interior environment. Locate the floor and room the user is currently in.
2. Pathfinding within an interior environment. Users need to travel between different floors. The navigation system should be able to analyse room connection, location of elevator and staircases. Then calculate a shortest path then navigate users to their destination.
3. Display the AR navigation guidance on the smartphone for users.

## AR environment implementation:
Unity Engine (Universal Render Pipeline)
### Platform: 
Android / IOS
### AR API: 
AR Foundation
- AR Foundation is a Unity package that allows user to develop AR applications in a multi-platform way within Unity. It can develop the AR environment in Unity then build to Android or IOS platform in Unity editor. It provides an interface to connect with different AR API, for instance Google ARCore, ARKit for IOS, and Windows XR Plugin for Microsoft HoloLens. Developers can develop the AR applcation once, then build to multiple platforms.

## AR develop environment setup on Unity
