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


2. I added a Debug.Log() node for step 7, checking whether the animal falling stopped in the dialogue mode, and continued in the explore mode. This node is particularly useful because in dialogue mode, the cursor is disabled, and I couldn’t look upward to see whether the animal is stopped in the air. However, after I added the animal stopped by the Debug.Log() node in the dialogue graph, I’m sure now that the Set Enabled is working. 


3. The Set Cursor Lock State is relevant to my Vertical Slice because I would like to lock the player’s cursor when they interact with the riddle at each crossroad. After the player clicks on the riddle, a text will appear, similar to the dialogue state in this activity. Cursor lock in this state makes sense because otherwise the player’s view is likely to move and disrupt reading through the riddle.


4. The concept of a game state and state machine is extremely relevant to my Vertical Slice because my horror game involves a monster switching in various mutually exclusive states, with each state performing different actions. The monster will switch between states of patrol, search, chase, and attack. In patrol state, the monster wanders around in predetermine path or to a random location using Navemesh. After the player gets in the detection range of the monster, it transitions into the search state. After the player gets in the monster’s line of sight, the monster switches into chase state and pursues the player at a higher speed. If the monster gets near enough to the player, it switches to the attack state and damage player.
