# A8 – Gears

## Objective

The objective of this assignment was to design and assemble a functional gearbox that could be easily assembled and disassembled while maintaining proper alignment, strength, and clearance between components.

The gearbox uses two spur gears with a gear ratio of 24:9 and a specified output torque of 1.25 in-lbf at 1100 rpm.

The main objectives of this project were to:

- Analyze the input and output shafts to determine whether their specified diameters could safely transmit the required torque and power.
- Design and select suitable journal bearings based on pressure, surface velocity, PV rating, material selection, and wall thickness.
- Develop a two-piece gearbox housing that provides sufficient gear clearance and supports the shafts and bearings.
- Incorporate removable fastening hardware to allow the gearbox to be assembled and disassembled.
- Use SOLIDWORKS to create the housing, model the shafts, and assemble the gearbox components.
- Document engineering calculations, preliminary sketches, design modifications, challenges, and lessons learned throughout the project.
  


## Analyze


## Design and Analysis

### Input Shaft Analysis

The first step of the gearbox design was analyzing the input shaft to determine whether its specified diameter could safely transmit the required torque and power.

I began by identifying the known and unknown variables. The input shaft had a diameter of 0.125 inches and a length of 1 inch. Using the given gear ratio of 24:9 and the output conditions, I calculated an input torque of 0.46875 in-lbf and a rotational speed of approximately 2933.3 rpm.

#### Knowns, Unknowns, and Free-Body Diagram

I created a free-body diagram (FBD) to represent the torque acting on the shaft. The diagram shows the applied input torque and the opposing torque from the gear. This helped establish rotational equilibrium and identify the loading conditions for the stress analysis.

![Input Shaft Knowns and Unknowns](images/input-shaft-knowns.jpg)

![Input Shaft Free-Body Diagram](images/input-shaft-fbd.jpg)

#### Shaft Stress Calculations

To determine the maximum shear stress, I used the torsion equation for a solid circular shaft. This equation relates the transmitted torque to the shaft diameter and polar moment of inertia.

The calculated maximum shear stress was approximately **1,222.3 psi**.

I then used the power-transmission shaft equation referenced in Machinery's Handbook and discussed in the course lecture to estimate the shaft's power capacity.

The calculated results were:

- Maximum shear stress: **1,222.3 psi**
- Shaft power capacity: **0.0716 hp**
- Required transmitted power: **0.0218 hp**

![Input Shaft Handwritten Calculations](images/input-shaft-calculations.jpg)

#### Material Selection and Design Conclusion

I selected AISI 1045 steel as the proposed shaft material because it is commonly used for mechanical shafts and offers suitable strength for power-transmission applications. The final CAD model was assigned AISI 1045 cold-drawn steel.

The calculated power capacity exceeded the required transmitted power. Therefore, the original 0.125-inch shaft diameter was considered sufficient under the assumptions of the course's power-transmission design equation.

This analysis allowed me to retain the original shaft diameter without increasing its size, helping keep the gearbox compact.


### Output Shaft Analysis

The next step was analyzing the output shaft to determine whether it could safely transmit the required output torque. I followed the same engineering process used for the input shaft, beginning with the known variables, creating a free-body diagram, and calculating the resulting shear stress and power capacity.

The output shaft had a specified diameter of 0.250 inches, a length of 1 inch, an output torque of 1.25 in-lbf, and a rotational speed of 1100 rpm.

#### Knowns, Unknowns, and Free-Body Diagram

I first identified the known and unknown variables needed for the analysis. I then created a free-body diagram showing the applied torque from the output gear and the opposing torque transmitted to the load.

This diagram helped me understand how the shaft experiences torsional loading and provided the basis for calculating the maximum shear stress.

![Output Shaft Knowns and Unknowns](images/output-shaft-knowns.jpg)

![Output Shaft Free-Body Diagram](images/output-shaft-fbd.jpg)

#### Shaft Stress and Power Calculations

I used the torsion equation for a solid circular shaft to determine the maximum shear stress. Because the output shaft has a larger diameter than the input shaft, it experiences a lower shear stress despite transmitting more torque.

The calculated maximum shear stress was approximately **407.4 psi**.

