# OOP Assignment #6

- Due: 2026/6/2 23:59:59
- Author: 111703003 廖經翔
- Contact: <111703003@g.nccu.edu.tw>

---

## 2D Game (2/2)

Objective: Extend the game skeleton from Assignment #5 and build a simple Vampire Survivors-like survival game.

### Description

In this assignment, you are required to extend the basic game structure from Assignment #5.

You will implement a simple survival game (Like Vampire Survivor). The player can move around the screen, enemies will spawn periodically and chase the player, and the player will attack automatically. The goal is to survive as long as possible.

This assignment focuses on Object-Oriented Design, object interaction, collision handling, and game state management.

### Requirements

1. Reuse or extend the architecture from Assignment #5.
2. Design an architecture that continues to decouple UI logics and Data logics.
3. Implement a movable Player GameObject.
   - The player should be controlled by keyboard input.
   - Example: WASD to move.
4. Implement Enemy GameObjects.
   - Enemies should spawn periodically.
   - Enemies should move toward the player.
5. Implement an automatic attack system.
   - The player should attack automatically at a fixed interval.
   - You may implement the attack as projectiles fired toward the nearest enemy.
6. Implement Projectile GameObjects.
   - Projectiles should move after being created.
   - Projectiles should disappear after hitting an enemy or leaving the screen.
7. Implement collision detection between:
   - Projectile and Enemy
   - Enemy and Player
8. Implement HP for both Player and Enemy.
   - Enemies should disappear when their HP reaches zero.
   - The player should lose HP when colliding with enemies.
9. Remove dead enemies and expired projectiles from the game world.
10. Display basic UI information:
    - Player HP
    - Survival time
    - Kill count
11. Implement a Game Over state.
    - When the player's HP reaches zero, the game should stop and display a Game Over message.
12. Update your UML Class Diagram to show the architecture of your app briefly.

### Expected Output

After running the program, the following should be displayed on the window:

1. A movable player GameObject with key control.
2. Enemy GameObjects that spawn periodically.
3. Enemies moving toward the player.
4. The player automatically attacking nearby enemies.
5. Projectiles damaging enemies.
6. Defeated enemies disappearing from the game.
7. The player losing HP when touching enemies.
8. A Game Over message when the player's HP reaches zero.
9. Basic UI showing:
   - Player HP
   - Survival time
   - Kill count

> You can customize every GameObject's appearance.

### Suggested Architecture

You may design your own architecture, but your program should clearly separate different responsibilities.

For example:

```text
GameWorld
- Stores and manages GameObjects
- Updates all objects
- Removes dead or expired objects

GameObject
- Base class of objects in the game
- Stores basic data such as position and size

Player
- A movable GameObject
- Has HP
- Can be controlled by keyboard input

Enemy
- A GameObject that moves toward the player
- Has HP

Projectile
- A GameObject created by the player's attack
- Moves in a direction
- Damages enemies

Spawner
- Controls enemy spawning

Weapon / AutoAttack
- Controls the player's automatic attack behavior

CollisionSystem
- Handles collision detection between objects

GameObjectFactory
- Creates GameObjects such as Player, Enemy, and Projectile

Renderer / GameView
- Handles GameObjects drawing logic

UIRenderer / HUDRenderer
- Draws HP, survival time, kill count, and Game Over text

GameController
- Controls the main loop
- Reads input
- Updates the model
- Calls the view to render the current state
```

You do not need to use exactly the same class names, but your design should have clear responsibility separation.

### Scope Limitation

You do **not** need to implement the following features:

1. Level-up system
2. Multiple weapons
3. Experience gems
4. Upgrade selection UI
5. Sound effects
6. Animation
7. Scrolling map
8. Complex enemy wave design

These features may be implemented as bonus features, but they are not required.

### Bonus

You may implement the following features for extra points:

TBD

### Compile and Run

Before compiling the program, in **Project Folder**:

```console
cmake -B build
```

```console
cmake --build build
```

To run the program:

```console
./build/[your_project_name]
```

### Submit the assignment

- The Github repository should inherit from Assignment 5.
- To submit the assignment, please use the following command to commit:
```
git commit -m “feat:Assignment5 submit”
```

to mark the submission version. Otherwise, the last commit before the deadline will take precedence.

### Scoring Criteria

TBD

### Reminder

1. The default `include` and `resources` path is configured. You don't need to add prefix to locate files.
   Just use `#include "some_header.h"` under `include/`.
2. You may create new files for more features.
3. This assignment is based on Assignment #5.
4. Focus on clear Object-Oriented Design rather than complex game content.
5. Keep your game simple and playable.
