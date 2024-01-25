# PureShow
 This is a simple webcoding project that allows you to improvise a laser show using just a projector. The page is meant to projected and controlled using a keyboard in a similar fashion to other lightshow projects on my profile

# How do I run it?
First you'll want to download all of the files and unzip the file. With the folder ready put it wherever you like on your system. It's important to note that all the contents within the folder should say in thier relative locations, which is to day don't move or rename contents within the folder as it may cause issues when attempting to use the webpage. 

## How to Use
This project is inteded to be used with a projector and fog machine. By projecting the contents of this site while interacting with it and filling the room or area you are projecting in with fog it should create a laser projector effect. This effect is best experiences when standing opissite to the projector in your room or area and facing the projector while the projector faces you. 

Each set of lights corresponds to a row on your keyboard. There are 4 sets of lights for 4 rows on your keybaord. Each row will have 4 keys on the left side and right side of the specified center key/s.
The "G" key can be used to switch between a instant and fade-out mode. Pressing the key will toggle the current lighting effect.
The "T" key can be used to toggle a spinning mode.
Using the Up and Down arrow keys change the fading duration to be longer and shorter respectivly.
Using the Left and Right arrow keys change the spin speed to be slower and faster respectivly. **you may need to re-apply the spin effect when changing this parameter for the changes to take place.**

###### Main Row | Colored Circles
The center of this row is the "G" key (not used as a light). The active keys include **asdf_hjkl**. Note the underscore to specify the center with a signle key center

###### Second Row | White Circles
This row is right above the main row with the center key "T". Active keys: **qwer_yuio**

###### Third Row | Colored Fill
This row is above the second row with the center keys "5" and "6". Active keys: **2345 6789**. Space in the middle shows the center but with no key inbetween the two specified center keys.

###### Fourth Row | Colored Top/Bottom Lights
This row is at the bottom, below the main row with the center keys "V" "B". Active keys: **zxcv bnm,** . Note the Comma is an included key within the set

### Second Group of Lights
In addition to the rows mentioned above by activating the caps lock key on your keyboard you can interact with a second group of lights for more dynamic shows. These lights use the same key assignments as the first group but offer more effects to choose from. All of these lights are white in color.

###### Main Row | Vertical Bars
The active keys include **asdf_hjkl**

###### Second Row | Point Lights
Active keys: **qwer_yuio**

###### Third Row | Side Bars
Active keys: **2345 6789**

###### Fourth Row | Top/Bottom Lights
Active keys: **zxcv bnm,**

## Control Center
This lighshow utlity features a control center that allows you to replay and record lightshows. This can be used to control multiple sets of lights at once with two different performances put together. In order to view the control center click the **control** key on your keyboard.

###### TURN ON/OFF ALL LIGHTS
At the very top there is a button that allows you to instantly turn on or off all the lights. The text should change to describe the action according to its last interaction.

###### Setting Music and Replay Files
If you have already recorded a replay file (Will go over how to record and save a replay further on) you can uploaded it here in the file input box. The file must be a test file and it must include the line "THIS MESSAGE ENSURES THE LIGHTSHOW KNOWS THIS IS A WORKING REPLAY FILE: 17E2B9A2CA807" at the very top followed by a new line to begin the recording data. 

Recording data consisits of the time an event occurs, then the light being affects, the action taking place, and then any specifications for that action. Below is an example:

THIS MESSAGE ENSURES THE LIGHTSHOW KNOWS THIS IS A WORKING REPLAY FILE: 17E2B9A2CA807
#Event Time	Element	I = on | 0 = Off | F = Fade when fading the time to fade is in the third tab over
3.604914	AR2	I		#This line will turn on the AR2 element
21.150575	AL4	O		#This line turns off the AL4 element
23.543904	AR2	F	0.6	#Fade the AR2 element with a duration of 0.6s
28.937615	AL1	F	0.2	#Fade the AL1 element with a duration of 0.2s
35.327256	SPIN	SET	4	#Set the spin speed at 4 seconds
46.704171	I	S1		#Enable the spin mode on the first set
78.934872	I	S2		#Enable the spin mode on the second set

If the replay file isnt working check to see if the first line matches the specific line above. This will also be indicated by a message above the preview box for the uploaded file that says "Make sure you're uploading the correct replay file". If it doesnt contain the line and the file looks to be in the correct format feel free to use any text editor and add the line at the top. **Be sure to keep the text editing in plain text format.**

Adding the music file is simple. It can be any audio file as an MP3 and will be played when you start the show.

##### Starting the show (for playback and/or recording of replay files)
There is a button with the text "BEGIN PLAYBACK", once clicked it will change to "STOP PLAYBACK" indicating a chagned action that will cease an active replay. Once the button is clicked red text and a red bar will count you down. The bar is provided to easily visuale exactly when each second starts and ends. After the countdown the replay is active and will begin playing any uploaded music file and iterating through an uploaded replay file.

If you wish to record and save a replay file be sure to check the checkbox that says "Record with playback". This will begin outputting events to a text box at the bottom of the control center that you can copy and paste into a plain text file to save the replay. I recomend highlighting the text from the bottom as I have often encountered issues accidentally highilighting an image from the lightshow with the text and causeing issues when trying to paste into a plain text file.

##### Show Runtime
This checkmark allows you to see the current time of the show and how many operations have been iterated since the begiging of the show. Runtime will be shown in the bottom left corner. Top number corresponds to the current time of the show and the bottom number corresponds to how many operations have been iterated. An operation in this case is when the code checks the current time of the show and compares it with the next command from the replay files. Often times the action taken place is to wait another cycle until the show time matches or excees the time of the next command in the replay file. In a nutshell its how many times the code has checked for something to happen from the replay file. 

##### Sliders
The Fade duration slider controlls the amount of time the fading effect takes to go from 100% opacity to 0%.
The Spin Speed slider controlls the amount of time it takes for the elements to complete one full rotation. So for a shorter time the elements will spin faster and longer times result in slower spinning.
The Fade change and Spin change sliders controll how much the arrow keys vary the respective fade or spin times per each key press. For example with Fade change set to 0.1 seconds, every time you pressed the up or down arrow key it will change the fade duration by 0.1 seconds.

##### Extra Tid Bits
After the sliders you'll find a text preview of your replay file if one is uploaded. Below that there should be a player to preview an uploaded music file. **Be sure the music player is paused when starting the the show from the "BEGIN PLAYBACK" Button.** At the very bottom is a text box that will contain the output of a new replay file if you choose to record one using the "Record with playback" checkbox.

## Bugs and Technicalities
When recording a replay file often times the message that is reqiured on the first line will disspaear and you would have to re-add it manually when saving the plain text. If the window has been inactive for a while it may not be runnig at full speed. In order to avoid timing mishaps when using the "BEGIN PLAYBACK" button to start the show click the button to turn on or off all the lights until it's fully responsive, which is to say all the lights have no delay to turn on or off when clicking the button. 

Also keep in mind to use the lightshow without recording or playing back a replay feel free to play with the lights without pressing the "BEGIN PLAYBACK" buttton. Everything should still function such as the spin and fade effects and changing between light groups.