I also evaluated the shaft's power capacity using the short-shaft design relationship adopted from the course material. During the analysis, I initially applied the same power-transmission equation used for the input shaft. After reviewing the design assumptions, I revised the calculation using the short-shaft coefficient of 38.

The calculated results were:

- Maximum shear stress: **407.4 psi**
- Estimated shaft power capacity: **0.4523 hp**
- Required transmitted power: **0.0218 hp**

![Output Shaft Handwritten Calculations](images/output-shaft-calculations.jpg)

#### Material Selection and Design Conclusion

I selected AISI 1045 steel for the output shaft, consistent with the input shaft material. AISI 1045 cold-drawn steel was assigned to the shaft model in SOLIDWORKS.

The calculated power capacity exceeded the required power, indicating that the specified 0.250-inch shaft diameter was sufficient under the assumed design conditions.

The output shaft was therefore retained at its original diameter. This analysis reinforced the relationship between shaft diameter, transmitted torque, and torsional shear stress.


### Journal Bearing Analysis and Material Selection

After completing the shaft analysis, I moved on to designing and selecting the journal bearings. The purpose of the bearings was to support the rotating shafts, maintain proper alignment, and reduce friction between the shafts and the gearbox housing.

The gearbox required four journal bearings, with two supporting the input shaft and two supporting the output shaft.

#### Gear Force Analysis

Before selecting the bearings, I needed to determine the forces generated by the meshing gears.

I selected an 18-tooth input pinion and a 48-tooth output gear, both with a diametral pitch of 48 and a pressure angle of 20 degrees. These gears maintained the required gear ratio of 24:9.

Using the gear force equations from the course lecture, I calculated the tangential force responsible for transmitting torque and the radial force that pushes the gears apart.

The calculated forces were:

- Tangential force: **2.50 lbf**
- Radial force: **0.910 lbf**
- Resultant gear force: **2.66 lbf**

For the preliminary bearing analysis, I assumed the gear was centered between two equally spaced bearings. This allowed the resultant load to be divided equally between the bearings.

The estimated load on each bearing was **1.33 lbf**.

![Gear Force and Bearing Load Calculations](images/gear-force-calculations.jpg)

#### Bearing Pressure, Velocity, and PV Analysis

The next step was determining the operating conditions of the journal bearings.

I selected a preliminary bearing length of 0.250 inches for both shafts. Using the projected bearing area, I calculated the bearing pressure caused by the applied load.

I then calculated the surface velocity using the shaft diameter and rotational speed. Finally, I multiplied the bearing pressure by the surface velocity to determine the PV value.

The PV value was important because it helped evaluate whether the selected bearing material could operate under the expected loading and rotational speed.

The calculated results were:

| Parameter | Input Bearing | Output Bearing |
|---|---|---|
| Shaft Diameter | 0.125 in | 0.250 in |
| Bearing Length | 0.250 in | 0.250 in |
| Applied Load | 1.33 lbf | 1.33 lbf |
| Bearing Pressure | 42.6 psi | 21.3 psi |
| Surface Velocity | 96.0 ft/min | 72.0 ft/min |
| PV Value | 4,090 psi-ft/min | 1,534 psi-ft/min |

![Journal Bearing Pressure Calculations](images/bearing-pressure-calculations.jpg)

![Journal Bearing Velocity and PV Calculations](images/bearing-pv-calculations.jpg)

#### Bearing Material Selection

After calculating the pressure, velocity, and PV values, I compared the results with the bearing material limits discussed in the course lecture.

I selected **SAE 841 oil-impregnated bronze** because it provides good wear resistance and is commonly used in sleeve bearings. The oil contained within the porous bronze helps reduce friction during shaft rotation.

The preliminary calculations showed that the pressure, velocity, and PV values for both bearings were below the material limits presented in the lecture.

This made SAE 841 bronze a suitable preliminary material choice for the gearbox.

#### McMaster-Carr Bearing Selection

After selecting the bearing material, I used McMaster-Carr to identify commercially available bearings compatible with the shaft dimensions.

**Input Journal Bearing**
- McMaster-Carr Part: 1688K321
- Material: Oil-embedded bronze
- Shaft Diameter: 0.125 in
- Housing Bore: 0.250 in
- Bearing Length: 0.250 in

