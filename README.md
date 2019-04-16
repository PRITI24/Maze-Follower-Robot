# Maze-Follower-Robot
Maze Following(Solving white Line path in black space)
![alt text](https:)//upload.wikimedia.org/wikipedia/en/a/a0/Simple_Maze.svg)
# THOUGHT OF METHODS FOR DOING IT
# 1.Using lsa08
FIRST IDEA CAME TO MY MIND WAS OBVIOUSLY IR SENSORS BUT I JUST STUDIED ABOUT LSA08 THEN…..AND I THOUGHT LSA08 WOULD BE MRE EFFICIENT IN MY PROJECT BECAUSE USING PID CONTROLLER,I CAN CONTROL MY MOTIONS PERFECTLY WITHOUT ANY FLUCTUATIONS……WHICH MAY HAPPEN WITH IR SENSORS….AND WHICH ACTUALLY HAPPENED…..
# 2.Using ultrasonic sensors
I THOUGHT THAT THE MAZE I HAVE BEEN GIVEN MAY BE OF WALLS ..SO I HAVE THOUGHT OF USING WALL FOLLOWERS IN THIS PROJECT….THAT IS USING ULTRASONIC SENSOR…SO I STUDIED ABOUT ULTRASONIC OPERATION IN MY CODE,MEANS HOW I CAN WRITE CODE USING ULTRASONIC SENSORS….
# 3.Using IR sensors
FINALLY I HAVE BEEN TOLD TO WRITE MY CODE USING 3 IR SENSOS ONLY……….
# VARIOUS WAYS OF SOLVING MAZE
# 1.LEFT HAND (OR) RIGHT HAND RULE
IN LEFT HAND RULE,IT ALWAYS FOLLOW LEFT SIDE……..
# 2.USING NEW VARIABLES
THIS CAN ACTUALLY WORK,HERE WE ARE STORING PATHS IN NEW VARIABLES AND CHECKING ON JUNCTION THAT IS DECISION MAKING POINTS THAT WHAT WAS MY LAST STORED PATH SO THAT I CAN KNOW WHERE I WANT TO MOVE RIGHT NOW……
# 3.USING DIFFIRENT ALGORITHMS
BY ACTUALLY DRAWING PATHS ON MAZE IT WILL BE EASY TO SOLVE MAZE BUT I WAS NOT ALLOWED TO DO SO ,SO I STICKED TO ONE METHOD ONLY..BUT THERE ARE OTHER ALGORITHMS WHICH ARE MORE EFFICIENT ,ITS TALKS ABOUT SOLVING PROBLEMS BY GRAPH,SO I DIDN’T GO IN DEPTH BECAUSE I HAD LESS TIME AND ALGO WAS COMPLEX AND OF HIGHER STANDARD……..
# Wrote a code finally with 3 IR Sensors
IF(LEFTSENSOR ON BLACK,MIDDLESENSOR ON WHITE,RIGHTSENSOR ON BLACK)
{MOVE FORWARD}..............................
IF(LEFTSENSOR ON WHITE ,MIDDLESENSOR ON WHITE,RIGHTSENSOR ON BLACK)
{MOVE LEFT ALWAYS}.............................
IF(LEFTSENSOR ON BLACK ,MIDDLESENSOR ON WHITE,RIGHTSENSOR ON WHITE)
{MOVE FORWARD WITH LOW SPEED,
CHECK IF(ALL SENSORS ON BLACK)........................
THEN MOVE RIGHT
ELSE MOVE FORWARD}
IF(ALL SENSORS ON WHITE)
{MOVE LEFT}...................
IF(ALL SENSORS ON BLACK)
{U TURN}....................
# STRUCTURE OF CODE FOR CHANGING ARRAY(1 day)
START->TAKE A NEW ARRAYB[I]->LUS THEN R->INCREMENT PREVIOUS ARRAY BY 3 AND NEW ARRAY BY 1->LUL THEN S->INCREMENT PREVIOUS ARRAY BY 3 AND NEW ARRAY BY 1->LUR THEN U->INCREMENT PREVIOUS ARRAY BY 3 AND NEW ARRAY BY 1->SUL THEN R->INCREMENT PREVIOUS ARRAY BY 3 AND NEW ARRAY BY 1->SUS THEN U->INCREMENT PREVIOUS ARRAY BY 3 AND NEW ARRAY BY 1->RUL THEN U->CHECK IN YOUR NEW ARRAY IF U IS STORED THEN REPEAT THE PROCEDURE OTHER COME OUTT OF CHANGINGING ARRAY->END
# THOUGHT OF METHODS FOR EXPLORING MAZE…….(7-8 days)
Using new variable::::
1.Check if a[i]==l && left==1 middle==0 && right==o
{move left
d++;
}
2.Check if a[i]== r && left==0 && m==0 && r==1
{
Move right
D++;
}

