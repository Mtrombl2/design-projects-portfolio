# A3 – Parametric Design and FEA
## Objective
The objective of this assignment was to parametrically design a hollow aluminum bar subjected to an axial load while limiting the maximum deflection to 0.009 inches. The design was then analyzed using FEA to compare the deflection and evaluate the von Mises stress and factor of safety.
## Analyze
### Initial Design and Hand Calculations
I began by choosing an applied load of 425 lbf and dimensions of 1.0 in for the width, 0.5 in for the height, and 0.1 in for the wall thickness. I then calculated the cross sectional area of the hollow bar and used the direct tension elongation equation to determine the required length while maintaining a maximum deflection of 0.009 in.

### Creating The Beam in CAD
I started by sketching the outer cross section of the bar and extruded it to my calculated length. I then created another rectangular sketch on the end face using my wall thickness and used an extrude cut to remove the inside material, creating a hollow beam.

### Parameters 
After creating the beam, I assigned parameters for Young's modulus, maximum deflection, applied load, width, height, and wall thickness. I then created relations in Creo to calculate the cross-sectional area and bar length which were very similar to my hand calculations. Finally, I connected the parameters to the corresponding CAD dimensions so that changes to the parameters would automatically update the model.

### Material Selection
After creating the parameters, I assigned Aluminum Wrought as the material for the beam. I selected this material because it's Young's modulus is approximately 10.22 x 10^6 psi, which falls within the required range. This also closely matched the 10 x 10^6 psi I used in my hand calculations.
### FEA
After completing the CAD model and assigning the material, I performed a static FEA in Creo. I fixed one end of the beam and applied a 425 lbf tensile load at the opposite end in the axial direction. I then created and ran a static analysis using the assigned load and constraint.

### Deflection Map
After running the static analysis, I generated a displacement map to determine the maximum axial deflection of the beam. The FEA resulted in a maximum deflection of 0.0087978 in, which was very close to the maximum design deflection of 0.009 in used in my hand calculations.

### Von Mises Stress Map
I then generated a von Mises stress map to evaluate the maximum stress in the beam. The FEA resulted in a maximum von Mises stress of 1.828 Ksi. Using the specified aluminum yield strength of 40 Ksi, I calculated a factor of safety of approximately 21.88, indicating that the beam remains well below the yield strength under the applied load.



## Decide
### Hand Calculation Versus FEA
My parametric hand calculation used a maximum axial deflection of 0.009 in, while the FEA resulted in a maximum deflection of 0.0087978 in. This resulted in a percent difference of approximately 2.25%. The results were very close because the hand calculation and FEA used the same geometry, loading conditions, and very similar material properties. The small differences may be due to the slightly different Young's modulus of the Aluminum Wrought material used in Creo and numerical approximations in the FEA. I would trust the hand calculation slightly more because the direct tension equation directly represents this simple axial loading condition, while the FEA serves as confirmation of the analytical result.

###Pin Hole Stress Calculation
I then considered the effect of adding a substantial pin hole to the bar without redoing the FEA. I assumed a hole to width ratio of d/W=0.50, which gave a stress concentration factor of Kt=2.16 from Peterson's stress concentration relation. Using the nominal stress away from the hole, I estimated the peak stress at the hole to be approximately 3.53 Ksi. Compared to the aluminum yield strength of 40 Ksi, this resulted in a factor of safety of approximately 11.3, so the design woudl still easily pass with the pin hole.

## Communicate
One of the biggest challenges I had during this assignment was setting up the FEA in Creo. I initially could not access Creo because my license expired and then I couldn't access the simulate extension because it was not installed. After installing the extension, I was able to set up the constraints, apply the axial load, and successfully run the analysis. I also learned how important it is to verify the direction of an applied load before running the FEA. Overall, this assignment helped me better understand how parametric modeling, hand calculations, and FEA can be used together to verify a design. This assignment took me about 5 hours to do all of the work, but I waited days for Solid Works to download, and it is still downloading as I am typing and it took hours to renew my Creo license.
### Finished Beam Part
[Beam Model](beam.prt.2)
