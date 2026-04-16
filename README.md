# snake-game
<img width="865" height="487" alt="3f1dd2c51c01510a0a57f0389b3ade66" src="https://github.com/user-attachments/assets/eef6e533-5a67-49a4-b42e-a03883bb8106" />

Purpose of the software
 [1] We  use the agile model.
  [2]reason
  1.As a foundation for subsequent flexible iterations to seize the market
Choose agile development to leave sufficient space for the project's commercialization and market capture in the future. In the future, if we want to turn this game into a launchable product, we can quickly iterate the functions based on user feedback and respond more quickly to market demands.
  2.The project is small in scale and has flexible requirements. Agile is more suitable.
In the development process of games like Snake, it is easy to add ideas temporarily and modify details. The waterfall flow is linear and it is troublesome to make modifications later. However, agile allows for adjustments while working, which perfectly suits small projects.
  3.Quick results can be seen, facilitating team collaboration and adjustments.
Agile is developed in small iterations. We can quickly create the core "the snake can move and eat food" minimum viable version within a short period of time. Everyone can directly play and see the effect, and then gradually add functions and fix bugs. Unlike the waterfall flow, where the final product can only be seen after all stages are completed, problems in the middle are difficult to detect in time and it is not convenient for teammates to offer suggestions.
  4.Suitable for the development rhythm of small teams.
Agile development is more flexible. It focuses on writing code and implementing functions. The development progress can be adjusted according to everyone's time, and there will be no situation where a certain part slows down the entire project.
  5.Convenient for rapid trial and error and optimizing the experience.
The operation feel of the game, the speed of the snake's movement, and collision detection, etc., can only be known through actual play. Agile development allows us to test and fix bugs after completing one version.
 [3]target market
The target market mainly consists of the following two aspects
  1.Casual game enthusiasts (core mass market)
Players of all age groups, including students, office workers, and the elderly, without professional gaming skills, are seeking a low-barrier, stress-free entertainment experience.
This is our core user group, with a large base and stable demands. We can make them aware of it through multiple channels such as mini-programs, short-video platforms, and web pages.
  2.Competitors driving the development of software (vertical advancement market)
Game enthusiasts, participants in snake eating competitions, etc., have high game proficiency, and pursue operation, high scores, and innovative gameplay
Break through the limitations of the game, even conduct secondary development based on the project, promoting the iteration of game functions and gameplay innovation
The feedback from these users can help us quickly optimize the game experience, discover bugs, and at the same time, their competitive content can bring popularity to the product, attract more users, and promote the continuous development and ecological improvement of the software itself.
1. Development Process & Project Timeline
Throughout the entire process, we adopted the agile development approach, dividing the project into 4 iterative sprint phases. Each phase had clear timeframes, deliverables, and phased tasks, ensuring the smooth progress of the Snake Game development..
Sprint 1: Requirement Analysis and Core Prototype Development
Timeline: Day 1
Core Tasks:
1.1.1Confirm project requirements and core game theme: Single-player snake step game, including step-by-step movement logic, basic user interface framework design
1.1.2Build the minimum viable product prototype and implement the core game logic
1.1.3Complete the basic game loop: Snake movement, food generation/eating, collision detection (wall/self collision termination)       Deliverables:
Requirement specification document
Functional prototype of the single-player "snake" game (including complete core logic)
Basic user interface framework
Sprint 2: Iteration of Dual Player Mode and Optimization of User Experience
Timeline: Day 2
Core Tasks:
1.2.1Develop and launch the dual player battle mode, setting the P2 control logic (using the W, A, S, D keys for control)
1.2.2Optimize collision detection rules (mechanism for punishing opponent collisions)
1.2.3Implement a virtual steering wheel based on clicks to support mouse/touchscreen operations
1.2.4Conduct comprehensive functional testing of single-player and dual-player modes, and fix errors related to operation
Deliverables:
Two- Player Battle Mode Function Version
Upgraded Collision Detection System
Multi-input Operation Adaptation Module
Test Report and Bug Fixes
Sprint 3: Comprehensive Optimization of Scoring System and User Interface/User Experience
Timeline: Day 3
Core Task:
1.3.1Develop a real-time scoring statistics system and dual leaderboards (single-player mode/dual-player mode)
1.3.2Implement local data persistence using localStorage to save scores
1.3.3Optimize the layout of the user interface and responsive design
1.3.4Complete compatibility testing for computers and mobile devices
Deliverables:
Scoring system and leaderboard module
Local data storage
Responsive user interface design and adaptation plan
Cross-device compatibility testing
Sprint 4: Function Closure, Online Deployment and Experience Optimization
Timeline: Day 4
Core Tasks:
1.4.1Upgrade the game control buttons (start/pause/restart/back)
1.4.2Deploy the project to GitHub Pages for online practice and public testing
1.4.3Conduct comprehensive regression tests for all functions, fix minor errors
1.4.4 Polish game interaction experience, optimize performance and loading speed
Deliverables:
The final version of the game, including all functions
Online deployment link (on GitHub page)
Complete test report
Final project delivery package
2.Members（Roles&Responsibilities&Portion）
ZHANGXINYUN（p2421611）：Source codes（and data if it is applicable）    【100%】
SHAOZHURUN（p2421468）：Documentation（Graphical Abstract&Purpose of the software）   【33%】
RENSIYAN（p2405280）：Documentation（Software development Plan：Development Process）   【33%】
LIUSHIYU（p2421183）：Documentation（Software development Plan：Algorithm）【33%】
ZHANGRUOXI（p2421107） ：Demonstration-Video clips  【100%】