3.if(l==1&& m==0 && r==1)
{
Move forward;
A[i]=s;
i++;
}
If(l==0 && m==0 && r==1)
{
Move left;
A[i]=l;
i++;
If(d!=0)
{
D++;
}
}
If(l==1 && m==0 && r==0)
{
Move right
A[i]=R;
i++;
If(d!=0)
{
D++;
}
}
If(l==1 && m==1 && r==1)
{
U turn
A[i]=U;
i++;
D++;
}


If(l==0 && m==0 && r==0)
{
If(a[i-2d]==R)
{
Move right
A[i]=R;
]
If(a[i-2d]==L)
{
Move left;
A[i]=L;
}
D=0;
}
# Why my method is in efficient?
Because my method is too lengthy to be processed by microcontroller
Thus I decided to go with universal method left hand rule

# Switching from exploring loop to main loop…..
USE SWITCH AND GIVE CONDITION THAT IF SWITCH PIN IS HIGH THEN IT WILL EXPLORE OTHERWISE IT WILL CHANGE ARRAY AND GO INTO MAIN LOOP……
# Why Arduino was not working before?
WE CAN PRESUME THAT IF GROUND PIN AND VCC PINS ARE SHORTED THEN NOTHING WILL WORK EVEN ARDUINO WON’T BE ABLE TO DIFFERENTIATE PINS….
IN MY CASE IR SENSOR, BOTH PIN TOUCHED METAL PLATE AND HENCEFORTH MY ARDUINO WAS NOT WORKING
TO SEE WHAT IS THE PROBLEM START DISCONNECTING YOUR JUMPERS ONE BY ONE……
PROBLEM DIFFERENTIATE IN EVERY CASE….
# Why sensors was fluctuating on black surface?
BECAUSE ENVIRONMENT AFFECT THE IR SENSORS SOMETIME.
SOLUTION::::::::COVER IT WITH BLACK TAPE OR SOMETHING BLACK.
# Why my motors were not working properly and why it was fluctuating?
WE REMOVED WHEELS FOR CHECKING WHETHER MOTOR IS WORKING OR NOT BUT THE PROBLEM WAS KI ZIPPIES WERE LOSE ………SO ALWAYS CHECK ZIPPIES…..
Also my Hercules was not working but always remember that before declaring that your motor driver is not working always check the connectors….may be connectors are bad……
# Why switching was more efiicient than my method?
My method did not knew properly when did the exploring stopped because of inertia of motion of my wheels conditions change very easily on a particular path so one contion cannot manage same condition again ………henceforth use switching instead of adding one more condition……
# What is important before running program?
TOOLS:::
A)PORT      :
B)PROGRAMMER    :        ArduinoISP.org
C)PROCESSOR   :     ATmega2560(Mega2560)
D)BOARD     :      Arduino/Genuino Mega or Mega 2560

# SoftwareSerial.h
LEARNED ::
SOFTWARESERIAL IS REQUIRED TO PRINT ON SERIAL MONITOR
THIS IS ALSO NEEDED BECAUSE WE WANTED SERIAL COMMUNICATION ON PIN 0 AND 1 ON ARDUINO………
# My motors were not working properly....had to upload the program again
THIS WAS BECAUSE OF MY CODE AND ALSO CONNECTIONS BECOME LOSE EASILY….
# My Serial monitor was not displaying what I wanted?
Solution: 
Just remove zippies and upload your program again
# Pins for switch 
![alt text](https://1sheeld.com/wp-content/uploads/2018/08/4ac18da01c1c58927bf2cf7a0ce24f03_NX3-High-Performance-Analog-Switches-1404188438.png)
USED 2ND SWITCH ::
1.PIN:OUTPUT
2.PIN:VIN
3:PIN:GROUNG

# Refer link for switch
https://1sheeld.com/tutorials/arduino-relay-lamp/





