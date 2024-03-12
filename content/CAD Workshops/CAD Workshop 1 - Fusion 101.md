Check out #**online-useful-resources!** in our discord for useful links to start your deep diving in!
![[Pasted image 20240312191845.png]]
---

[Fusion Help | Self-paced learning for Fusion | Autodesk](https://help.autodesk.com/view/fusion360/ENU/courses/)
![[Pasted image 20240302212356.png]]

---
[Fusion Help | Tutorials | Autodesk](https://help.autodesk.com/view/fusion360/ENU/?guid=GUID-962B7698-D862-4D7D-AB33-EEE39542DD2F)
![[Pasted image 20240302212430.png]]

---
### Fusion 360 Interaction & Keyboard Shortcuts

[Autodesk Fusion Keyboard Shortcuts, Hotkeys & Commands Guide | Autodesk](https://www.autodesk.com/shortcuts/fusion-360)
[Fusion360 Top 5 Shortcuts](https://youtu.be/eLAojK6MyPo)
- Pan: ctrl/alt - Middle Mouse
- Orbit: shift - Middle Mouse Button

---
![[Pasted image 20240312193843.png]]
---
# Fusion 360 Home Page
- Left - Teams you are in, Project Files & Folders
- Right - Blank Workspace
![[Pasted image 20240306074453.png]]
---
### Object Modification Tools
![[Pasted image 20240306074819.png]]

---
## Today's project:
![[Pasted image 20240312231044.png]]

---
## 1. Making the Carriage Chassis
![[Pasted image 20240312233227.png]]

---

![[Pasted image 20240312233245.png]]

---
## Misc Organization Stuff: Parameters
Don't worry about these just yet, they're just here for reference if you need them
- (CC = CarriageChassis) i.e. 
- CCL = CarriageChassisLength
- CCIL = CarriageChassisInnerLength
![[Pasted image 20240312235326.png]]

---
## Creating the First sketch:
![[Pasted image 20240312235716.png]]

---
### 1. Main Chassis Rectangle
- Create a Centre Rectangle with the following Dimensions
	- (Ps. when you first click to place the rectangle, you are able to type number values for width and height, toggling between both with tab)
![[Pasted image 20240313000523.png]]

---
### 2. Create Square Nut Insert Hole
- Create a 2-point rectangle, starting from the centre (black) point, and click on the bottom right corner
- Ensure that the line type is selected as Construction!!
![[Pasted image 20240313000814.png]]

---
### 2.1 Create Square Nut Insert Hole
* Use Centre Rectangle (Non- Construction)
* Add a Construction line through the centre of this new Rectangle (wait until you see the triangle icon, that means it's the midpoint)
![[Pasted image 20240313001931.png]]
---
### 2.2 Create Square Nut Insert Hole
* Create another centre rectangle (non Construction)at any point along this new line, with the below dimensions
* Then press D for the dimension tool, select the Far Edge of the 1st rectangle, and the black dot of the new rectangle, and make 5 the dimension
![[Pasted image 20240313082730.png]]
---
## Creating the Chassis pt.1
![[Pasted image 20240313083452.png]]


---
## 3.0 Extrude Main Chassis & Square Nut
- You'll notice that there are two sections that are highlightable
- Press E(for extrude) or Q(for press pull and it'll automatically turn into an extrude)
- Select both faces and extrude them up by 10mm as New Body
![[Pasted image 20240313082147.png]]

---
### 3.1 Extrude Main Chasses & Square Nut
* Once you've confirmed the extrude you'll notice that the sketch dissapears.
* Go the the sketch folder and click on the eye to make it visible again
* Once you've made it visible, extrude the Square Nut hole by 9mm
![[Pasted image 20240313082513.png]]

---

### 4. Rectangular Pattern the Square Nut Feature
- Use the Rectangular Pattern set to object type features, to pattern that extrude command we did across the bottom of the body.
- We select the long edge of the body as the axis, and the extrude feature as the object.
- Copy the values below to get a similar outcome
![[Pasted image 20240313082952.png]]
---