3.Schedule
Sprint 1 — Day 1

Core Mission:
Group discussion and requirement confirmation, role division and allocation, project foundation establishment, core logic development for single-player mode, and construction of the minimum viable prototype.

Sprint 2 — Day 2

Core Mission:
Development of the two-player battle mode, optimization of collision detection rules, adaptation of multi-input operations (keyboard, mouse, touchscreen), improvement of user interaction experience, and bug fixing.

Sprint 3 — Day 3

Core Mission:
Development of real-time scoring and dual leaderboards, implementation of local data persistence using localStorage, optimization of user interface and user experience layout, and cross-device compatibility testing.

Sprint 4 — Day 4

Core Mission:
Completion of all core functions and control features, deployment of the project to GitHub Pages, full testing of the system, fixing minor issues, improvement of game performance and user experience, and final integration of documentation and testing materials.
 4. Algorithm
Key Algorithmic Components:
4.1Game Loop and State Management
The game is driven by a main loop that manages four states: "ready", "running", "paused", and "game over". In the "running" state, the game state updates at fixed intervals (e.g., 500ms). This "step-based" update, triggered by a timer, is fundamental to the core "move-and-pause" gameplay, distinct from traditional continuous-movement Snake games.

4.2Snake Movement and State Representation
The state of each snake is represented by an array named snake. Each element in the array is a coordinate object {x, y} representing a single segment of the snake's body on the grid. To move, a new head coordinate is calculated based on the current direction (dx, dy) and inserted at the beginning of the array. If the move does not result in food consumption, the last coordinate (the tail) is removed from the array. If food is eaten, the tail is not removed, resulting in the snake's growth.

4.3Collision Detection System
Wall Collision: Check if the new head's coordinates {x, y}are outside the grid boundaries (x < 0 || x >= gridSize || y < 0 || y >= gridSize).
Self-Collision: Iterate through the snakearray to check if the new head's coordinates match any other body segment's coordinates.
Opponent Collision: Exclusive to "VS Mode". After a move, check if the current snake's head coordinates collide with any segment of the opponent's snake. Collision results in an immediate loss.
Food Collision: Check if the new head's coordinates match the current food's coordinates. If true, the score increases, the snake grows, and a new food item is generated at a random location not occupied by any snake.

4.4Input Handling and Response
The game supports both keyboard and on-screen input. Keyboard events (key down) are listened for, with arrow keys controlling Player 1 and WASD keys controlling Player 2. On-screen directional buttons simulate key presses via click or touch events. An input lock prevents multiple valid direction changes within a single game step, ensuring the snake processes one queued direction per move.

4.5Data Persistence (Leader board)
The browser's local Storage API is used for the local leader board. When a game ends, the player's score is evaluated against a stored array of historical records. If the score is higher than the lowest record or the array is not full, it is inserted. The array is then sorted in descending order, trimmed to the top N entries (e.g., 5), and saved back to local Storage. On initialization, the leader board is read from local Storage and rendered.



5. Current status of your software 
Completed Features:
Full Game Modes: Successfully implemented the planned "Single Player" and "Two Players VS" modes.

Core Game Logic: Implemented "step-interval" based movement, precise collision detection (wall, self, opponent, food), and real-time scoring.

Diverse Control Schemes: Simultaneous support for keyboard (Arrow Keys/WASD) and on-screen virtual D-pad, ensuring compatibility on both PC and mobile devices.

Local Data Management: Utilized local Storage to implement independent high-score leader boards for both single and VS modes.

Complete User Interface: Includes mode selection, main game interface, control panels, status indicators, and leader boards. Features responsive design and an aesthetically pleasing layout.

Project Management & Deployment: The code is version-controlled via GitHub and has been successfully deployed to GitHub Pages, allowing instant online access and play testing via a public link.

Deployment & Testing:
Development has concluded. The software has passed internal functional and user experience testing. It is now running stably online as a deliverable product, providing a smooth user experience.

6. Future plan
Although the current version is fully functional, we have outlined the following future development directions to enhance user experience, expand the audience, and explore commercialization potential.

6.1Feature Expansion & Gameplay Innovation
Enrich Game Modes: Plans to add a "Time Attack Mode" (highest score within a time limit)
Introduce a Power-up System: Design items such as "Speed Boost/Slow Potion", "Phase Through Walls", and "Food Magnet" to increase randomness and strategic depth.
Social & Competitive Features: Develop "Daily Challenge" tasks and integrate social sharing functionality, allowing players to share scores on social platforms or view friend leaderboards.

6.2Introduce Backend Services: Develop a simple backend API to implement a global online leaderboard, a user account system, and cloud save functionality, enabling player data synchronization across devices.

6.3Community Building & Open Source
Open Source the Project: Make the code repository public on GitHub, accompanied by detailed development documentation and contribution guidelines to attract developer collaboration and build a community.
Mod & Customization Support: Provide a level editor or Mod development interface, allowing advanced users to create custom maps, rules, and skins, significantly extending the game's lifecycle.