**Output Journal Bearing**
- McMaster-Carr Part: 7634N11
- Material: Oil-embedded bronze
- Shaft Diameter: 0.250 in
- Housing Bore: 0.375 in
- Bearing Length: 0.250 in
- Design: Flanged sleeve bearing

The flanged output bearing required additional consideration during the housing design because its flange needed to remain outside the housing while the cylindrical portion fit into the bearing opening.

The catalog dimensions were used to create the bearing seats in SOLIDWORKS. The final design also required consideration of running clearances and bearing operating limits.

![Input Journal Bearing Selection](images/input-bearing-selection.jpg)

![Output Journal Bearing Selection](images/output-bearing-selection.jpg)

#### Journal Bearing Design Conclusion

The bearing calculations provided the information needed to select suitable materials and preliminary dimensions.

The selected bronze bearings satisfied the material-level pressure, velocity, and PV checks based on the assumed loading conditions. Their nominal dimensions also matched the bearing seats designed into the gearbox housing.

This analysis helped establish the bearing locations and support geometry used during CAD modeling. Final verification of the manufacturer-specific operating limits and fits remained an important design consideration.


### Journal Bearing Wall Thickness Analysis

After selecting the journal bearing materials, I determined the wall thickness needed for the bearings. This was important because the bearings needed to support the rotating shafts while fitting securely inside the gearbox housing.

#### Bearing Dimensions and Calculations

I used the inside and outside diameters of the selected journal bearings to determine their nominal wall thickness.

The wall thickness of a cylindrical bearing can be calculated using:

$$
t = \frac{D_o-D_i}{2}
$$

Where:
- t = Bearing wall thickness
- D_o = Outside diameter
- D_i = Inside diameter

For the input bearing, I used an inside diameter of 0.125 inches and an outside diameter of 0.250 inches.

For the output bearing, I used an inside diameter of 0.250 inches and an outside diameter of 0.375 inches.

The calculated nominal wall thickness for both bearings was:

**t = 0.0625 inches**

![Journal Bearing Thickness Calculations](images/bearing-thickness-calculations.jpg)

#### Bearing Thickness Design Considerations

I selected commercially available sleeve bearings with nominal wall thicknesses of 0.0625 inches. The selected dimensions were consistent with the bearing materials and preliminary operating conditions evaluated earlier in the project.

The bearing pressure calculations helped evaluate the suitability of the bearing material. However, projected bearing pressure is not equivalent to uniform internal pressure acting on a hollow cylinder. Therefore, the geometric wall thickness calculation alone does not establish the minimum thickness required to prevent material failure.

A separate structural stress assessment would be needed to fully verify the wall thickness under the applied bearing loads.

#### Incorporating Bearing Dimensions into SOLIDWORKS

After selecting the bearing dimensions, I incorporated them into the gearbox housing.

I created circular bearing seats with inside diameters matching the outside diameters of the selected bearings.

Because the housing floor was only 0.125 inches thick, I added raised circular bearing supports with a height of 0.125 inches.

This created a total nominal bearing support length of 0.250 inches, matching the selected journal bearings.

The raised supports provided additional material around the bearing openings without requiring the entire housing floor to be thicker.

![SOLIDWORKS Bearing Support Design](images/bearing-supports.jpg)

#### Design Conclusion

Both selected bearings had a nominal wall thickness of 0.0625 inches. Their dimensions were incorporated into the SOLIDWORKS housing to provide the appropriate bearing seats and support lengths.

This stage demonstrated the importance of considering both component geometry and loading conditions when designing bearing supports. Although the selected dimensions were suitable for the preliminary CAD layout, a complete minimum-thickness stress verification would require additional analysis.


### Gearbox Housing Concept and Design Changes

After completing the shaft and bearing calculations, I began designing the gearbox housing. The purpose of the housing was to protect the gears, maintain proper shaft alignment, support the journal bearings, and allow the gearbox to be assembled and disassembled.

#### Initial Housing Sketch

I started by creating a hand-drawn concept sketch of the gearbox. My original design used a rounded housing that followed the general shape of the two gears.

The sketch included the 18-tooth input pinion, 48-tooth output gear, shaft openings, bearing locations, and four fastening locations.

