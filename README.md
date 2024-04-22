# IMGD4000Portfolio

I was part of the development team for Spaceward for IMGD 4000.  
Here is the website for the game: [https://datapointbeing.github.io/Spaceward-Website](https://datapointbeing.github.io/Spaceward-Website)  

My key roles during development centered around the movement mechanics, level/gameplay design, deployable build testing  

The biggest proportion of these was with creating the movement mechanics for Spaceward. Since it is a 3D playformer, the movement is very important to how the player interacts with the game.  
The main implementations were: Separately unlockable double jump & dashing, air movement improvements, and coyote time jumping.  

The biggest challenge faced in those implementations was with coyote time. The concept behind coyote time is to allow the player a window of time after running off a platform to be able to jump. This is a mechanic in many platformers such as Celeste. It makes the game feel more fair overall to the player. The issue was getting this to functional properly with the built in jumping function and when double jumping was enabled. Unreal Engine 5 considers a jump from the ground as +1 to the current jumps counter, but jumping in air after running off a platform as +2. This makes it so that you can't simple give a temporary extra jump to the player during the time window.  

My solution for this challenge was to check for what type of jumping that player had unlocked and if they had used the air jump. Since by default you can't jump in the air, this just meant resetting the jump count to default. With double jump however two possible values needed to be in place to allow for the player to always be able to use at least one air jump regardless of if they jumped during the coyote time window.  

Here is the blueprint script that updates the player's unlocking of double jump along with enabling coyote time:  

![image](https://github.com/Michaellsterk/IMGD4000Portfolio/assets/34323970/46417a20-07a9-49ca-b731-250ded5280c4)

Some smaller challenges were time management for implementing art assets and creating a deployable build of the game. The solution we came to for art assets was to increase the amount of communication and updates between the Tech and Art teams as well as instituting a cutoff for when we'd stop adding or changing elements that would require additional assets. The deployable build issues came from some specific blueprint functions only working within a development deployment and not a shipping one. We tried to avoid using these and utilized development deployements when needed. The key difference between developement and shipping deployements are soft safety features are removed in lieu of better performance. Our game was optimized enough to not need the additional performance.  

# [Get clarity on what to include for architectural diagrams]

Overall the main things learned was to keep constant communication between all team members. Use the live variable viewing features of Unreal Engine 5 to see exactly what is changing in the background when different functions are called to help debug problems. And lastly to ensure that a deployable build of our game currently possible with what we created.  

The Spaceward development team chose to use GitHub as our primary version control software. We all utilized the desktop UI version of GitHub. We did this as it was the easiest to understand and see what changes were made and to exlcude files for versioning. We also made sure to make branches whenever major changes or additions were being worked on to not potentially harm the main branch. GitHub was not used for version control of art assets due to file size limitations and the team not wanting to risk GitHub LSF costs.  
