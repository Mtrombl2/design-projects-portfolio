# A7 – [FEA On Bracket]

## Objective
The objective of this project was to use Finite Element Analysis (FEA) in SOLIDWORKS to evaluate and improve the structural performance of a previously designed bracket. Three design iterations were analyzed to reduce maximum von Mises stress, minimize displacement, and improve the factor of safety while maintaining the required geometry and material. Mesh convergence studies were performed using a 7% tolerance to evaluate the consistency of the simulation results. The overall goal was to improve the bracket's performance under the applied load and work toward a target factor of safety of 4.


## Analyze
I used SOLIDWORKS Simulation to perform static Finite Element Analysis (FEA) on three bracket designs. Each design used 6061-T6 aluminum and a total applied load of 1,200 lbf, with a fixed constraint applied to the upper bracket.

For each design, I tested different mesh densities and compared the maximum von Mises stress, displacement, and factor of safety. I used a 7% mesh convergence tolerance to evaluate the consistency of the simulation results.
### Design I – Original Bracket
I began by analyzing my original bracket from the previous assignment. The bracket was made of 6061-T6 aluminum with a yield strength of approximately 275 MPa.

![Original Bracket](images/design1-original.png)

#### FEA Setup

I created a static study in SOLIDWORKS Simulation. A fixed constraint was applied to the interior horizontal surface of the upper bracket to represent the rigid T-beam support. A total downward force of 1,200 lbf was applied to the cylinder, representing two 600 lbf strap forces.

![Fixed Support](images/design1-fixed.png)

![Applied Force](images/design1-force.png)

#### Mesh Convergence

I started with a coarse mesh and refined it to a medium mesh to check convergence. The coarse mesh contained 2,808 elements, while the medium mesh contained 7,559 elements.

![Coarse Mesh](images/design1-coarse.png)

![Medium Mesh](images/design1-medium.png)

The changes in maximum stress, displacement, and factor of safety were all below the required 7% convergence tolerance.

#### Initial FEA Results

The stress plot revealed high stress near the vertical support (Feature B). The simulation also produced a stability warning, so I checked for underconstrained bodies. SOLIDWORKS reported that the model was fully constrained.

![Von Mises Stress](images/design1-stress.png)

![Displacement](images/design1-displacement.png)

![Factor of Safety](images/design1-fos.png)

![Constraint Diagnostic](images/design1-diagnostic.png)

These results helped identify Feature B as the main area to improve for Design II.

### Design II – Increased Support Thickness

For my second design, I increased the thickness of Feature B (the vertical support) from 0.1141 in to 0.200 in. I made this change because the original FEA showed high stress around the vertical support. My goal was to reduce stress and displacement while minimizing the additional mass.

![Design II Modified Bracket](images/design2-bracket.png)

#### Geometry Modification

I used SOLIDWORKS Equations to modify Feature B while keeping the original T-beam fit dimensions unchanged. I also verified the dimensions using the Measure tool to ensure the bracket maintained its required fit.

![Updated Equations](images/design2-equations.png)

![Fit Verification](images/design2-fit.png)

#### Mesh Convergence

I performed three mesh iterations to evaluate the consistency of the FEA results.

- Coarse Mesh: 2,865 elements
- Medium Mesh: 8,264 elements
- Fine Mesh: 24,216 elements

![Coarse Mesh Details](images/design2-coarse.png)

![Medium Mesh Details](images/design2-medium.png)

![Fine Mesh Details](images/design2-fine.png)

The medium-to-fine mesh comparison showed a 4.47% change in maximum von Mises stress and a 1.75% change in maximum displacement. Both were below the required 7% convergence tolerance.

#### FEA Results

The increased thickness reduced the maximum stress and displacement compared with Design I. However, the bracket still did not meet the required factor of safety of 4.

![Von Mises Stress](images/design2-stress.png)

![Displacement](images/design2-displacement.png)

![Factor of Safety](images/design2-fos.png)

These results showed that increasing Feature B's thickness improved the bracket's performance, but additional reinforcement was needed for Design III.

### Design III – Reinforced Bracket
For my third design, I made several modifications to improve the bracket's strength and stiffness. I increased Feature B's thickness from 0.200 in to 0.500 in, added fillets to reduce stress concentrations, and extended the cylinder to provide more room for the strap.

![Design III Modified Bracket](images/design3-bracket.png)

#### Geometry Modifications

The following changes were made in SOLIDWORKS:

- Increased Feature B thickness to 0.500 in
- Added a 0.150-in fillet at the lower cylinder connection
- Added a 0.250-in fillet at the upper support connection
- Increased cylinder length from 1.000 in to 1.500 in
- Maintained the original T-beam fit dimensions

These modifications were intended to strengthen the connections between the bracket features and reduce bending and stress concentrations.

![Updated Equations](images/design3-equations.png)

![Lower Fillet](images/design3-lower-fillet.png)

![Upper Fillet](images/design3-upper-fillet.png)

