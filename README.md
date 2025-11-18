# Procedural Building Generation

For this project I used Houdini to create a procedural walking golem that can move around on a terrain.
The golem has a building on top of it that can be fully customized and infinitely expanded by the user.

## Showcase

Screenshot
![](img/c1.png)

Demo Video 1
[Demo Video 1]([https://private-user-images.githubusercontent.com/180119095/515971460-f3e3c42f-4b79-40f3-a774-dc6bee08437b.mp4](https://private-user-images.githubusercontent.com/180119095/515971460-f3e3c42f-4b79-40f3-a774-dc6bee08437b.mp4?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjM1MDY2MTYsIm5iZiI6MTc2MzUwNjMxNiwicGF0aCI6Ii8xODAxMTkwOTUvNTE1OTcxNDYwLWYzZTNjNDJmLTRiNzktNDBmMy1hNzc0LWRjNmJlZTA4NDM3Yi5tcDQ_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUxMTE4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MTExOFQyMjUxNTZaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT05NjZiYmVjNTI1ZDE2NGJkZWYyMmU2ZTQwYzJmNDJkMWMxNzIyZmJjMjU5ZjQ1NmVjMDM4YmY3MDhjYWFkYjk5JlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.NBLLWycOn2ZcInr6QcfwdKroBxw4mwT74nHhTn0HHh4))

Demo Video 2
[Demo Video 2]([https://private-user-images.githubusercontent.com/180119095/515972043-eada97bc-975a-4140-844d-1a462161f83e.mp4](https://private-user-images.githubusercontent.com/180119095/515972043-eada97bc-975a-4140-844d-1a462161f83e.mp4?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjM1MDY1MDgsIm5iZiI6MTc2MzUwNjIwOCwicGF0aCI6Ii8xODAxMTkwOTUvNTE1OTcyMDQzLWVhZGE5N2JjLTk3NWEtNDE0MC04NDRkLTFhNDYyMTYxZjgzZS5tcDQ_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjUxMTE4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI1MTExOFQyMjUwMDhaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT00MWUxMDA1MjI4Y2E0Y2U3OTYwNGJjNDZkMDRlNjc4YmVkZmI1NDE4ZWY1NmQ2YTYwMWE0MTBhYTQ0NDcyMzJjJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCJ9.74zlUXHEJgEB5BZvWPT5w1NSgUwMMEhJp9Sr1MtszEY))

## Inspiration and Reference

The design and the concept is based on the Walking Mausoleum from Elden Ring, A walking entity that roams around the world and will turn into a permanent landmark when defeated.

![](ref/walk1.png)
![](ref/walk2.png)

## User Control

The user is able to control various aspects of the golem as shown below:

![](img/gui0.png)

## Implementation

All the features, including the 3D assets, are fully created using Houdini.

Screenshot of node network:

![](img/gui1.png)

## Breakdown

The building on the golem is created by stacking multiple floors on top of eachother. each level has a basic polygon cylinder as its base shape, and then the following components are added on top:

- Borders & Decoration
Placed at the top edge and bottom edge of the level, with optional decoration shapes on top.
![](img/f1.png)

- Pillars & Decoration
Placed on the side edges of the level, the decoration on top includeds a extremly simplified squab mesh.
![](img/f3.png)

- Procedurally placed assets
Sampled from a preset of 3 different decoration models, all also modeled in houdini.
![](img/f2.png)

- Support sturctures
Curved beams that connect to the floor below, only generated if the size difference is appropreate.
![](img/f16.png)

- Stacking
At the end, all floors are stacked on top of eachother.
![](img/f4.png)

- Golem Body
A simple base for the golems body, fractured into smaller rocks using a voronoi pattern.
![](img/f10.png)

- Bell
procedurally modeled Bell under the golems body, it is also animated based on a simple string simulation.
![](img/f13.png)

- Trees
Placed at the side of the golem's body, based on a user defined count, created with L-Systems.
![](img/f11.png)

- Golem Leg
Created with the same voronoi pattern like the main body, leg count is based on user input.
![](img/f6.png)

- Skulls 
Human skulls are scattered at the base on the golem's legs for decoration based on the in-game design. 
![](img/f5.png)

- Skeleton
The legs are then rigged procedurally and deformed based on a procedurally generated skeleton.
![](img/f7.png)
![](img/f8.png)

- IK Movement
The skeleton can then move around a defined path on other geometry using Inverse Kinematics;
![](img/f9.png)

The golem will them match the pose of the skeleton and walk on the terrain.
![](img/f14.png)

- Particle System
When the golem's leg steps on the ground, particles are spawned in the animation.
![](img/f15.png)

## Past Submission Content

### Submission2:

Created the basic shape of the structure. Added a fully functioning building generation tool with border, pillars, simple assets and support. there are toggles for border and pillar decorations and it also supports different sided polygons for every floor.

![](img/s3.png)

![](img/s2.png)

### Submission 1

A very basic building tool based on Simon's tutorial (https://www.youtube.com/watch?v=uIe97023sDk&t=979s&ab_channel=SimonHoudini)

![](img/s0.png)

## Future Improvement

This was a really fun project! If given more time, here are the main details that I would still want to improve on:
 - Improve visuals on rocks to look more realistic
 - physics on plants: have them shake when golem steps
 - optimization (current implementation runs slow!)

## Contact
Contact over discord is prefered for any questions!

handle: @nebulirion 
