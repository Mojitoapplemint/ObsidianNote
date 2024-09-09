# User use case
- Goal: Reach the end of the game
- External initiator: Actor
- Start Condition: SheepyTime not in initial state
- Stop Condition: Determine winner(s)
- Clear Value: Play until the end of the game
- Main Path: Main success from user journey

# Green: Before any phase
- Since we are using java, the java garbage collection will take care of orphaned objects
- Create First Sheep Token from Model in initial craetion
- The player know when it called its night
- **Add instance variable of phase to fence and pass it ?? phase object parameter during construction?**
![[Pasted image 20240123233936.png|400]]
- 
# Orange: Racing Phase
![[Pasted image 20240123233401.png|400]]

# Purple: Resting Phase
![[Pasted image 20240123232629.png|400]]
- If we were (??), a better design would be initialize model would reset the (???) of objects 
- Pass Players parameter as an arraylist from Model at a method called setPlayers in the Reference Tile after all players are initialized 

# Red 
- set gameboard: set fence on board
- Array with arraylist as slots, for gameboard, for scoreboard, loop it
- Each token move in board by itself
- Each token has a ???
![[Pasted image 20240123233019.png]]

- In constructor, pass Reference Tile to First Sheep Token as instance variable