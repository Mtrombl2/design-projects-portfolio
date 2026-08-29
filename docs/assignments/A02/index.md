# A2 – Truss Stress Analysis

## Objective
The Objective of this project was to design and analyze a lightweight planar truss qhilw satisfying the given geometric and loading constraints. I used static equilibrium and method of joints to determine the internal forces in each member. I then used the maximum internal force and the required safety factor to determine the minimum cross sectional area of the truss members and connecting pins. Finally, I created a CAD model of the truss to evaluate it's weight and compared the Cad results with my analytical calculations.

## Analyze
I began the analysis by identifying the given geometric constraints and loading conditions for the truss. I then determined the support reactions usng the overall free body diagram before analyzing the individual joints. After finding the internal member forces, I used the largest internal force to calculate the required cross sectional area of the truss members and then designed the connecting pins based on the largest reaction force.
### Given Constraints
The first step was to identify the geometric and loading constraints provided in the problem. The truss has a total span of 1.2m, a height of 0.3m, and 0.4m distance between the lower joints. I selected P=25kN for the applied loads and used these dimensions throughout the analysis.
![Given truss constraints](Constraints.jpg)

### Support Reactions
I created an overall free body diagram of the truss to determine the support reactions.I used the equations of equilibrium, including sum of moments equals zero, sum of forces in the x direction equals zero, and sum of forces in the y direction equals zero, to solve for the reactions at supports A and B. The resulting reactions were used as the starting point for the method of joints analysis.
![Support Reactions](Truss.jpg)

### Method of Joints
I used the method of joints to determine the internal forces in each of the truss members. At each joint, I applied the equations of equilibrium, sum of forces in the x and y direction equal zero, and resolved the angled members into their x and y components using the geometry of the truss. I used the resulting signs and directions to classify each member as being in tension or compression.

### Joint B
![Joint B](JointB.jpg)

### Joint C
![Joint C](JointC.jpg)

### Joint O
![Joint O](JointO.jpg)

### Joint D
![Joint D](JointD.jpg)

### Internal Force Results
![Internal Force Results](OverallMember.jpg)

### Max Internal Force 
After solving for the internal forces in each member, I compared the magnitudes of the member forces to identify the governing load of the truss member design. The largest internal force was 20.04 kN, which occurred in members CO and OD. Iused this value as the maximum internal force when determining the required cross sectional area of the truss members.

### Member Cross Sectional Area
I used the maximum internal member force of 20.04 kN to determine the required cross sectional area of the truss members. A safety factor of 3.5 was applied to the yield strength of the material to determine the allowable stress. The calculated minimum cross sectional area was 0.343 in^2, and this same area was used for each truss member.
![Cross Sectional Area](CrossSection.jpg)

### Total Member Length and Weight of the Truss
I calculated the length of the diagonal members using the Pythagorean theorem. With a=0.4m and b=0.3m, the diagonal member length was 0.3606m. I then added the lengths of all seven truss members to obtain a total member length of 3.0424m. I converted this length to inches so that it was consistent with the cross sectional area and steel density units. Then using V=AL, I calculated the total volume of the truss members as 41.08in^3. Using the steel density of 0.2831lb/in^3, I calculated the approximate truss weight using W=pV. The resulting truss weight was 11.61lb.

### Pin Design
I designed the connecting pins using the largest reaction load. The pins were modeled as single shear connections using hardened tool steel, a safety factor of 4, and the specified material properties.



## Decide
_Which geometry did you select, and why? This is your first open design choice in the course — defend it._

## Communicate