The calculated center distance between the gears was **0.6875 inches**, which was important for maintaining the proper gear alignment and meshing relationship.

I also included preliminary clearances around the gears and housing walls to prevent contact during operation.

![Original Gearbox Housing Sketch](images/original-housing-sketch.jpg)

#### Two-Piece Housing Design

The assignment required the gearbox to be assembled and disassembled. To accomplish this, I designed the housing with two separate components:

- A bottom housing that supports the gears, shafts, and journal bearings.
- A removable top cover that provides additional shaft support and access to the internal components.

I chose to use four bolts and nuts to fasten the two housing halves together. This allowed the top cover to be removed when installing, inspecting, or replacing components.

I also created a side-view sketch to demonstrate how the two housing halves would fit together.

![Gearbox Housing Side View](images/housing-side-view.jpg)

#### Design Modification: Rounded to Rectangular Housing

When I began modeling the housing in SOLIDWORKS, I decided to change my original rounded design to a rectangular housing.

I made this modification because a rectangular design was easier to sketch, dimension, extrude, and modify using SOLIDWORKS.

The rectangular shape also provided straight edges for positioning the mounting tabs and additional space for arranging the internal components.

Another advantage was that the rectangular design would simplify several manufacturing operations compared with creating a rounded housing that closely followed the gear profiles.

Although the external shape changed, I maintained the important functional requirements from my original sketch, including the gear center distance, shaft locations, bearing supports, and removable fastening system.

![Rectangular Gearbox Housing in SOLIDWORKS](images/rectangular-housing.jpg)

#### Preliminary Housing Dimensions

I selected the following dimensions for the SOLIDWORKS model:

| Feature | Dimension |
|---|---|
| Housing Length | 2.75 in |
| Housing Width | 2.25 in |
| Bottom Housing Height | 0.50 in |
| Internal Cavity Length | 2.50 in |
| Internal Cavity Width | 2.00 in |
| Cavity Cut Depth | 0.375 in |
| Wall Thickness | 0.125 in |
| Floor Thickness | 0.125 in |
| Top Cover Thickness | 0.125 in |

These dimensions provided a starting point for creating the two-piece housing. Final component clearances and fits were considered during assembly.

#### Design Conclusion

The initial sketch helped me understand the spatial arrangement of the gearbox components before beginning CAD modeling.

Changing from a rounded housing to a rectangular housing demonstrated how engineering designs can evolve during development.

The rectangular design simplified the modeling process while maintaining the intended function of the gearbox. This modification was an important part of my design process because it allowed me to develop a housing that was easier to construct and assemble in SOLIDWORKS.


### SOLIDWORKS Modeling and Assembly Process

After completing my engineering calculations and preliminary housing sketches, I began creating the gearbox in SOLIDWORKS. My goal was to develop a two-piece housing that could support the shafts, bearings, and gears while allowing the gearbox to be assembled and disassembled.

#### Bottom Housing Design

I started by creating a rectangular sketch measuring 2.75 inches by 2.25 inches. I then used the Extruded Boss/Base feature to extrude the rectangle to a height of 0.50 inches.

Next, I created a smaller rectangle measuring 2.50 inches by 2.00 inches on the top face. I used Extruded Cut with a depth of 0.375 inches to create the internal gear cavity.

This left a 0.125-inch floor and 0.125-inch walls around the housing. The cavity provided space for the gears and shafts while maintaining the structure of the housing.

![Bottom Housing and Gear Cavity](images/bottom-housing-cavity.jpg)

#### Bearing Supports and Shaft Openings

After creating the housing cavity, I added the bearing locations based on the dimensions from my previous calculations.

The two shaft centers were separated by 0.6875 inches to maintain the correct gear center distance.

I created two circular bearing supports with the following dimensions:

- Input bearing support: 0.500-inch outside diameter
- Output bearing support: 0.625-inch outside diameter
- Input bearing opening: 0.250-inch diameter
- Output bearing opening: 0.375-inch diameter

I extruded the circular supports upward by 0.125 inches. Combined with the original housing floor, this provided a nominal support length of 0.250 inches.

I then used Extruded Cut to create openings through the housing for the journal bearings and shafts.

