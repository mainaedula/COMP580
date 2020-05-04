Danielle du Preez and Maina Edula

May 4, 2020

***COMP 580 Final Project: The Eco-Architect***

**Description of the Project**

*Theme:* Our game is a role-playing limited text-based “choose your adventure” game, with 5 sets of choices that require the player to acquire in-game information in order to select the most appropriate choice. The player arrives at an island town that has burned down, and now needs to help rebuild it in an environmentally sustainable manner. The player achieves a final score in the game according to the quality of their choices at each stage.

*Gameplay:* There are 5 rounds that the player has to complete to rebuild the town, and for each round the player has to choose between a good and bad option. The 5 rounds are: rebuilding the houses, replanting trees, supplying water to the town, helping the townspeople start farming, and supplying power to the town. In each round the player is presented with two options of materials/methods/etc and has to consult with various townspeople in order to choose the best option. The score is calculated at the end depending on which option the player chose in each round.

There is a mayor and 7 townspeople (an environmentalist, an engineer, two business people, and three regular inhabitants), each in their own grid location on the game map. Each round is played as follows:

The mayor presents the initial task for the round (ex: choose a material to rebuild houses)

The player goes to the two business people who each offer different choices (ex: concrete vs wood)

The player can visit the environmentalist for her expert opinion on how the choices will affect the island ecosystem (ex: wood requires deforestation)

The player can visit any of the 3 townspeople who will give more subjective pros and cons for the choices (ex: I want concrete because it is sturdier and safer for my children)

Upon hearing all this information, the player makes a choice, goes back to the corresponding businessperson to accept their proposal, and then to the engineer to start building.

*Navigation:* The game is based on a 3x3 grid, which can be navigated with the arrow keys. One townsperson lives in each grid square. A single key press corresponds to moving one grid square, or N/S/E/W on the game map. In keeping with the tradition of text adventure games, there is no visible map, and the player must maintain awareness of their spatial orientation based on a description of the grid location they are at. In addition to a verbal description (“Town Hall, South Square”) each grid square has a unique background score that plays after all the narration is finished. 

*Controls:* Movement is controlled with an arrow key press as described above. Once the player has navigated to the desired grid square, they can interact with the townsperson who lives there by pressing the spacebar. They can leave to another square at any time by pressing arrow keys. All choices presented in interactions with townspeople will be binary. If the townsperson offers the player a choice (ex. “I can supply everyone with lumber for us to rebuild our houses. That’s a good idea, right?”), the player can accept the offer by pressing any letter key or exit the interaction by pressing the spacebar. 

*Intended Audience:* This game is intended for children with blindness or visual impairment, but should have a similar play experience for both blind and sighted children. The game is grid-based so it requires spatial understanding. We utilize the arrow keys, the spacebar, and audio-based cues. Each move the character is verbally described and different sound feedback plays depending on what square they land on and what choice they select.

*Technologies, Frameworks, and Libraries Used:* We initially used an open-source library and software called Quest 5 (https://docs.textadventures.co.uk/quest) to create the basic functionality and story arcs. We chose Quest because it allows users to host their games on its website, and includes basic functionality, like grid-based gameplay. Quest 5, like other game engines, allows specific functions to be added to a basic frame via additional programming. However, Quest does not appear to be designed to handle keypress events in browser while also smoothly integrating sounds that play on keypress. So, after creating our project in Quest, we were not satisfied with the end product, which was only able to run on Quest's downloaded engine on windows.

We decided to rebuild the project using standard the HTML/CSS/JavaScipt combo. Using JavaScript and JQuery allowed us to implement the keyboard controls with significantly improved functionality, while smoothly allowing sounds to play. We used JQuery to handle keyboard events anywhere in the window and to update the text content of the page. We used JavaScript standard audio class to manipulate audio.

*How to Build and Deploy:* We chose to put all of our scripts into a single HTML file. First, all keypress events lead to traversal through the intro dialogue. Future keypress events are delegated to functions. We allocated one function for movement with arrowkeys that sets the new location and controls the audio that plays on entry of a particular grid square. The basis for our grid locations was simply indexing them 0 through 8 from right to left, top to bottom of the grid.

We allocated two other functions to handle the "spacebar" events which allowed users to "talk" to the non-player character in the grid square. Another function handled the "select" events which allowed players to accept a binary choice using any letter key. Within the spacebar and select functions, we selected the appropriate actions based on several values, including the choice ID, the location, and what round the came was on. This was just a matter of using case statements and making an appropriate set of variables to track the player's progress.

Any game of the same grid-based choose-your-own-adventure-with-audio structure can be built in this manner. We could distill the outline for out game into a generic template that would simple require developers to fill in the dialogue and sound files. To deploy, we put the main html file in a folder with the mp3 sound files and cloned it to a GitHub pages repo. Any webhost can host this type of project, but GitHub pages is a good option because it is convenient and simple to use.

*Problems Encountered:* The major problem we encountered was that after we added all the sound and disabled command bar to use arrow keys and spacebar, the game no longer became functional on the web player. The only way to play it is by downloading the desktop version, which only works on Windows OS. We did not anticipate this problem because Quest was functioning well until close to the end of development. We elected to use Quest because we expected that it would simplify our work by easily tracking the story arcs. If we had known this issue would arise, we would have built the whole game with JavaScript from the start.

The primary bug with HTML/CSS/JavaScript is that sound cannot autoplay in Chrome regardless of browser settings until the user has interacted with the page. We wanted the whole game to be audio-driven so that a blind user could play independently, but unfortunately we had to require a click on the window for the audio to begin playing. However, the first like "press any key to continue" should still be able to be read by a screen-reader.

*Future Work:* Future expansion on this project could incorporate more obstacles within the rounds or choices with more interference--for example, choosing wood in round 1 would affect the options available for round 2. There could also be levels of increasing difficulty to progress through where each level requires more thought and consideration than the last, and maybe also has higher stakes if you perform poorly.

In terms of technology, maybe the game could be adapted to be used with a touch-screen tablet. It is grid based anyway, so instead of arrow keys, the player could use their finger to navigate along the grid using haptic feedback and perhaps even different voice commands to control actions. This may involve utilizing NLP software as well. 

