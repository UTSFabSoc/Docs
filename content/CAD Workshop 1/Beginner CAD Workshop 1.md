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
# Making Train Chassis


---



---
## Making Curved Train Tracks



---
## Create New Component and....
![[Pasted image 20240306102748.png]]

---
## Set Parameters
* Create new parameters for the Rail Length, Width, Bend Radius & the Angle.
* by default, the unit is mm, but you'll have to change the unit to deg. for the angle
![[Pasted image 20240306105805.png]]]]



---
## Create New Sketch
* set the dimensions for the sketch to be the parameters we've just set
![[Pasted image 20240305220335.png]]
---
### Add 2 Point Rectangle Floating Nearby

![[Pasted image 20240306104828.png]]]]
---
### Route 1: Use Sketch Dimension and ctrl click on existing dimensions
- YOu can click and drag the new rectangle to adjust it's position
![[Pasted image 20240305220623.png]]
![[Pasted image 20240306104907.png]]
---
### Delete New Rectangle's Horizontal & Vertical Constraints
![[Pasted image 20240306095339.png]]
---
### Create Extending line, (Bend Radius) Perpindicular to 1st Rectangle, as a Construction line

![[Pasted image 20240306105607.png]]
---
### Create Center Point arc (RailAngle) from the end of Bend Radius to Inner corner of the 1st Rectangle 
![[Pasted image 20240306110115.png]]
---
### Create Offset at (Rail Width) from inner bend, to outer edge
![[Pasted image 20240306110259.png]]

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
### Finish Sketch, and Rename to Curved Rail, & Save as External Component


---
### Create Plane Along Path
![[Pasted image 20240305215421.png]]
---
### Start new Sketch & Design Steel Girders using Center Rectangle
![[Pasted image 20240305215804.png]]

---
### Select & Delete Construction Lines & Trim Overlap
![[Pasted image 20240305215938.png]]
---
![[Pasted image 20240305220141.png]]