These supports allowed me to provide additional material around the bearings without increasing the thickness of the entire housing.

![Bearing Supports in SOLIDWORKS](images/bearing-supports-cad.jpg)

#### Mounting Tabs and Bolt Holes

Next, I created four circular mounting tabs around the outside corners of the housing.

Each tab had a diameter of 0.375 inches and extended along the housing height.

I then created four 0.196-inch clearance holes for the #8-32 fastening bolts.

The purpose of these tabs was to provide a secure way to connect the bottom housing and removable cover while keeping the fasteners outside the internal gear cavity.

![Bottom Housing Mounting Tabs](images/housing-mounting-tabs.jpg)

#### Removable Top Cover

After completing the bottom housing, I created a separate top cover directly within the SOLIDWORKS assembly.

I used the existing housing as a reference to ensure the cover aligned with the base.

The cover was modeled as a 2.75-inch by 2.25-inch rectangle with a thickness of 0.125 inches.

I added four matching mounting tabs and bolt holes so the cover could be fastened to the bottom housing.

I also created two upper bearing openings and circular supports to help maintain the alignment of the input and output shafts.

The top cover was designed to be removable so the internal gearbox components could be accessed for assembly and maintenance.

![Top Cover CAD Model](images/gearbox-top-cover.jpg)

#### Gear and Shaft Assembly

Once both housing components were modeled, I began assembling the internal gearbox components.

I downloaded the spur gear CAD models from McMaster-Carr and inserted them into my SOLIDWORKS assembly.

The selected gears were:

- Input pinion: 18 teeth, 48 diametral pitch
- Output gear: 48 teeth, 48 diametral pitch
- Pressure angle: 20 degrees
- Gear center distance: 0.6875 inches

I used Concentric Mates to align each gear with its shaft location and Distance Mates to establish preliminary clearance above the lower bearing supports.

I also created the two shafts using the specified diameters of 0.125 and 0.250 inches, with each shaft measuring 1 inch long.

The shafts were assigned AISI 1045 cold-drawn steel in SOLIDWORKS.

After inserting the shafts, I used assembly mates to align them with their respective gears and lock their relative rotation to represent the press-fit connections.

![Gears and Shafts Inside Housing](images/gear-shaft-assembly.jpg)

#### Journal Bearing Installation

I inserted four journal bearings into the assembly, with two supporting each shaft.

I used Concentric Mates to align the bearings with their corresponding housing openings and Coincident Mates to position them within the bearing supports.

The output bearings were flanged, so I positioned their flanges against the exterior housing surfaces while their cylindrical portions extended into the bearing openings.

The bearings were intended to remain stationary while the shafts rotated through them.

![Journal Bearings Installed](images/journal-bearings-installed.jpg)

#### Fastening Hardware

After assembling the main components, I inserted four #8-32 machine screws and matching hex nuts.

I used Concentric Mates to align the bolts with their mounting holes and Coincident Mates to position the bolt heads against the top cover.

I then installed the nuts underneath the housing to complete the fastening arrangement.

This design allows the top cover to be removed without permanently joining the two housing components.

![Gearbox Bolts and Nuts](images/gearbox-fasteners.jpg)

#### Gear Motion Testing

After completing the component assembly, I used the SOLIDWORKS Mechanical Gear Mate to connect the rotations of the input and output gears.

I entered a gear ratio of 48:18, matching the selected tooth counts.

I then tested the motion by rotating the input and output shafts in the assembly.

Both gears rotated together in opposite directions, demonstrating that the Gear Mate and the shaft-to-gear rotational constraints were functioning correctly.

This test confirmed the intended rotational relationship between the gears. It did not, by itself, verify all physical clearances.

I also used SOLIDWORKS Interference Detection to inspect the assembly and observed a reported interference near the fastening hardware. This was identified as an item requiring verification before finalizing the design.

![Completed Gearbox Assembly](images/final-gearbox-assembly.jpg)

#### CAD Development Conclusion

The SOLIDWORKS modeling process allowed me to transform my original housing concept into a complete gearbox assembly.

Throughout the process, I learned how to use extrusions, cuts, circular bearing supports, assembly mates, and imported CAD components to create a mechanical system.

