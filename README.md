# GDIM 33 In-Class Activities
## W1
### Activity 1

[Mood Board Link](https://www.figma.com/design/lAhA7HvISIvNDCbMs1xBvM/GDIM33-Mood-Board?node-id=0-1&t=NBryKd18J8DVdteo-1)

1.1 As I create the mood board, I realized an apprant preferences of horror, cyberpunk, minimalist, and futuristic. A particular mechanic that I found intriguing is survival horror, either with platform 8, where players need to proceed whenever it is safe, or fight with monsters using limited resources. A specific genre that I love is from the game Control, with Neo-noir, metaphysical, and surrealism, resulting in an exaggerated architectural scale and dramatic contrast between individuals. In terms of vertical slice, I would like to create a 3D survival horror game with limited resources, monster chase, and a spooky environment.

1.2 After chatting with Alex, I realized a similar interest in cyberpunk style, where technological advancement has led to greater division between the rich and the poor. Aesthetically, both of us are interested in nights lit up by neon lights, a messy environment, and the struggle of the individual. After chatting with Yan, I noticed a similar interest in the rebuilding effect of light in the game. She is interested in light shining through the window and reflection in water. I also want to explore the properties of water and light.

1.3 TA loves playing multiplayer games, particularly player vs. player games such as Overwatch. This is particularly different from my taste in games because I’m a big fan of single-player narrative-driven RPG games such as Cyberpunk 2077 and Red Dead Redemption. However, I do enjoy multiplayer games in a more collaborative means such as Overcooked, Mario Party, Split Fiction, and It Takes Two. Interactions that happen between real people sometimes are more unexpected and interesting compared to AI-driven NPCs.

### Activity 2

2.1 selected genre: 3D survival horror, Resident Evil/Layers of Fear-like. Includes gameplay of resource collection and management, monster chase, and sanity system. The player plays as the hazard cleanup unit assigned to clean an abandoned lab after a failed experiment, using unconventional weapons to deal with monsters (like a water gun? broom? light etc.). 

2.2 Core mechanics: 
      resource management: collect limited medicine/ammo to recover or to attack in combat, 
      survival strategy: hide/run from or attack the monster
      sanity: player loses sanity if they remain in the dark for too long
      Goal: key-item collection to enter the next level or to escape the room. 
    Core game loop: 
      exploration and collection of medicine/ammunition/key- threat encounter: monster -           resource expenditure - recovery by healing using medication and or reload using              ammunition - return to exploration

[Break-down Diagram Link](https://www.figma.com/design/GscfURruZJtSMoIxLdmxUY/GDIM-33-Break-Down-Diagram?t=JKCzMFfHauji2zpV-1)

## W2

N/A

## W3

### Activity 1

[Updated Breakdown Diagram Link](https://www.figma.com/design/npm787IlXqCvnhdhI53a0R/Xichan-Updated-Breakdown?node-id=0-1&p=f&t=UgTFQP49jCnK04cZ-0)

### Activity 2

1. It is advantageous to save the event name for the explore-to-dialogue state transitions as the Scene variable clickNpcEventName because it allows easier management. Using a variable to manage action easier compared to a node because it will avoid misspelling. I use a variable clickNpcEventName = clickWalrus and call the variable clickNpcEventName so that I don’t need to type clickWalrus every time I need to use that node. Moreover, if I want to change the name of the node, I will only need to change it one time rather than changing it in every place in each graph and custom event.


2. I added a Debug.Log() node for step 7, checking whether the animal falling stopped in the dialogue mode, and continued in the explore mode. This node is particularly useful because in dialogue mode, the cursor is locked, and I couldn’t look upward to see whether the animal is stopped in the air. However, after I added the debug log to test whether animals were stopped by the graph, I’m sure now that the Set Enabled is working.


3. The Set Cursor Lock State is relevant to my Vertical Slice because I would like to lock the player’s cursor when they are exploring the maze, and unlock the cursor when they interact with the riddle at each crossroad. After the player clicks on the riddle, a text will appear, similar to the dialogue state in this activity. Cursor unlock in this state makes sense because the player needs to interact with the text and exit UI. It is useful to lock the cursor when exploring because the cursor movement might be distracting. 


4. The concept of a game state and state machine is extremely relevant to my Vertical Slice because my horror game involves a monster switching in various mutually exclusive states, with each state performing different actions. The monster will switch between states of patrol, search, chase, and attack. In patrol state, the monster wanders around in predetermine path or to a random location using Navmesh. After the player gets in the detection range of the monster, it transitions into the search state. After the player gets in the monster’s line of sight, the monster switches into chase state and pursues the player at a higher speed. If the monster gets near enough to the player, it switches to the attack state and damage player.


## W4

### Activity 1

#### Playtest Goal

For my current build, the player could walk, look around, and explore the maze while a monster chases them. If the player gets caught, the game ends, and they can restart the game. The NavMesh AI navigation for the monster works and allows the monster to patrol between two patrol points. 

The goal for today’s playtesting is to determine whether the monster’s AI navigation system and state machine controlling state transition between patrol, chase, and attack work properly and repeatedly. I would also like to figure out whether the basic mechanics of running from the monster are intuitive enough and if the maze is well-designed so that it is easy to navigate. 

Playtest Team Member: Tina Meng,Xichan Zheng,JingyiBi,Alex Ding,Yan Zhang

#### Playtest Note

1. The player’s mouse-controlled look-around is too fast, making them feel dizzy and sick.
2. Monster’s chase/attack detection range is too small. Once the player leaves its range, the monster instantly ignores the player and proceeds to the patrol point. Other team members said that this kills the horror vibe. Maybe it is better to use the field of view instead of the distance as the detection range, so that it is more intuitive. 
3. Maze design with a lot of crossroads seems to be working well, as my peers look scared when they arrive at a crossroad. 
4. The environmental lighting is too bright; it is better to reduce the intensity and number of lights.
5. The walls in the scene are too dark and similar; they sometimes crash into walls.
6. The player moves too fast, even faster than the monster
7. One of the team members suggested hiding a hiding spot, such as a closet, to introduce stratetigic element in the chase.

### Activity 2

1. Yes, a writer could add more dialogue to this setup without writing any code because the lines are mainly stored in ScriptableObject instead of in C# script. They could simply use the inspector to create a new dialogue node or edit an existing node. The writer does not need to know how to code.

2. Without writing any code, the number of dialogue nodes is unlimited because the writer could always continuously add new nodes to DialogueNodeW4. However, the actual number of dialogues might be influenced by project scale or management.

3. The purpose of regenerating nodes before the activity is to rescan code and types so that custom types like PlayerReplyW4 can be identified and become a usable node in visual scripting graphs.

## W5

### Activity 1

Animation system

This system will allow the monster to play different animations based on the state it is in. For example, the patrol state will play a walk animation, whereas the chase state will play a running animation.

Basic steps:
1. create animator
    1. download monster 3D model with animations: idle, walk, run, attack
    2. import model and animation clips into Unity
    3. create an animator controller. 
    4. add an animator component and attach it to the monster
    5. add animation states in the animator controller, including idle, walk, run, and attack
    6. create an integer animator parameter named monsterState, which refers to each animation clip using an integer parameter
        1. monsterState = 1: Patrol
        2. monsterState = 2: Run
        3. monsterState = 3: Attack
    7. set animation transition based on monsterState value using conditions
    8. test whether the setup is successful by changing the monsterState integer in the animator window when running the game and see whether the monster switch animation
2. link the animator with the monster’s navigation state machine graph
    1. open monster’s navigation state machine graph
    2. open patrol state and add an Animator Set Integer node to set the monsterState integer to value 1, corresponding to the walk animation
    3. test whether the walk animation and transition work by running the game and checking if the monster is walking in default patrol state.
    4. open chase state and add an Animator Set Integer node to set the monsterState integer to value 2, corresponding to the run animation
    5. test whether the run animation and transition work by running the game and checking if the monster switches from walk to run when the player enters detection range. 
    6. open attack state and add an Animator Set Integer node to set the monsterState integer to value 3, corresponding to the attack animation
    7. test whether the attack animation and transition work by running the game and checking if the monster play attack animation when player enters attack range.
  
### Activity 2

During class, I followed the steps to build the animation system. I finished importing the 3D model, animation clip, set up a monster animation controller, and added the animation state and integer animator parameter. I disable the monster’s capsule placeholder mesh renderer and drag the monster model as a child object so that I don’t have to set up the NavMesh agent and state machine again. Then I used the Animator Set Integer node in the visual scripting graph to control the transition of the animation clip in the monster’s state machine. However, the animation system wasn’t fully implemented sucessfully and I’m still in the process of debugging. 

## W6


### Activity 1

#### Playtest Goal

The goal for playtesting today will be testing the animations, navigation of the monster, and the core mechanic of path selection in crossroads. 

Since my Milestone 1 submission, I have updated the level scene layout from greybox to an actual asset. I also adjusted the scale of the corridor to be more spacious. I also implemented the monster’s animation system based on the animator and state machine. The monster will play fly, chase, and attack animations based on the monster’s state. 

[Link to 0506Playtest Itch Build](https://xichanz.itch.io/0506playtest)

Playtest order: Xichan, Alex, Tina, Xinyan


#### Playtesting notes: 

1. The point light intensity is too high
2. If the player takes time reading the instruction they will miss the monster patrolling and never encounter it because its navigation route is too long.
3. The AI for monster navigation seems to be “dumb”; the player can easily run from her
4. The door and window can be seen through and spoil the structure of the maze
5. Replace the player’s capsule placeholder with an actual human model so that the player can see something when they look down
6. The ceiling height is a bit low.
7. The riddle at the crossroads is too simple. Peers suggested to replace riddle asking appeareance of the monster with a question about the number or color of the props.
8. The ambush monster spawns too quickly


### Activity 2

1. The multiply setting of the Blend node makes the resulting color darker and less saturated than the input colors because multiply node multiplies the RGB value of the two input colors. By multiplying the values, all of the value reduces because Unity has RGB values that range from 0~1, making both the value and the saturation lower.
2. When combining Alpha values with multiply node, the result will be more transparent because alpha also range beween 0 and 1, a multiplication of them often results in a smaller value, which leads to a more transparent result.
3. The shader gets UV values from the data of the UV unwrap from the model. This UV map tells the shader how to map the texture onto the surface of the model.
4. Yes, because different mode yields interesting and sometimes unexpected results. I've been studying Unity VFX using particle systems, and I also find parameters like color over lifetime a very useful and powerful tool in art creation.
