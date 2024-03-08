# Fusion 360
---
[Fusion Help | Self-paced learning for Fusion | Autodesk](https://help.autodesk.com/view/fusion360/ENU/courses/)
![[Pasted image 20240302212356.png]]

---
[Fusion Help | Tutorials | Autodesk](https://help.autodesk.com/view/fusion360/ENU/?guid=GUID-962B7698-D862-4D7D-AB33-EEE39542DD2F)
![[Pasted image 20240302212430.png]]

---
## Home Screen Overview
- Left - Teams you are in, Project Files & Folders
- Right - Blank Workspace
![[Pasted image 20240306074453.png]]
---
### Object Modification Tools
![[Pasted image 20240306074819.png]]

---
#### Making A Train & Tracks
- By Now you should have created your own private Team, Create a New Project Labelled "CAD Workshops"
- Create a new Folder Labelled "Workshop 1: Train & Tracks"

![[Pasted image 20240306150846.png]]

---
## Making Curved Train Tracks



---
## Create New Component and....
![[Pasted image 20240306102748.png]]

---
## Set Parameters
* Create new parameters for the Rail Length, Width, Bend Radius & the Angle.
* by default, the unit is mm, but you'll have to change the unit to deg. for the angle
![[Pasted image 20240306105805.png]]



---
## Create New Sketch
* set the dimensions for the sketch to be the parameters we've just set
![[Pasted image 20240305220335.png]]
---
### Add 2 Point Rectangle Floating Nearby

![[Pasted image 20240306104828.png]]
---
### Use Sketch Dimension and ctrl click on existing dimensions
- You can click and drag the new rectangle to adjust it's position
![[Pasted image 20240305220623.png]]
![[Pasted image 20240306104907.png]]
---
### Delete New Rectangle's Horizontal & Vertical Constraints
![[Pasted image 20240306095339.png]]
---
### Create Extending line, (Bend Radius) Perpindicular to 1st Rectangle, as a Construction line

![[Pasted image 20240306105607.png]]
---
### Create Center Point arc 
(RailAngle) from the end of Bend Radius to Inner corner of the 1st Rectangle 
![[Pasted image 20240306110115.png]]
---
### Repeat For Outer Edge
![[Pasted image 20240306113338.png]]

---
### Use Coincident Constrain to attach bottom left of the 2nd Rectangle to the inner Curve modifier.
- Then do the same for the outer edge
![[Pasted image 20240306110719.png]]

---
### Difference Between Free Floating Sketches & Dimensioned Sketches
![[Pasted image 20240306110845.png]] ![[Pasted image 20240306103219.png]]
* Blue Lines: Not Dimensioned
* White Lines: Is Dimensioned

---
### Dimensioning The Sketch
* Constrain the long Edges to be parallel & one of the sides and bottom lines to be perpendicular
* You will now notice that the sketch has a red lock
![[Pasted image 20240306110948.png]]
---
### Turn All Solid Lines (except the outer rail lines) into construction lines
- Select All and press X (or select Construction Linetype)
![[Pasted image 20240306111614.png]]

---
### Create Construction line attached to the midpoint of the curved bend
- (This will act as our mirror line when we duplicate the connection bars between the rails)
![[Pasted image 20240306111749.png]]
---
### Finish Sketch, and Rename to Curved Rail, & Save to your Train & Rail Project Folder
![[Pasted image 20240306113105.png]]

---
### Create Plane Along Path of outer rail
![[Pasted image 20240306113210.png]]
---
### Start new Sketch & Design Steel Girders using Center Rectangle
- Feel free to make your own custom design too if you'd like!
![[Pasted image 20240305215804.png]]

---
### Select & Delete Construction Lines & Trim Overlap
![[Pasted image 20240305215938.png]]
---
![[Pasted image 20240305220141.png]]
---
### Project the Midpoint of the 1st Rectangle to the current Sketch
- This gives us reference to the midpoint, allowing us to mirror the design across.
![[Pasted image 20240306120405.png]]

---
### Create a Vertical Floating Construction Line & Constrain it to the new points' midpoint
![[Pasted image 20240306120728.png]]
---
### Select the Mirror Tool, Double click the Rail Object & select the newly created middle line as Mirror Line
![[Pasted image 20240306120758.png]]

---
### Finish, Rename (RailSketch) & Save

---
### Perform Sweep Command using the Rail Sketch & the Rail Path
- make Sure Chain Selection is turned on (this just auto selects any connecting paths, as our rail is technically made of 3 separate paths)
- (You can select both profiles we made & the paths should auto fill!)
![[Pasted image 20240306121846.png]]

---
### Congrats, You should now have a rail path!
![[Pasted image 20240306122302.png]]

---
### Now to design the Sleepers...
- Create an Offset plane & set the offset to 0
- Create a new sketch, and project the bottom, Inner Plane & the midplane we made during the rail sketch!
![[Pasted image 20240306122945.png]]
---
### Select & Set these new Projection Lines as Construction Lines
![[Pasted image 20240306135925.png]]
---
### Create Sleepers using Centre Rectangle at the Midpoint
- atm, I used 28x5mm for the sleepers, although you are welcome touse the line and curve tools to make your own custom designs!
- DONT FORGET TO CONSTRAIN THE FAR EDGES OF THE SLEEPERS TO THE RAIL
![[Pasted image 20240306123228.png]]

---
### Create Line Tracing the Middle line we used earlier! Ensure it is set as Construction & USE THE FIX/UNFIX Constraint to keep it in place
![[Pasted image 20240306124000.png]] 

---
### Use Move Command to Create Copy of a sleeper
- Use the Move/Copy Command (FIRST CLICK CREATE COPY CHECKBOX)
- Then just move it out of the way, distance does not matter, as we'll be constraining it to the curved mid-line
![[Pasted image 20240306124149.png]]

---
### Add Construction Line to find it's center point, Dimension Sides, Pareallel & Perpendicular Constrain the sides and Corners
![[Pasted image 20240306125005.png]]

---
### Midpoint & Perpendicular Constrain it to the middle Line
![[Pasted image 20240306125117.png]]


---
### Extrude The Straight Rail Sleeper & Curved Rail Sleeper
- Select the Sleepers & Extrude them by 3mm
- Extrude as separate "extrude" actions, we want them as separate "features"
![[Pasted image 20240306142143.png]]
---
### Create More Parameters!!!
* Create the Following new parameters: 
* StraightSectionSleeperNumber: 3
* StraightSectionSleeperOffsetDistance: (Rail_Length/StraightSectionSleeperNumber) * 10mm
* CurvedSectionSleeperAngle: Rail_Angle / CurvedSectionSleeperNumber * 2
* CurvedSectionSleeperNumber: 3
![[Pasted image 20240306143745.png]]

---
### Pattern The **FEATURE**, Not the SKETCH or BODY
![[Pasted image 20240306141944.png]]

---
### Pattern the Curved Sleepers
Create an Axis perpendicular to Face at Point. Use the point we used mark the radius of the bend, and any face that's facing up
![[Pasted image 20240306142928.png]]
---
### Create Circular Pattern
using the Parameters we made earlier
![[Pasted image 20240306143322.png]]
---
### Setting Up Mirror Plane
- Select Construct, Plane at Angle
- Set angle to -90. This will serve as our mirror plane
![[Pasted image 20240306133639.png]]

---
### Mirroring Features
- First Select Mirror, Set Object Type to Features, Compute Type to Optimized
- Select Mirror Plane as the one we just created
- **IT IS ALWAYS MORE EFFICIENT TO MIRROR/PATTERN ECT. FEATURES INSTEAD OF BODIES, & COMPUTE TO OPTIMIZED**
- Select the features from the Timeline!
![[Pasted image 20240306144010.png]]

---
### Now why did we go through all that?
- Why did we go through all that when all we had to do was use pattern on path?!?!?!
- Because it's important to know that there's no right way to solve a problem using CAD
	- **But there is a faster way!!!**
![[Pasted image 20240306144303.png]]

---
### Select All Bodies & Combine
![[Pasted image 20240306135422.png]]

---
# Congratulations! Your Railway is complete
- And due to the magic of parametric modelling, you can always change the dimensions through the parameter menu after the fact