The final CAD assembly demonstrated the intended rotational relationship between the input and output gears and provided a removable two-piece housing for the internal components.

The modeling process also highlighted the importance of checking component alignment, assembly constraints, and possible interference before considering a design fully verified.



## Decide

### Final Gearbox Design Selection

After completing the engineering calculations, preliminary sketches, and SOLIDWORKS assembly, I decided to keep the rectangular two-piece gearbox design.

I selected this design because it provided sufficient space for the gears, shafts, and journal bearings while allowing the housing to be assembled and disassembled using removable bolts and nuts.

Although my original concept used a rounded housing, the rectangular design was simpler to model and provided convenient mounting locations for the fastening hardware.

### Shaft and Bearing Design Decisions

Based on my shaft calculations, I decided to maintain the specified input and output shaft diameters.

The input shaft had a calculated maximum shear stress of 1,222.3 psi, while the output shaft had a maximum shear stress of 407.4 psi.

Both shafts had estimated power capacities greater than the required transmitted power of 0.0218 hp under the selected course design equations.

I also decided to use AISI 1045 steel for both shafts because of its mechanical strength and suitability for rotating shaft applications.

For the journal bearings, I selected SAE 841 bronze because the preliminary pressure, velocity, and PV calculations were within the material limits discussed in the course lecture.

I incorporated raised bearing supports into both housing halves to accommodate the selected bearing lengths without increasing the overall housing thickness.

### Final Assembly Evaluation

After assembling the gearbox in SOLIDWORKS, I tested its rotational motion using a Mechanical Gear Mate.

The 18-tooth input gear and 48-tooth output gear rotated in opposite directions with the intended 48:18 gear ratio.

I also confirmed that rotating the input shaft caused the connected gears and output shaft to rotate.

This demonstrated that the rotational assembly mates were functioning as intended.

The two-piece housing and removable fastening hardware also provided a way to access the internal components during assembly and maintenance.

![Final Gearbox Assembly](images/final-gearbox-assembly.jpg)

### Design Challenges and Improvements

Several challenges occurred throughout the design process.

One challenge was correctly positioning the gears and shafts using SOLIDWORKS assembly mates. I had to adjust concentric and distance mates to establish the intended alignment and preliminary clearances.

Another challenge was creating the bearing supports without accidentally filling the bearing openings during extrusion. I corrected this by adjusting the selected sketch contours.

I also encountered an interference warning involving the fastening hardware during the assembly evaluation.

Although the gearbox demonstrated the intended rotational motion, the interference warning and final dimensional clearances required additional verification.

If I continued improving the design, I would focus on confirming the bearing fits, checking gear and housing clearances, and refining the fastening hardware.

![Gearbox Assembly Evaluation](images/gearbox-design-evaluation.jpg)

### Final Design Decision

Overall, I decided to retain the rectangular two-piece gearbox housing with AISI 1045 steel shafts, bronze journal bearings, and removable fastening hardware.

This configuration met the main objectives of creating a compact gearbox assembly with the intended gear ratio and rotational relationship.

The project demonstrated how engineering calculations, material selection, CAD modeling, and assembly testing can be combined to develop a mechanical design.

While the completed SOLIDWORKS assembly demonstrated the intended motion, additional physical-fit and interference verification would be necessary before manufacturing the gearbox.



## Communicate

### Final Project Summary

Throughout this project, I applied engineering calculations, material selection, mechanical design, and CAD assembly techniques to develop a two-piece gearbox.

I began by analyzing the input and output shafts to determine their torsional stresses and power capacities. I then calculated the journal bearing loads, pressures, surface velocities, and PV values to select suitable bearing materials and dimensions.

After completing the calculations, I developed a preliminary housing sketch and used SOLIDWORKS to model and assemble the gearbox.

The completed CAD assembly included:

- A rectangular bottom housing and removable top cover
- An 18-tooth input gear and 48-tooth output gear
- Two AISI 1045 steel shafts
- Four bronze journal bearings
- Four machine screws and matching hex nuts

I tested the assembly by rotating the shafts and observing the resulting gear motion. Both gears rotated in opposite directions with the intended gear ratio.

The project allowed me to connect engineering analysis with practical mechanical design and assembly techniques.

