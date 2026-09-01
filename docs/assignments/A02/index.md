# A2 – Truss Stress Analysis

## Objective
The Objective of this project was to design and analyze a lightweight planar truss while satisfying the given geometric and loading constraints. I used static equilibrium and method of joints to determine the internal forces in each member. I then used the maximum internal force and the required safety factor to determine the minimum cross sectional area of the truss members and connecting pins. Finally, I created a CAD model of the truss to evaluate it's weight and compared the CAD results with my analytical calculations.

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
After solving for the internal forces in each member, I compared the magnitudes of the member forces to identify the governing load of the truss member design. The largest internal force was 20.04 kN, which occurred in members CO and OD. I used this value as the maximum internal force when determining the required cross sectional area of the truss members.

### Member Cross Sectional Area
I used the maximum internal member force of 20.04 kN to determine the required cross sectional area of the truss members. A safety factor of 3.5 was applied to the yield strength of the material to determine the allowable stress. The calculated minimum cross sectional area was 0.343 in^2, and this same area was used for each truss member.
![Cross Sectional Area](CrossSection.jpg)

### Total Member Length and Weight of the Truss
I calculated the length of the diagonal members using the Pythagorean theorem. With a=0.4m and b=0.3m, the diagonal member length was 0.3606m. I then added the lengths of all seven truss members to obtain a total member length of 3.0424m. I converted this length to inches so that it was consistent with the cross sectional area and steel density units. Then using V=AL, I calculated the total volume of the truss members as 41.08in^3. Using the steel density of 0.2831lb/in^3, I calculated the approximate truss weight using W=pV. The resulting truss weight was 11.61lb.
![Total Member Length and Weight of Truss](Weight.jpg)

### Pin Design
I designed the connecting pins using the largest reaction load. The pins were modeled as single shear connections using hardened tool steel, a safety factor of 4, and the specified material properties.
![Pin Design](Shear.jpg)

### Minimum Pin Cross Sectional Area
For the single shear connection, I used the shear stress relationship and applied the required safety factor to determine the minimum pin cross sectional area.
![Minimum Pin Cross Sectional Area](Apin.jpg)
### Combined Pin weight
After determining the required pin area, I calculated the volume and weight of the pins using their geometry and the material density 0.278 lb/in^3. The combined weight of the pins was determined to be 0.061lb.
![Combined Pin Weight](WeightP.jpg)



## Decide
### Overall Length and Height
I first concerted the required overall dimensions from meters to inches so that I could use them in Creo. I then created one large rectangle using the specified overall length and height and extruded it 0.5 in. This rectangle established the overall boundary of my truss and provided the starting geometry for the rest of my design.
![Rectangle](Rectangle.jpg)
![Extrusion](Extrusion.jpg)

### Extrusion Cut 1
I created two triangular sections on the ends of the rectangular truss boundary. I dimensioned the triangle using the corrected diagonal length which also required me to recalculate the weight. The triangles were then used to cut away the unwanted material, creating the diagonal openings for the truss design.
![Recalc](Recalc.jpg) 
![Cut1](Cut1.jpg)
![Extrude 1](Extrude1.jpg)
### Extrusion Cut 2
I created the center triangular section of the truss using the calculated diagonal geometry. I then used the sketch to remove the unwanted material form the rectangular body, creating the center opening while maintaining the required member thickness of 0.686 in , which I calculated from the minimum cross sectional area.
![Calculation](0.686.jpg)
![Cut2](Cut2.jpg)
### Extrusion Cut 3
I created the two remaining triangular sections using the calculated truss geometry. I then used an extruded cut to remove the material from both ends of the truss, leaving the required member thickness of 0.686 in and completing the main truss geometry.
![Cut 3](Cut3.jpg)
![Extrude3](Extrude3.jpg)
### Material selection
I chose low carbon steel as the closest available material for the truss. This will provide sufficient strength for the expected loads.
![Material](Material.jpg)

### Pin Creation
I designed the connecting pins using the largest reaction load from my truss analysis. I calculated the minimum required pin cross sectional area using the shear stress, safety factor, and specified material properties. I then used a large pin size in my CAD model than the minimum calculated size. I chose the larger pins to provide extra strength and stability in the connections and to make the pins easier to model and assemble. Although my hand calculation from earlier did not account for this, I accounted for it in my final weight calculation. The large pins increased the volume which will increase the overall weight of the truss.
![Pins](Pins.jpg)
![Pin Extrude](PinExtrude.jpg)

### Compared CAD weight with Hand Calculation Weight
I compared the final weight obtained from my CAD model with my original hand calculation. The CAD weight was slightly heavier because of the larger connected pins and using a low carbon steel material instead of the exact material that was given. I accounted for these differences when determining the final CAD weight. My calculated truss weight was 12.69 lb and my calculate pin weight was 0.061lb. The overall weight of the truss from CAD was 13.6106lb which is a 7.26 % difference. My calculated weight, was close but since I made the pins bigger than my original design, it made the weight increase a lot more.
![Weight](WeightCAD.jpg)
## Communicate

### Key engineering lessons learned
This project taught me the importance of checking calculations before applying them to a CAD design. I learned that changing the truss geometry, member dimensions, or pin sizes can affect the final weight and design. I also learned that engineering decisions require balancing strength, stability, and weight rather than focusing on only one factor. Finally, comparing my hand calculations with my CAD model helped me understand how important design assumptions and material election can affect the final result. This project also shopwed me how important being prepared with time is, especially while working with both calculations and CAD. I realized that I was some what rusty with CAD, which made the modeling process take longer than expected. In the future I plan to start the CAD creation earlier and give myself more time to trouble shoot and make changes. I also want to improve my CAD skills and may explore SolidWorks and also taking a class online. Hopefully though my portfolio this year you will be able to see how much I improve on the design process.

### Finished Cad design 
[CAD Truss Model](./truss.prt.2)





