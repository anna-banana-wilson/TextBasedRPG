# Text Based RPG: Smith College Zombie Apocalypse

This text based adventure game is called Smith College Zombie Apocalypse. The game in based at Smith Collge in Northampton, Massachussetts, and takes you through a variety of challenges. 


# ABOUT THE DESIGN AND PROCESS

Visual diagram of the class structure:
![image](https://user-images.githubusercontent.com/72671700/160195859-efb907bc-1094-45bb-a6d8-f1c76cc0874e.png)

The most important part of our design was the custom objects we built. We realized that games are inherently very object oriented, and we had many specific purposes for our different objects. For example, a building contains several specific things: intro text, enemy encounter, win condition, lose condition, items contained, etc. These are the following custom objects we created:

- Node: This is an object we made that represents a place on the map. It points in the four cardinal directions, and it also holds an Area.

- Area: This object represents an area on the map, holding info about things like the Buildings that the area contains and intro text.

- Buildings: These are located within the Areas. Each Buildings object contains intro text, info about what you may encounter within that building, how to win that encounter, how to lose, and items contained in the building.

As you can see, each of these objects holds a very specific set of information, so it made the most sense to create custom objects.

NOTE: You may notice that we have employed a lot of switch cases. This is because writing a bunch of if elses is space-inefficent, takes longer to code, and to quote Anna, "looks gross." The other two concur. 

We also used some built-in classes. We used arrayLists a couple times, for the inventory and the list of abilities the player had gained. The reason for this was that it just needed to hold some strings, but it needed to be resizable because the player gains more and more items and abilities as the game progresses. In another case, we used the built in class HashMap in a funky way. This is how it was initialized:

HashMap<String, HashMap<String, String>> responses;
 
It’s a HashMap of HashMaps. The reason for this was we started out with a HasMap of just different actions (verbs) and response sentences that the computer could print out in response to them. That is obviously a key and value, as a HashMap would have. We soon realized that we needed to go a layer deeper: each verb also has a set of items that it can be said with. So, we made another HashMap within each verb, as its data.

As for alternative data structures, the main alternative we could have used was for our graph. Ours is a very base-level structure we made ourselves, with each node having four pointers, and the nodes on the edge of the map not pointing to anything (we had to prevent the player from entering these nodes). Alternatively, we could have used Guava. It would have been helpful because we wouldn’t have had to code it from scratch, but we already made our Node class before we talked about it in class, and it works just fine for our purposes. It also probably would've been a big learning curve, as we heard from other teams during Demo day.

## COMMANDS AND MAP OF OUR WORLD

## HELPFUL ADVICE
You cannot return to a building once you've completed it, so make sure you take everything you can while you're there! There's no limit on how much you can carry. 

## LIST OF COMMANDS
You can type more than two words, but the extra words will be ignored. For example, you cannot travel to Chapin Lawn by typing "travel to chapin". Instead, type "travel chapin". You could also type "travel chapin lawn". Capitalization is ignored. 

- to travel by foot
  - "walk" or "go", followed by cardinal direction
  - for example, "walk north" or "go w"
- to travel by bike
  - bike must be unlocked
  - "travel", "bike", or "ride" followed by area name
  - for example, "travel burton" or "travel burton hall"
- to check inventory
  - "check", "items", "inventory"
- to use items
  - "use" followed by item name
  - for example, "spray extinguisher" and "use extinguisher" will both work
  - Hint: If you get stuck, try "use". Might not always work, but give it a shot.  
- to take items
  - "take" or "grab", followed by item name
- to leave a building
  - "exit", "leave", or "run away"
- to enter a building
  - "enter" followed by building name
  - for example, "enter burton" or "enter seelye hall"
- to give items 
  - "give" followed by item name
- to eat items 
  - "eat" followed by item name
- to play items 
  - "play" followed by item name
- to throw items 
  - "throw" followed by item name

Note: some commands only work for specific items. When in doubt, try "use"!

## LIST OF AREAS

The game map is divided into separate areas, each of which can contain buildings you can enter. The available buildings in each area are listed when the player travels there. Here are all the available areas and the words that can be used to access them:

- Burton Lawn (burton)
- Chapin Lawn (chapin)
- Seelye Lawn (seelye)
- The area around College Hall (college, collegehall)
- Green Street (green, greenst, greenstreet)
- The area around Ford Hall (ford) 
- President's House (empty, think of it as a placemark to visualize where you are) 

Three areas along Mill River and College Lane are also available to travel to:
- The upper shore (upper, uppershore)
- The middle shore (middle, middleshore)
- The lower shore (lower, lowershore)

Some areas are actually the borders of the map, and cannot be traveled to, so if the text for these areas show up, go in a different direction. These areas are listed below:
- Elm Street (elm)
- West Street (west)
- Paradise Pond (pond, paradise, lake)

## SAVING AND LOADING 
You can save your progress throughout the game in case you lose at some point. 

to save: 
- "save"

The game also automatically saves your progress every time you use your bike to travel to a new location. 

If you lose, the game takes you back to where you last saved or where you last traveled to with your bike. If you haven't saved or biked anywhere, you will have to restart from the very beginning of the game. 

to load: 
- "load" 

Maybe you forgot where you left off, so the "save.txt" file lists (in this order):
  - what items are in your inventory
  - where you currently are in terms of area and building
  - the remaining items from buildings you might want to pick up
  - how many of the buildings you have completed
  - which abilities you have unlocked
  - which minibosses you have defeated (Hint: The order is "N" and "J")
- You can then play again from where you left off. 

# SPOILER ALERT

There are quite a few challenges in this game and places where you may lose!

Several of the buildings have their own challenges upon entry. We're not going to tell you which, because we really want you to explore and figure stuff out. 

There are two minibosses in this game that you will have to defeat somehow. The hints as to where they are and what tools you need might be on the pieces of paper you pick up throughout the game. 

There is also a final boss you will have to defeat in order to win the game. This final boss situation will be unlocked once you've defeated both minibosses, in addition to the items you unlocked by defeating said minibosses. Do you remember where the posters/flyers/leaflets told you to escape to? At the very beginning? 

Have fun!

## SUPER SECRET KONAMI CODE
If you want to beat the game quickly, here's how:
- Go to Tyler (Green Street) and take the candy
- Go to McConnell (middle shore) and give the candy to Jordan
  - You have now acquired the inflatable raft!
- Go to Hillyer (Seelye Lawn) and take the book
- Go to Ford (Ford area) and give the book to Nick
  - You have now acquired the flare gun!
- Go to the Botanical Garden (upper shore) and take the oar
- Go to the lake (travel far west) and do the following:
  - inflate boat
  - get in boat / enter boat
  - use oar / paddle / row
  - use flare gun / fire flare gun


# CREDITS
Created by Anna Wilson, Jade Lee, and Skye Worster December 2021