![Completed A8 Gearbox Assembly](images/final-gearbox-assembly.jpg)

### Lessons Learned

One of the most important things I learned from this project was how engineering calculations influence CAD design decisions. The shaft and bearing calculations helped determine the dimensions and materials that needed to be incorporated into the gearbox.

I also learned more about creating mechanical assemblies in SOLIDWORKS, especially how different mates control the position and movement of components.

**Some of my main lessons learned included:**

- Understanding the importance of concentric and distance mates when positioning mechanical components.
- Learning how to use a Gear Mate to establish the rotational relationship between two gears.
- Understanding why journal bearings must remain stationary while the shafts rotate inside them.
- Recognizing how bearing dimensions affect the design of the housing and its support features.
- Learning how to modify an original design concept to simplify modeling and manufacturing.
- Recognizing the importance of checking component interference and clearances before finalizing a mechanical assembly.

### Challenges and Mistakes

I encountered several challenges while completing this project.

One issue occurred when creating the upper bearing supports. During extrusion, I accidentally filled the bearing openings. I corrected this by adjusting the sketch and selecting only the ring-shaped regions for extrusion.

Another challenge occurred when inserting the input shaft into the assembly. SOLIDWORKS would not allow the shaft to move into position because the component was fixed. Changing the component from Fixed to Float allowed me to complete the concentric mate.

I also had difficulty selecting certain surfaces when applying mates because other components obstructed my view. I learned to temporarily hide components to access the necessary faces.

During the assembly process, I received a computer memory warning. This reinforced the importance of saving frequently and managing complex CAD assemblies carefully.

Finally, I observed an interference warning near the fastening hardware during SOLIDWORKS evaluation. This showed me the importance of inspecting the finished assembly rather than relying only on its appearance.

![SOLIDWORKS Assembly Process](images/assembly-process.jpg)

### Time Spent

The project required time for calculations, preliminary design, CAD modeling, component selection, assembly, and documentation.

| Activity | Time Spent |
|---|---|
| Shaft analysis and calculations | [Enter hours] |
| Journal bearing analysis and selection | [Enter hours] |
| Preliminary housing sketches | [Enter hours] |
| SOLIDWORKS housing modeling | [Enter hours] |
| Component assembly and mating | [Enter hours] |
| Verification and documentation | [Enter hours] |
| **Total Time** | **[Enter total hours]** |

### Final Reflection

Overall, this project gave me a better understanding of the process involved in designing and assembling a mechanical gearbox.

The most challenging portion was creating the SOLIDWORKS assembly and ensuring that each component was properly positioned.

However, working through these challenges improved my understanding of mechanical design, assembly constraints, and the relationship between individual components.

I was able to complete the gearbox CAD assembly and demonstrate the intended rotational relationship between the input and output gears.

This project helped me improve my CAD modeling and engineering problem-solving skills while showing the importance of evaluating a design throughout the development process.

---

## Appendix — CAD Files and References

### SOLIDWORKS CAD Files

The following files contain the gearbox assembly and the custom components created during this project.

- [Complete Gearbox Assembly](cad/A8_GEARBOX_ASSEMBLY.SLDASM)
- [Bottom Gearbox Housing](cad/A8_Gearbox_Base.SLDPRT)
- [Removable Top Cover](cad/A8_Gearbox_Cover.SLDPRT)
- [Input Shaft](cad/A8_Input_Shaft.SLDPRT)
- [Output Shaft](cad/A8_Output_Shaft.SLDPRT)

The assembly also incorporates downloaded McMaster-Carr CAD components, including the gears, journal bearings, bolts, and nuts.

### Component Supplier

The commercially available gearbox components were selected using:

[McMaster-Carr](https://www.mcmaster.com/)

### Engineering References

- MEGR 2156 — Designing a Gearbox: Shafts, Gears & Journals
- Machinery's Handbook — Shaft design and bearing material references
- SOLIDWORKS — CAD modeling and assembly tools

### Additional Project Images

![Gearbox Housing Concept Sketch](images/original-housing-sketch.jpg)

![Gearbox Interior](images/gear-shaft-assembly.jpg)

![Final Gearbox CAD Model](images/final-gearbox-assembly.jpg)


