---
layout: post
tag: Project
---

## Traffic Simulator Design Document

---

The traffic simulator aims to create a realistic representation of vehicular movement within a modeled street intersection environment in Unity. The simulation will consider vehicle behaviors, traffic rules, and environmental factors to generate an authentic traffic flow.

### Objectives

-   Develop a Dynamic Traffic Simulation System
-   Implement Traffic Rule Adherence for AI
-   Ensure Collision Avoidance Among Vehicles

### Visual Concept
![image](https://github.com/Picbridge/Picbridge.github.io/assets/34910988/b2430cf7-192a-4cdb-b11a-9b22e21409c5)

### Core Features

-   **Road System**
    -   A grid layout with a four-way intersection.
    -   Multiple lanes on each road for straight-going traffic, left and right turns.
-   **Traffic AI**
    -   Vehicles will obey traffic lights, yield at intersections, and follow lane directions.
    -   Vehicles will use Unity's NavMesh system for navigation, with custom scripts for complex maneuvers at intersections.
-   **Traffic Control**
    -   Programmable traffic lights with adjustable intervals.
-   **Simulation Parameters**
    -   Adjustable vehicle spawn rate to simulate various traffic conditions.
    -   A UI panel to adjust simulation parameters in real-time.Future Features
-   Random events can be triggered to simulate accidents affecting traffic flow.

### Milestones

-   Environment setup and basic road system.
-   Basic vehicle movement and navigation.
-   Advanced traffic AI behaviors and traffic light system.
-   User interface and simulation controls.
-   Performance optimization and testing.
-   Final polish.

---

### Sources

Art assets : [https://assetstore.unity.com/packages/3d/vehicles/land/simple-cars-pack-97669](https://assetstore.unity.com/packages/3d/vehicles/land/simple-cars-pack-97669)