#### Mesh Convergence

I performed three mesh iterations to evaluate the consistency of the simulation results.

- Coarse Mesh: 3,519 elements
- Medium Mesh: 7,960 elements
- Fine Mesh: 25,087 elements

![Coarse Mesh Details](images/design3-coarse.png)

![Medium Mesh Details](images/design3-medium.png)

![Fine Mesh Details](images/design3-fine.png)

The medium-to-fine mesh comparison showed a 1.08% change in maximum von Mises stress and a 0.63% change in maximum displacement. Both were within the required 7% convergence tolerance.

#### FEA Results

The final design showed a substantial reduction in stress and displacement compared with the previous designs. The maximum von Mises stress was below the material's yield strength, although the factor of safety remained below the target of 4.

![Von Mises Stress](images/design3-stress.png)

![Displacement](images/design3-displacement.png)

![Factor of Safety](images/design3-fos.png)

The results demonstrated that increasing the support thickness and adding fillets improved the bracket's structural performance. The longer cylinder also provided additional exposed surface for the strap.

### Additional Design Exploration – Gusset Reinforcement

After completing Design III, I wanted to continue improving my bracket to get closer to the target factor of safety of 4.

I added a reinforcing gusset to the back of Feature B to strengthen the connection between the vertical support and the cylinder. I then performed another FEA simulation to evaluate the effect of this modification.

![Gusset Reinforcement](images/gusset-design.png)

#### Von Mises Stress Results

- Design III Maximum Stress: 221.6 MPa
- Gusset Design Maximum Stress: 135.0 MPa
- Stress Reduction: 39.1%
- Estimated Factor of Safety: 2.04
- Target Factor of Safety: 4.0

![Gusset Von Mises Stress](images/gusset-stress.png)

Adding the gusset reduced the maximum von Mises stress by approximately 39.1%. This showed that reinforcing the support connection was effective at improving the bracket's structural performance.

Although the modified bracket still did not achieve the target factor of safety of 4, the additional experiment demonstrated how reinforcing high-stress regions can improve a design.

## Decide
### Design Comparison

After completing the FEA simulations, I compared the three bracket designs to determine which modifications improved structural performance. I evaluated maximum von Mises stress, displacement, minimum factor of safety, and mass.

| Parameter | Design I | Design II | Design III |
|---|---|---|---|
| Maximum Von Mises Stress (MPa) | 1457 | 851 | 221.6 |
| Maximum Displacement (mm) | 6.741 | 2.508 | 0.2522 |
| Minimum Factor of Safety | 0.189 | 0.32 | 1.24 |
| Mass (lb) | 0.34 | 0.35 | 0.43 |
| Fine/Final Mesh Elements | 7,559 | 24,216 | 25,087 |

### Evaluation of Results

Design III performed the best of the three required designs. Compared with Design I, the maximum von Mises stress decreased by approximately 84.8%, and the maximum displacement decreased by 96.3%. The minimum factor of safety increased from 0.189 to approximately 1.24.

These improvements were achieved by increasing Feature B's thickness, adding fillets, and extending the cylinder. However, the bracket's mass increased from 0.34 lb to 0.43 lb.

### Additional Gusset Evaluation

After completing Design III, I experimented with adding a gusset to the back of Feature B. This further reduced the maximum von Mises stress from 221.6 MPa to approximately 135.0 MPa, representing a 39.1% reduction.

The estimated factor of safety increased to approximately 2.04. Although this additional result was not verified through a complete mesh convergence study, it showed that reinforcing the support connection could further improve the bracket.

### Final Decision

Design III was the best-performing design among my three completed iterations. It achieved significant reductions in stress and displacement while maintaining the required T-beam fit dimensions.

Although the target factor of safety of 4 was not achieved, the design process demonstrated substantial improvement. If I continued developing the bracket, I would focus on further reinforcing the cylinder-to-support connection while considering the additional mass and maintaining the required geometry.

The project demonstrated the importance of using FEA results to guide engineering decisions rather than making geometry changes based solely on appearance.

## Communicate
### Lessons Learned

- Learned how to use SOLIDWORKS Simulation to analyze stress, displacement, and factor of safety.
- Gained a better understanding of how changing dimensions and adding fillets or gussets can improve structural performance.
- Learned how to perform mesh convergence studies and verify results using a 7% tolerance.
- Improved my ability to identify high-stress areas and make design decisions based on FEA results.
- Learned the importance of maintaining required fit dimensions while modifying a design.
- Realized that even when a design does not meet every requirement, the results can help guide future improvements.

### Time Spent

**Total Time: 8 hours**

## Appendix

### SOLIDWORKS CAD Files

The SOLIDWORKS CAD files for the bracket designs are linked below.

- [Design I – Original Bracket](BRACKET.SLDPRT)
- [Design II – Modified Bracket](BRACKETDESIGNII.SLDPRT)
- [Design III – Final Bracket](BRACKETDESIGNIII.SLDPRT)
