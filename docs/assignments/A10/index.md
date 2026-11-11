# A10 – Lead Screw Translating System

## Objective

The objective of this assignment is to design a mechanically driven tensile testing system capable of applying a maximum tensile load of 2,000 N to a test specimen while maintaining a factor of safety of 4.

The design incorporates two identical Acme leadscrews that control the movement of an aluminum crosshead. The system must provide a crosshead speed ranging from 1 to 50 mm/min, use leadscrews at least 18 inches long, and limit the maximum crosshead deflection to 0.1 mm.

To develop the design, engineering calculations are performed to determine the minimum leadscrew diameter, required rotational speed range, maximum driving torque, bronze nut thread bending stress, and crosshead bending stress and deflection.

Additional calculations evaluate the strength of the central grip attachment, mounting bolts, aluminum thread engagement, and leadscrew buckling. Commercially available components are selected, and the proposed design is prepared for assembly modeling in Creo Parametric.

The goal is to develop a practical tensile tester design that satisfies the specified engineering requirements while demonstrating the application of mechanics of materials, machine design, and component selection.

## Analyze
The following engineering calculations were performed to evaluate the strength, performance, and feasibility of the proposed tensile testing system.

Each calculation includes the known parameters, unknown variables, free-body diagram where applicable, governing equations, and numerical results.

The analysis begins with the leadscrew design, followed by component selection, bronze nut verification, crosshead design, and additional structural checks.


### 1. Minimum Leadscrew Diameter

The first step in designing the tensile tester was determining the minimum required diameter of each leadscrew to withstand the applied axial load.

Since the tensile tester uses two identical leadscrews, the maximum applied force of 2,000 N was assumed to be distributed equally between them.

#### Knowns

- Maximum tensile force: \(F = 2000 \text{ N}\)
- Number of leadscrews: \(n = 2\)
- Force per leadscrew: \(P = 1000 \text{ N}\)
- Factor of safety: \(FS = 4\)
- Preliminary material: AISI 1018 cold-drawn steel
- Yield strength: \(\sigma_y = 370 \text{ MPa}\)

#### Unknown

- Minimum required leadscrew root diameter, \(d_{\min}\)

#### Governing Equations

The allowable axial stress is calculated using:

$$
\sigma_{\text{allow}} = \frac{\sigma_y}{FS}
$$

The axial stress in a circular leadscrew is:

$$
\sigma = \frac{P}{A} = \frac{4P}{\pi d^2}
$$

Rearranging to solve for the minimum diameter:

$$
d_{\min} = \sqrt{\frac{4P}{\pi \sigma_{\text{allow}}}}
$$

#### Numerical Solution

First, calculate the allowable stress:

$$
\sigma_{\text{allow}} = \frac{370}{4}
= 92.5 \text{ MPa}
$$

Substitute into the minimum diameter equation:

$$
d_{\min} = \sqrt{\frac{4(1000)}{\pi(92.5)}}
$$

$$
\boxed{d_{\min} = 3.71 \text{ mm}}
$$

#### Engineering Conclusion

The calculated minimum leadscrew root diameter is approximately **3.71 mm** based on axial yielding.

This establishes the minimum diameter required to resist the assumed axial load with a factor of safety of 4. A larger commercially available leadscrew will be selected to provide additional strength and accommodate the mechanical requirements of the system.

This calculation addresses axial yielding only. Buckling and other loading conditions are evaluated separately.


### 2. Leadscrew Rotational Speed Range

The next step was determining the rotational speed required for the leadscrews to move the crosshead within the specified velocity range of 1–50 mm/min.

A preliminary **Roton 1/2"-10 Acme leadscrew** was selected. This screw has a single-start thread with a lead of 0.100 in/rev, equivalent to 2.54 mm/rev.

The lead represents the linear distance the nut travels during one complete revolution of the leadscrew.

#### Knowns

- Minimum crosshead velocity: \(v_{\min}=1\text{ mm/min}\)
- Maximum crosshead velocity: \(v_{\max}=50\text{ mm/min}\)
- Leadscrew thread: 1/2"-10 Acme
- Lead: \(l=2.54\text{ mm/rev}\)

#### Unknowns

- Minimum rotational speed, \(N_{\min}\)
- Maximum rotational speed, \(N_{\max}\)

#### Governing Equation

The relationship between linear velocity, leadscrew lead, and rotational speed is:

$$
v=Nl
$$

Rearranging:

$$
\boxed{N=\frac{v}{l}}
$$

#### Numerical Solution

**Minimum rotational speed:**

$$
N_{\min}=\frac{1}{2.54}
$$

$$
\boxed{N_{\min}=0.394\text{ rpm}}
$$

**Maximum rotational speed:**

$$
N_{\max}=\frac{50}{2.54}
$$

$$
\boxed{N_{\max}=19.69\text{ rpm}}
$$

#### Engineering Conclusion

The selected leadscrews must operate between approximately **0.394 and 19.69 rpm** to achieve the required crosshead velocity range.

Both leadscrews must rotate at the same speed and in the appropriate direction to maintain alignment and produce uniform crosshead movement.

The drive system must therefore provide controlled low-speed rotation across this range.

#### Handwritten Calculations

![Leadscrew Rotational Speed Calculation](images/A10_Leadscrew_RPM.png)
#### Handwritten Calculations

![Minimum Leadscrew Diameter Calculation](images/A10_Leadscrew_Diameter.png)

### 3. Maximum Driving Torque

The next step was calculating the torque required to rotate each Acme leadscrew while moving the crosshead under the maximum applied load.

The calculation accounts for the axial force, screw geometry, and friction between the steel leadscrew and bronze nut.

Because Acme threads have a 29° included angle, the friction coefficient was adjusted using the 14.5° thread half-angle.

#### Knowns

- Total applied force: \(F = 2000\text{ N}\)
- Force per leadscrew: \(P = 1000\text{ N}\)
- Leadscrew type: 1/2"-10 Acme
- Pitch diameter: \(d_p = 11.43\text{ mm}\)
- Lead: \(l = 2.54\text{ mm/rev}\)
- Assumed friction coefficient: \(\mu = 0.15\)
- Acme thread half-angle: \(\alpha = 14.5^\circ\)

#### Unknowns

- Adjusted friction coefficient, \(\mu'\)
- Driving torque per leadscrew, \(T\)
- Combined driving torque for both leadscrews, \(T_{\text{total}}\)

#### Governing Equations

The effective friction coefficient for the Acme thread is approximated by:

$$
\mu' = \frac{\mu}{\cos(\alpha)}
$$

The circumferential distance at the pitch diameter is:

$$
C = \pi d_p
$$

The tangential force required to raise the load is:

$$
F_t = P\left(\frac{\mu'C+l}{C-\mu'l}\right)
$$

Torque is related to tangential force by:

$$
T = F_t\frac{d_p}{2}
$$

Combining the equations:

$$
\boxed{
T=\frac{Pd_p}{2}
\left(\frac{\mu'\pi d_p+l}
{\pi d_p-\mu'l}\right)
}
$$

#### Numerical Solution

**Step 1: Adjust the friction coefficient**

$$
\mu'=\frac{0.15}{\cos(14.5^\circ)}
$$

$$
\boxed{\mu'=0.1549}
$$

**Step 2: Calculate the pitch circumference**

$$
C=\pi(11.43)
$$

$$
\boxed{C=35.91\text{ mm}}
$$

**Step 3: Calculate the driving torque**

$$
T=\frac{(1000)(11.43)}{2}
\left(
\frac{(0.1549)(35.91)+2.54}
{35.91-(0.1549)(2.54)}
\right)
$$

$$
T\approx1303\text{ N·mm}
$$

Converting to N·m:

$$
\boxed{T\approx1.30\text{ N·m per leadscrew}}
$$

**Step 4: Calculate combined torque**

Since the system uses two identical leadscrews:

$$
T_{\text{total}}=2T
$$

$$
T_{\text{total}}=2(1.30)
$$

$$
\boxed{T_{\text{total}}\approx2.61\text{ N·m}}
$$

#### Engineering Conclusion

The calculated driving torque is approximately **1.30 N·m per leadscrew**, resulting in a combined theoretical torque requirement of approximately **2.61 N·m**.

This calculation represents the torque required to advance the Acme screws under the assumed maximum axial load and friction coefficient.

Additional torque may be required to overcome bearing friction, drivetrain losses, and other mechanical resistance. These effects must be considered when selecting the final drive mechanism.

#### Handwritten Calculations

![Maximum Driving Torque Calculation](images/A10_Leadscrew_Torque.png)

### 4. Leadscrew Selection and Verification

After determining the minimum required leadscrew diameter, rotational speed range, and driving torque, a commercially available Acme leadscrew was selected for the tensile tester.

The preliminary selection was a **Roton 1/2"-10 right-hand Acme leadscrew**. Two identical leadscrews will be used to move the crosshead and distribute the applied tensile load.

#### Selected Leadscrew Specifications

| Property | Specification |
|---|---|
| Manufacturer | Roton Products |
| Leadscrew type | Right-hand Acme |
| Nominal diameter | 1/2 in (12.70 mm) |
| Thread specification | 1/2"-10 |
| Lead | 0.100 in/rev (2.54 mm/rev) |
| Pitch diameter | Approximately 0.450 in (11.43 mm) |
| Minor/root diameter | 0.359 in (9.12 mm) |
| Required screw length | At least 18 in (457.2 mm) |
| Quantity | 2 identical leadscrews |

#### Diameter Verification

From the initial axial stress calculation, the minimum required root diameter was:

$$
d_{\min}=3.71\text{ mm}
$$

The selected Roton leadscrew has a root diameter of:

$$
d_{\text{selected}}=9.12\text{ mm}
$$

Comparing the two values:

$$
9.12\text{ mm}>3.71\text{ mm}
$$

Therefore, the selected leadscrew exceeds the minimum diameter required by the preliminary axial yielding calculation.

#### Axial Stress Verification

The axial stress is calculated using:

$$
\sigma=\frac{4P}{\pi d^2}
$$

Substituting the selected root diameter:

$$
\sigma=\frac{4(1000)}{\pi(9.12)^2}
$$

$$
\boxed{\sigma=15.31\text{ MPa}}
$$

The allowable stress for the preliminary AISI 1018 steel assumption was:

$$
\sigma_{\text{allow}}=\frac{370}{4}
=92.5\text{ MPa}
$$

Since:

$$
15.31<92.5\text{ MPa}
$$

The selected leadscrew satisfies the preliminary axial yielding requirement.

The actual screw material grade and yield strength must be confirmed before treating this check as final.

#### Operating Requirements

The selected lead of 2.54 mm/rev produces the following required operating speeds:

$$
N_{\min}=0.394\text{ rpm}
$$

$$
N_{\max}=19.69\text{ rpm}
$$

The estimated driving torque is:

$$
T=1.30\text{ N·m per leadscrew}
$$

These values will be used when developing the mechanical drive system.

#### Engineering Conclusion

The Roton 1/2"-10 right-hand Acme leadscrew was selected because its geometry exceeds the minimum root diameter calculated from axial stress and its lead can provide the required crosshead velocity range.

Two identical screws will be used, with a minimum required length of 18 inches each.

Although the leadscrew satisfies the preliminary axial stress calculation, its buckling resistance and actual support conditions must also be evaluated before final design approval.

#### Selected Component Reference

![Roton Acme Leadscrew Specifications](images/A10_Leadscrew_Selection.png)

*Figure 4. Manufacturer specifications for the selected Roton 1/2"-10 Acme leadscrew.*

**Manufacturer Reference:**  
[Roton – Acme Right-Hand Screws and Nuts](https://www.roton.com/family/acme-right-screws-and-nuts-7059284/)

### 5. Bronze Nut and Mounting Flange Selection

After selecting the Roton 1/2"-10 Acme leadscrews, compatible bronze nuts and mounting flanges were selected to transfer the axial forces between the rotating leadscrews and the moving crosshead.

Bronze nuts were chosen because they are commonly used with steel Acme leadscrews to provide controlled linear motion while reducing friction and wear.

The design uses two identical bronze nuts and two mounting flanges, one for each leadscrew.

#### Selected Bronze Nut

| Property | Specification |
|---|---|
| Manufacturer | Roton Products |
| Part number | #90222 |
| Component | Bronze threaded mounting nut |
| Thread size | 1/2"-10 Acme |
| Thread direction | Right-hand |
| Overall nut length | 0.750 in (19.05 mm) |
| External mounting thread length | 0.500 in (12.70 mm) |
| Reported bronze-nut operating load rating | 1,250 lbf |
| Quantity | 2 |

The maximum assumed load on each bronze nut is:

$$
P_{\text{nut}}=\frac{2000}{2}
$$

$$
\boxed{P_{\text{nut}}=1000\text{ N}}
$$

Converting to pounds-force:

$$
P_{\text{nut}}=\frac{1000}{4.44822}
$$

$$
\boxed{P_{\text{nut}}\approx224.8\text{ lbf}}
$$

The reported operating load rating of 1,250 lbf exceeds the expected operating load of 224.8 lbf per nut.

However, the operating load rating is not necessarily a yield or ultimate failure load. Therefore, it cannot be used by itself to establish a structural factor of safety of 4.

#### Selected Mounting Flange

| Property | Specification |
|---|---|
| Manufacturer | Roton Products |
| Part number | #89838 |
| Component | Steel mounting flange |
| Outside diameter | 2.600 in (66.04 mm) |
| Bolt circle diameter | 2.090 in (53.09 mm) |
| Mounting holes | 4 |
| Mounting-hole diameter | 0.266 in (6.76 mm) |
| Quantity | 2 |

Each mounting flange connects a bronze nut to the aluminum crosshead.

The flange mounting pattern was considered when determining the final preliminary dimensions of the crosshead.

#### Compatibility With the Leadscrew

The selected components are intended to form the following assembly:

1. Roton 1/2"-10 right-hand Acme leadscrew
2. Roton #90222 bronze mounting nut
3. Roton #89838 steel mounting flange
4. 6061-T6 aluminum crosshead

Rotation of each leadscrew causes its corresponding bronze nut to translate along the screw.

The mounting flanges connect the nuts to the crosshead, allowing both leadscrews to move the crosshead together.

The final CAD assembly must verify the nut-to-flange connection, fastener arrangement, alignment, and available clearances.

#### Engineering Conclusion

The Roton #90222 bronze nuts and #89838 mounting flanges were selected as preliminary components for the two-leadscrew tensile testing system.

The bronze nuts provide the threaded interface for converting screw rotation into linear movement, while the mounting flanges provide attachment points for the crosshead.

The selected flange dimensions also influenced the crosshead redesign, which increased its depth from 30 mm to 80 mm to accommodate the mounting hardware.

Further verification is required for the actual nut material, internal thread engagement, and connection details.

#### Selected Component Images

**Bronze Nut:**

![Roton Bronze Nut](images/A10_Bronze_Nut.png)

*Figure 5. Selected Roton #90222 bronze mounting nut.*

**Mounting Flange:**

![Roton Mounting Flange](images/A10_Mounting_Flange.png)

*Figure 6. Selected Roton #89838 mounting flange.*

#### Manufacturer Reference

[Roton – Acme Right-Hand Screws and Nuts](https://www.roton.com/family/acme-right-screws-and-nuts-7059284/)


### 6. Bronze Nut Thread Bending Stress

After selecting the Roton #90222 bronze nut, the next step was evaluating the bending stress experienced by its internal threads under the maximum applied axial load.

The bronze nut threads transfer the axial force from the rotating Acme leadscrew into the crosshead. Therefore, the threads must have sufficient strength to resist bending failure.

#### Knowns

- Total applied force: \(F = 2000\text{ N}\)
- Force per bronze nut: \(P = 1000\text{ N}\)
- Selected bronze nut: Roton #90222
- Leadscrew thread: 1/2"-10 Acme
- Leadscrew root diameter: \(d_{\min}=9.12\text{ mm}\)
- Thread pitch: \(p=2.54\text{ mm}\)
- Assumed internal thread engagement: \(L_e=12.7\text{ mm}\)
- Factor of safety: \(FS=4\)
- Preliminary bronze material assumption: SAE 660 (C93200)
- Assumed bronze yield strength: \(\sigma_y=96.5\text{ MPa}\)

**Note:** The actual bronze alloy and internal thread engagement length of the selected nut have not been confirmed. The 12.7 mm engagement is a preliminary assumption and should not be confused with the nut's external mounting thread length.

#### Unknowns

- Number of engaged threads, \(n_t\)
- Bronze nut thread bending stress, \(\sigma_b\)
- Allowable bending stress, \(\sigma_{\text{allow}}\)
- Preliminary factor of safety

#### Governing Equations

The approximate number of engaged threads is:

$$
n_t=\frac{L_e}{p}
$$

The thread bending stress equation is:

$$
\boxed{\sigma_b=\frac{6P}{n_t\pi d_{\min}p}}
$$

The allowable stress is:

$$
\sigma_{\text{allow}}=\frac{\sigma_y}{FS}
$$

#### Numerical Solution

**Step 1: Calculate the number of engaged threads**

$$
n_t=\frac{12.7}{2.54}
$$

$$
\boxed{n_t=5\text{ threads}}
$$

**Step 2: Calculate the thread bending stress**

$$
\sigma_b=\frac{6(1000)}{5\pi(9.12)(2.54)}
$$

$$
\boxed{\sigma_b=16.5\text{ MPa}}
$$

**Step 3: Calculate allowable bending stress**

$$
\sigma_{\text{allow}}=\frac{96.5}{4}
$$

$$
\boxed{\sigma_{\text{allow}}=24.13\text{ MPa}}
$$

**Step 4: Compare actual and allowable stress**

$$
16.5<24.13\text{ MPa}
$$

The calculated thread bending stress is below the allowable stress under the assumed material and engagement conditions.

**Step 5: Calculate the preliminary factor of safety**

$$
FS_{\text{actual}}=\frac{\sigma_y}{\sigma_b}
$$

$$
FS_{\text{actual}}=\frac{96.5}{16.5}
$$

$$
\boxed{FS_{\text{actual}}\approx5.85}
$$

#### Engineering Conclusion

The calculated bronze nut thread bending stress is approximately **16.5 MPa**, resulting in a preliminary factor of safety of **5.85**.

This exceeds the required factor of safety of 4 under the assumed material properties, thread engagement length, and simplified thread load distribution.

However, actual thread engagement, material properties, and nonuniform thread loading must be verified before considering the selected bronze nut fully validated.

#### Handwritten Calculations

![Bronze Nut Thread Bending Stress](images/A10_Bronze_Nut_Stress.png)

*Figure 7. Handwritten calculations used to determine the bronze nut thread bending stress and preliminary factor of safety.*


### 7. Crosshead Bending Stress

The next step was designing the crosshead to withstand the maximum tensile load of 2,000 N without exceeding the allowable bending stress.

The crosshead was modeled as a simply supported beam with the tensile force applied at its center. The two leadscrew connections were assumed to provide equal support reactions.

6061-T6 aluminum was selected as the preliminary crosshead material because of its strength, machinability, and relatively low weight.

#### Knowns

- Maximum tensile force: \(F=2000\text{ N}\)
- Leadscrew center spacing: \(L=200\text{ mm}\)
- Reaction at each leadscrew: \(R_A=R_B=1000\text{ N}\)
- Material: 6061-T6 aluminum
- Yield strength: \(\sigma_y=276\text{ MPa}\)
- Factor of safety: \(FS=4\)
- Initial crosshead depth: \(b=30\text{ mm}\)

#### Unknowns

- Maximum bending moment, \(M_{\max}\)
- Allowable bending stress, \(\sigma_{\text{allow}}\)
- Minimum crosshead height, \(h_{\min}\)
- Actual bending stress, \(\sigma_{\max}\)

#### Free-Body Diagram

![Crosshead Free-Body Diagram](images/A10_Crosshead_FBD.png)

*Figure 8. Crosshead free-body diagram showing the 2,000 N center load and two 1,000 N support reactions.*

#### Governing Equations

The allowable bending stress is:

$$
\sigma_{\text{allow}}=\frac{\sigma_y}{FS}
$$

For a simply supported beam with a concentrated load at the center:

$$
M_{\max}=\frac{FL}{4}
$$

The bending stress equation is:

$$
\sigma_{\max}=\frac{Mc}{I}
$$

For a rectangular cross-section:

$$
c=\frac{h}{2}
$$

$$
I=\frac{bh^3}{12}
$$

Substituting and simplifying:

$$
\boxed{\sigma_{\max}=\frac{6M_{\max}}{bh^2}}
$$

Rearranging to determine the minimum height:

$$
\boxed{h_{\min}=\sqrt{\frac{6M_{\max}}{b\sigma_{\text{allow}}}}}
$$

#### Numerical Solution

**Step 1: Calculate allowable bending stress**

$$
\sigma_{\text{allow}}=\frac{276}{4}
$$

$$
\boxed{\sigma_{\text{allow}}=69\text{ MPa}}
$$

**Step 2: Calculate maximum bending moment**

$$
M_{\max}=\frac{(2000)(200)}{4}
$$

$$
\boxed{M_{\max}=100,000\text{ N}\cdot\text{mm}}
$$

**Step 3: Determine minimum crosshead height**

Using the initial depth of 30 mm:

$$
h_{\min}=\sqrt{\frac{6(100000)}{30(69)}}
$$

$$
\boxed{h_{\min}=17.03\text{ mm}}
$$

**Step 4: Select an initial crosshead height**

An initial height of 30 mm was selected to provide additional stiffness and strength.

$$
h=30\text{ mm}
$$

**Step 5: Calculate actual bending stress**

$$
\sigma_{\max}=\frac{6(100000)}{30(30)^2}
$$

$$
\boxed{\sigma_{\max}=22.22\text{ MPa}}
$$

**Step 6: Verify the factor of safety**

$$
FS_{\text{actual}}=\frac{\sigma_y}{\sigma_{\max}}
$$

$$
FS_{\text{actual}}=\frac{276}{22.22}
$$

$$
\boxed{FS_{\text{actual}}\approx12.42}
$$

#### Engineering Conclusion

The minimum required crosshead height was calculated to be approximately **17.03 mm** for an initial 30 mm depth.

A height of 30 mm was selected, producing a maximum bending stress of **22.22 MPa** and a preliminary bending safety factor of **12.42**.

These results satisfy the required factor of safety of 4 for the simplified rectangular beam model.

The initial crosshead dimensions were 260 mm × 30 mm × 30 mm. However, the depth and overall length were later increased to accommodate the selected bronze-nut mounting flanges.

The revised crosshead dimensions and updated stress calculations are documented in the following sections.

#### Handwritten Calculations

![Crosshead Bending Stress Calculation](images/A10_Crosshead_Bending.png)

*Figure 9. Handwritten calculations used to determine the minimum crosshead height and initial bending stress.*


### 8. Crosshead Deflection

After verifying the crosshead bending stress, the next step was determining whether the crosshead would satisfy the maximum allowable deflection of 0.1 mm.

The crosshead was modeled as a simply supported beam with a concentrated 2,000 N load at its center.

The initial rectangular cross-section had a depth of 30 mm and a height of 30 mm.

#### Knowns

- Maximum tensile force: \(F=2000\text{ N}\)
- Leadscrew center spacing: \(L=200\text{ mm}\)
- Material: 6061-T6 aluminum
- Elastic modulus: \(E=69,000\text{ N/mm}^2\)
- Crosshead depth: \(b=30\text{ mm}\)
- Crosshead height: \(h=30\text{ mm}\)
- Maximum allowable deflection: \(\delta_{\text{allow}}=0.1\text{ mm}\)

#### Unknowns

- Area moment of inertia, \(I\)
- Maximum crosshead deflection, \(\delta_{\max}\)

#### Governing Equations

For a rectangular cross-section, the area moment of inertia is:

$$
I=\frac{bh^3}{12}
$$

For a simply supported beam with a concentrated load at its center, the maximum deflection is:

$$
\boxed{\delta_{\max}=\frac{FL^3}{48EI}}
$$

Substituting the rectangular moment of inertia:

$$
\boxed{\delta_{\max}=\frac{FL^3}{4Ebh^3}}
$$

#### Numerical Solution

**Step 1: Calculate the area moment of inertia**

$$
I=\frac{30(30)^3}{12}
$$

$$
\boxed{I=67,500\text{ mm}^4}
$$

**Step 2: Calculate maximum deflection**

$$
\delta_{\max}=\frac{(2000)(200)^3}{48(69000)(67500)}
$$

$$
\boxed{\delta_{\max}=0.0716\text{ mm}}
$$

**Step 3: Compare against the allowable deflection**

$$
\delta_{\max}<\delta_{\text{allow}}
$$

$$
0.0716<0.100\text{ mm}
$$

Therefore, the initial crosshead satisfies the specified deflection limit under the simplified beam assumptions.

#### Engineering Conclusion

The initial crosshead design produced a calculated maximum deflection of **0.0716 mm**, which is below the allowable limit of 0.1 mm.

Although the initial crosshead satisfied both the bending stress and deflection requirements, its 30 mm depth was insufficient to accommodate the selected Roton mounting flanges.

Therefore, the crosshead dimensions were revised to provide additional mounting space and structural stiffness.

The updated geometry and corresponding calculations are documented in the next section.

#### Handwritten Calculations

![Initial Crosshead Deflection Calculation](images/A10_Crosshead_Deflection.png)

*Figure 10. Handwritten calculation used to verify the initial crosshead deflection.*


### 9. Crosshead Design Revisions and Final Preliminary Dimensions

After completing the initial bending stress and deflection calculations, the crosshead dimensions were reviewed to ensure compatibility with the selected bronze nuts and mounting flanges.

Although the original crosshead satisfied the simplified structural calculations, its dimensions were insufficient to accommodate the mounting hardware.

Therefore, the crosshead was redesigned to provide additional mounting space and improve structural stiffness.

#### Reason for Design Changes

The selected Roton #89838 mounting flange has an outside diameter of 66.04 mm.

The original crosshead depth was only 30 mm, meaning the flange could not fit entirely within the crosshead footprint.

The crosshead depth was increased to 80 mm to accommodate the mounting flanges.

The overall length was also increased from 260 mm to 280 mm to provide additional material around the mounting locations.

The leadscrew spacing remained 200 mm.

#### Original vs. Revised Dimensions

| Feature | Original Design | Revised Design |
|---|---|---|
| Overall length | 260 mm | 280 mm |
| Crosshead depth | 30 mm | 80 mm |
| Crosshead height | 30 mm | 30 mm |
| Leadscrew spacing | 200 mm | 200 mm |
| Material | 6061-T6 aluminum | 6061-T6 aluminum |

#### Knowns

- Maximum tensile force: \(F=2000\text{ N}\)
- Leadscrew spacing: \(L=200\text{ mm}\)
- Maximum bending moment: \(M_{\max}=100,000\text{ N}\cdot\text{mm}\)
- Material: 6061-T6 aluminum
- Yield strength: \(\sigma_y=276\text{ MPa}\)
- Elastic modulus: \(E=69,000\text{ MPa}\)
- Factor of safety: \(FS=4\)
- Revised crosshead depth: \(b=80\text{ mm}\)
- Revised crosshead height: \(h=30\text{ mm}\)
- Allowable deflection: \(\delta_{\text{allow}}=0.1\text{ mm}\)

#### Unknowns

- Revised area moment of inertia, \(I\)
- Revised maximum bending stress, \(\sigma_{\max}\)
- Revised maximum deflection, \(\delta_{\max}\)
- Revised bending factor of safety

#### Governing Equations

The area moment of inertia for a rectangular cross-section is:

$$
I=\frac{bh^3}{12}
$$

The maximum bending stress is:

$$
\sigma_{\max}=\frac{6M_{\max}}{bh^2}
$$

The maximum beam deflection is:

$$
\delta_{\max}=\frac{FL^3}{48EI}
$$

The bending factor of safety is:

$$
FS_{\text{actual}}=\frac{\sigma_y}{\sigma_{\max}}
$$

#### Numerical Solution

**Step 1: Calculate the revised moment of inertia**

$$
I=\frac{80(30)^3}{12}
$$

$$
\boxed{I=180,000\text{ mm}^4}
$$

**Step 2: Calculate the revised bending stress**

$$
\sigma_{\max}=\frac{6(100000)}{80(30)^2}
$$

$$
\boxed{\sigma_{\max}=8.33\text{ MPa}}
$$

**Step 3: Calculate the bending factor of safety**

$$
FS_{\text{actual}}=\frac{276}{8.33}
$$

$$
\boxed{FS_{\text{actual}}\approx33.1}
$$

**Step 4: Calculate the revised maximum deflection**

$$
\delta_{\max}=\frac{(2000)(200)^3}{48(69000)(180000)}
$$

$$
\boxed{\delta_{\max}=0.0268\text{ mm}}
$$

**Step 5: Verify design requirements**

Allowable bending stress:

$$
\sigma_{\text{allow}}=\frac{276}{4}=69\text{ MPa}
$$

Stress comparison:

$$
8.33<69\text{ MPa}
$$

Deflection comparison:

$$
0.0268<0.100\text{ mm}
$$

The revised crosshead satisfies both requirements under the simplified solid-beam model.

#### Mounting-Hole Layout

The revised crosshead has overall dimensions of:

$$
\boxed{280\times80\times30\text{ mm}}
$$

The two leadscrew centerlines are positioned 200 mm apart.

Using the lower-left corner of the crosshead top face as the coordinate origin:

| Feature | X (mm) | Y (mm) |
|---|---:|---:|
| Left leadscrew center | 40.00 | 40.00 |
| Right leadscrew center | 240.00 | 40.00 |
| Crosshead center | 140.00 | 40.00 |

Each flange uses four mounting holes arranged on a 53.09 mm bolt circle.

**Left Flange Mounting Holes**

| Hole | X (mm) | Y (mm) |
|---|---:|---:|
| 1 | 13.46 | 13.46 |
| 2 | 13.46 | 66.54 |
| 3 | 66.54 | 13.46 |
| 4 | 66.54 | 66.54 |

**Right Flange Mounting Holes**

| Hole | X (mm) | Y (mm) |
|---|---:|---:|
| 1 | 213.46 | 13.46 |
| 2 | 213.46 | 66.54 |
| 3 | 266.54 | 13.46 |
| 4 | 266.54 | 66.54 |

The mounting-hole diameter is approximately 6.76 mm, based on the selected flange specification.

The CAD model must distinguish between clearance holes in the flange and the corresponding fastener attachment features in the crosshead.

#### Central Specimen Attachment

A separate grip adapter was proposed to connect the tensile specimen to the underside of the crosshead.

Two preliminary M6 × 1.0 blind tapped holes were positioned symmetrically around the crosshead center.

| Hole | X (mm) | Y (mm) |
|---|---:|---:|
| Grip attachment 1 | 120 | 40 |
| Grip attachment 2 | 160 | 40 |

The proposed minimum full thread engagement is 10 mm.

This arrangement avoids a large central through-hole and allows the specimen grip to be attached separately.

The grip geometry, bolt engagement, and actual load path must be confirmed in the final assembly.

#### Design Comparison

| Property | Initial Design | Revised Design |
|---|---:|---:|
| Bending stress | 22.22 MPa | 8.33 MPa |
| Maximum deflection | 0.0716 mm | 0.0268 mm |
| Bending factor of safety | 12.42 | 33.1 |
| Crosshead depth | 30 mm | 80 mm |

#### Engineering Conclusion

The crosshead was redesigned to accommodate the selected Roton mounting flanges and improve structural stiffness.

Increasing the depth from 30 mm to 80 mm reduced the calculated bending stress from 22.22 MPa to 8.33 MPa and the calculated deflection from 0.0716 mm to 0.0268 mm.

The revised crosshead dimensions are **280 mm × 80 mm × 30 mm**, with the two leadscrews spaced 200 mm apart.

The design satisfies the bending stress and deflection requirements under the simplified beam assumptions.

These results do not include the effects of mounting holes, local stress concentrations, connection flexibility, or detailed grip loading. Those features require further verification during final design development.

#### Handwritten Calculations

![Revised Crosshead Calculations](images/A10_Crosshead_Revised.png)

*Figure 11. Revised crosshead bending stress, deflection, and dimensional calculations.*

#### CAD Design Layout

![Crosshead Mounting Layout](images/A10_Crosshead_Layout.png)

*Figure 12. Preliminary crosshead layout showing leadscrew locations, flange mounting holes, and central specimen attachment.*


### 10. Central Grip Bolt Verification

After finalizing the preliminary crosshead dimensions, the next step was verifying the bolts used to attach the central specimen grip adapter.

The proposed attachment uses two M6 × 1.0 steel bolts threaded into the underside of the aluminum crosshead.

During tensile testing, the specimen applies a downward force of 2,000 N to the grip adapter. The bolts transfer this load into the crosshead.

For the preliminary analysis, the load was assumed to be distributed equally between the two bolts, with the bolts primarily subjected to axial tension.

#### Knowns

- Maximum tensile force: \(F=2000\text{ N}\)
- Number of grip bolts: \(n=2\)
- Bolt specification: M6 × 1.0
- Preliminary bolt property class: 8.8
- Bolt tensile stress area: \(A_t=20.1\text{ mm}^2\)
- Nominal bolt yield strength: \(\sigma_y=640\text{ MPa}\)
- Required factor of safety: \(FS=4\)

#### Unknowns

- Tensile force per bolt, \(F_b\)
- Bolt tensile stress, \(\sigma_b\)
- Allowable tensile stress, \(\sigma_{\text{allow}}\)
- Actual bolt factor of safety

#### Free-Body Diagram

![Central Grip Bolt FBD](images/A10_Grip_Bolt_FBD.png)

*Figure 13. Free-body diagram of the central grip adapter showing the applied tensile force and the two supporting bolt forces.*

#### Governing Equations

Using vertical force equilibrium:

$$
\sum F_y=0
$$

Assuming equal load distribution:

$$
2F_b-F=0
$$

Therefore:

$$
\boxed{F_b=\frac{F}{2}}
$$

The tensile stress in each bolt is:

$$
\boxed{\sigma_b=\frac{F_b}{A_t}}
$$

The allowable tensile stress is:

$$
\sigma_{\text{allow}}=\frac{\sigma_y}{FS}
$$

The actual factor of safety is:

$$
FS_{\text{actual}}=\frac{\sigma_y}{\sigma_b}
$$

#### Numerical Solution

**Step 1: Calculate the force per bolt**

$$
F_b=\frac{2000}{2}
$$

$$
\boxed{F_b=1000\text{ N}}
$$

**Step 2: Calculate the tensile stress**

$$
\sigma_b=\frac{1000}{20.1}
$$

$$
\boxed{\sigma_b=49.75\text{ MPa}}
$$

**Step 3: Calculate allowable tensile stress**

$$
\sigma_{\text{allow}}=\frac{640}{4}
$$

$$
\boxed{\sigma_{\text{allow}}=160\text{ MPa}}
$$

**Step 4: Compare actual and allowable stress**

$$
49.75<160\text{ MPa}
$$

The calculated bolt tensile stress is below the allowable stress.

**Step 5: Calculate actual factor of safety**

$$
FS_{\text{actual}}=\frac{640}{49.75}
$$

$$
\boxed{FS_{\text{actual}}\approx12.86}
$$

#### Engineering Conclusion

The proposed two M6 × 1.0 property class 8.8 steel bolts produce a nominal tensile stress of **49.75 MPa per bolt** under the assumed equal load distribution.

The calculated yield-based factor of safety is approximately **12.86**, exceeding the required factor of safety of 4.

Therefore, the selected bolts satisfy the preliminary axial tensile-strength requirement.

However, this calculation assumes equal loading, negligible bending and prying forces, and no additional effects from bolt preload or connection flexibility.

The aluminum internal threads must also be checked to ensure that the bolts cannot strip out of the crosshead.

#### Handwritten Calculations

![Central Grip Bolt Calculations](images/A10_Grip_Bolt_Calculations.png)

*Figure 14. Handwritten calculations used to verify the tensile strength of the central grip attachment bolts.*


### 11. Aluminum Thread Stripping Verification

After verifying the tensile strength of the central grip attachment bolts, the next step was evaluating the internal aluminum threads in the crosshead.

Although the steel bolts were determined to have sufficient tensile strength, the internal threads of the aluminum crosshead could potentially fail in shear.

Therefore, a preliminary thread stripping calculation was performed to evaluate the proposed 10 mm thread engagement.

#### Knowns

- Maximum applied tensile force: \(F=2000\text{ N}\)
- Number of grip attachment bolts: \(n=2\)
- Force per bolt: \(F_b=1000\text{ N}\)
- Bolt specification: M6 × 1.0
- Nominal bolt diameter: \(d=6\text{ mm}\)
- Thread pitch: \(p=1\text{ mm}\)
- Proposed full thread engagement: \(L_e=10\text{ mm}\)
- Crosshead material: 6061-T6 aluminum
- Aluminum yield strength: \(\sigma_y=276\text{ MPa}\)
- Required factor of safety: \(FS=4\)

#### Unknowns

- Allowable shear stress, \(\tau_{\text{allow}}\)
- Approximate thread shear area, \(A_s\)
- Estimated internal thread shear stress, \(\tau\)
- Preliminary thread stripping factor of safety

#### Thread Engagement Diagram

![Aluminum Thread Engagement Diagram](images/A10_Thread_Engagement.png)

*Figure 15. Diagram showing the M6 bolt engaged in the aluminum crosshead with a proposed 10 mm full thread engagement.*

#### Governing Equations

The shear yield strength of a ductile material can be estimated using the von Mises criterion:

$$
\tau_y=\frac{\sigma_y}{\sqrt{3}}
$$

The allowable shear stress is:

$$
\boxed{\tau_{\text{allow}}=\frac{\tau_y}{FS}}
$$

For an initial simplified estimate, the effective internal thread shear area is approximated by:

$$
\boxed{A_s\approx\frac{\pi dL_e}{2}}
$$

The estimated thread shear stress is:

$$
\boxed{\tau=\frac{F_b}{A_s}}
$$

The preliminary factor of safety is:

$$
FS_{\text{actual}}=\frac{\tau_y}{\tau}
$$

#### Numerical Solution

**Step 1: Calculate the aluminum shear yield strength**

$$
\tau_y=\frac{276}{\sqrt{3}}
$$

$$
\boxed{\tau_y=159.35\text{ MPa}}
$$

**Step 2: Calculate allowable shear stress**

$$
\tau_{\text{allow}}=\frac{159.35}{4}
$$

$$
\boxed{\tau_{\text{allow}}=39.84\text{ MPa}}
$$

**Step 3: Estimate the thread shear area**

$$
A_s\approx\frac{\pi(6)(10)}{2}
$$

$$
\boxed{A_s\approx94.25\text{ mm}^2}
$$

**Step 4: Calculate estimated thread shear stress**

$$
\tau=\frac{1000}{94.25}
$$

$$
\boxed{\tau\approx10.61\text{ MPa}}
$$

**Step 5: Compare actual and allowable shear stress**

$$
10.61<39.84\text{ MPa}
$$

The estimated thread shear stress is below the allowable shear stress.

**Step 6: Calculate the preliminary factor of safety**

$$
FS_{\text{actual}}=\frac{159.35}{10.61}
$$

$$
\boxed{FS_{\text{actual}}\approx15.0}
$$

#### Engineering Conclusion

The simplified thread stripping calculation produced an estimated shear stress of **10.61 MPa** and a preliminary factor of safety of approximately **15.0**.

These results indicate that the proposed 10 mm full thread engagement is promising for the M6 grip attachment bolts under the assumed loading conditions.

However, the shear area equation is an approximation. Actual ISO metric thread geometry, thread tolerances, nonuniform load distribution, and bolt preload can affect the connection's strength.

Therefore, this result is considered a preliminary verification rather than a final certified thread stripping capacity.

#### Handwritten Calculations

![Aluminum Thread Stripping Calculations](images/A10_Thread_Stripping.png)

*Figure 16. Handwritten calculations used to estimate the internal aluminum thread shear stress and preliminary factor of safety.*


### 12. Flange Mounting Bolt Verification

After verifying the central grip attachment, the next step was evaluating the bolts used to secure the bronze nut mounting flanges to the aluminum crosshead.

Each Roton #89838 mounting flange contains four mounting holes. The preliminary design uses four M6 property class 8.8 steel bolts per flange.

These bolts connect the flange to the crosshead and help transfer the axial loading from the bronze nut into the crosshead structure.

For the preliminary analysis, the 1,000 N axial load on each flange was assumed to be distributed equally among its four mounting bolts.

#### Knowns

- Maximum tensile force: \(F=2000\text{ N}\)
- Number of leadscrews: 2
- Load per flange: \(F_f=1000\text{ N}\)
- Mounting bolts per flange: \(n=4\)
- Total mounting bolts: 8
- Proposed bolt specification: M6 × 1.0
- Bolt property class: 8.8
- Bolt tensile stress area: \(A_t=20.1\text{ mm}^2\)
- Nominal bolt yield strength: \(\sigma_y=640\text{ MPa}\)
- Required factor of safety: \(FS=4\)
- Flange outside diameter: 66.04 mm
- Flange bolt circle diameter: 53.09 mm
- Flange mounting-hole diameter: 6.76 mm
- Crosshead dimensions: 280 × 80 × 30 mm

#### Unknowns

- Force per mounting bolt, \(F_b\)
- Nominal tensile stress per bolt, \(\sigma_b\)
- Allowable tensile stress, \(\sigma_{\text{allow}}\)
- Preliminary bolt factor of safety
- Minimum mounting-hole edge distance

#### Governing Equations

Assuming the flange load is distributed equally:

$$
\boxed{F_b=\frac{F_f}{n}}
$$

The nominal tensile stress is:

$$
\boxed{\sigma_b=\frac{F_b}{A_t}}
$$

The allowable tensile stress is:

$$
\sigma_{\text{allow}}=\frac{\sigma_y}{FS}
$$

The preliminary factor of safety is:

$$
FS_{\text{actual}}=\frac{\sigma_y}{\sigma_b}
$$

For the proposed square-oriented bolt pattern, the distance from each bolt center to the corresponding crosshead edge is:

$$
e_c=40-\frac{53.09}{2}
$$

The remaining material between the hole edge and the crosshead edge is:

$$
\boxed{e_{\text{clear}}=e_c-\frac{d_h}{2}}
$$

#### Numerical Solution

**Step 1: Calculate the load per mounting bolt**

$$
F_b=\frac{1000}{4}
$$

$$
\boxed{F_b=250\text{ N}}
$$

**Step 2: Calculate the nominal bolt tensile stress**

$$
\sigma_b=\frac{250}{20.1}
$$

$$
\boxed{\sigma_b=12.44\text{ MPa}}
$$

**Step 3: Calculate allowable tensile stress**

$$
\sigma_{\text{allow}}=\frac{640}{4}
$$

$$
\boxed{\sigma_{\text{allow}}=160\text{ MPa}}
$$

**Step 4: Compare actual and allowable stress**

$$
12.44<160\text{ MPa}
$$

The nominal bolt tensile stress is below the allowable stress.

**Step 5: Calculate the preliminary factor of safety**

$$
FS_{\text{actual}}=\frac{640}{12.44}
$$

$$
\boxed{FS_{\text{actual}}\approx51.4}
$$

**Step 6: Calculate the mounting-hole edge distance**

The distance from the bolt center to the nearest crosshead edge is:

$$
e_c=40-\frac{53.09}{2}
$$

$$
\boxed{e_c=13.46\text{ mm}}
$$

Subtracting the mounting-hole radius:

$$
e_{\text{clear}}=13.46-\frac{6.76}{2}
$$

$$
\boxed{e_{\text{clear}}=10.08\text{ mm}}
$$

Therefore, approximately 10.08 mm of material remains between each outer mounting-hole edge and the nearest crosshead edge.

This is a geometric clearance calculation, not a complete verification of aluminum tear-out or bearing strength.

#### Engineering Conclusion

The preliminary analysis indicates that each M6 mounting bolt would carry approximately **250 N** under the assumed equal load distribution.

The resulting nominal tensile stress is **12.44 MPa**, corresponding to a preliminary yield-based factor of safety of **51.4**.

The proposed mounting-hole arrangement also leaves approximately **10.08 mm** of material between the outer hole edges and the nearest crosshead edges.

These results support the preliminary selection of four M6 mounting bolts per flange.

However, the actual load path, bolt preload, possible prying forces, aluminum thread engagement, bearing stress, and edge tear-out must be evaluated before the flange connection is considered fully verified.

The final CAD assembly must also confirm that the proposed bolt-hole arrangement matches the selected Roton flange.

#### Handwritten Calculations

![Flange Mounting Bolt Calculations](images/A10_Flange_Bolt_Verification.png)

*Figure 17. Preliminary flange mounting bolt stress and edge-distance calculations.*

#### Flange Mounting Layout

![Flange Mounting Layout](images/A10_Flange_Mounting_Layout.png)

*Figure 18. Proposed four-bolt flange mounting arrangement on the revised aluminum crosshead.*

### 13. Leadscrew Buckling Verification

After verifying the leadscrew axial stress, bronze nut strength, and crosshead connections, the next step was evaluating the possibility of leadscrew buckling.

Buckling is a structural instability that can occur when a long, slender member is subjected to axial compression.

Because the tensile tester uses two leadscrews with a minimum length of 18 inches, buckling must be considered if the operating load places the leadscrews in compression.

Euler's critical buckling equation was used for the preliminary analysis.

#### Knowns

- Maximum applied tensile force: \(F=2000\text{ N}\)
- Number of leadscrews: 2
- Maximum axial load per leadscrew: \(P=1000\text{ N}\)
- Selected leadscrew: Roton 1/2"-10 Acme
- Leadscrew root diameter: \(d=9.12\text{ mm}\)
- Preliminary unsupported length: \(L=18\text{ in}=457.2\text{ mm}\)
- Assumed steel elastic modulus: \(E=205,000\text{ N/mm}^2\)
- Required factor of safety: \(FS=4\)
- Preliminary end condition: pinned-pinned
- Effective length factor: \(K=1.0\)

#### Unknowns

- Minimum area moment of inertia, \(I\)
- Critical buckling load, \(P_{cr}\)
- Buckling factor of safety, \(FS_{\text{buckling}}\)
- Whether the selected leadscrew satisfies the design requirement

#### Governing Equations

For a solid circular cross-section:

$$
\boxed{I=\frac{\pi d^4}{64}}
$$

Euler's critical buckling load is:

$$
\boxed{P_{cr}=\frac{\pi^2EI}{(KL)^2}}
$$

The buckling factor of safety is:

$$
\boxed{FS_{\text{buckling}}=\frac{P_{cr}}{P}}
$$

The required critical buckling load is:

$$
P_{cr,\text{required}}=FS\times P
$$

#### Numerical Solution

**Step 1: Calculate the area moment of inertia**

Using the leadscrew root diameter:

$$
I=\frac{\pi(9.12)^4}{64}
$$

$$
\boxed{I\approx339.5\text{ mm}^4}
$$

**Step 2: Calculate the critical buckling load**

Assuming pinned-pinned end conditions:

$$
K=1.0
$$

$$
P_{cr}=\frac{\pi^2(205000)(339.5)}{(1.0\times457.2)^2}
$$

$$
\boxed{P_{cr}\approx3286\text{ N}}
$$

**Step 3: Calculate the buckling factor of safety**

$$
FS_{\text{buckling}}=\frac{3286}{1000}
$$

$$
\boxed{FS_{\text{buckling}}\approx3.29}
$$

**Step 4: Determine the required critical load**

$$
P_{cr,\text{required}}=4(1000)
$$

$$
\boxed{P_{cr,\text{required}}=4000\text{ N}}
$$

**Step 5: Compare the calculated and required values**

$$
3286<4000\text{ N}
$$

Equivalently:

$$
3.29<4.00
$$

Therefore, the selected leadscrew does not satisfy the required buckling factor of safety under the assumed pinned-pinned, full-length compression conditions.

#### Effect of End Support Conditions

The critical buckling load depends strongly on the effective length factor, \(K\).

Different support conditions produce different critical loads.

| End Condition | K | Approximate Buckling FS |
|---|---:|---:|
| Fixed-free | 2.0 | 0.82 |
| Pinned-pinned | 1.0 | 3.29 |
| Fixed-pinned | 0.7 | 6.71 |
| Fixed-fixed | 0.5 | 13.14 |

These results demonstrate that the actual bearing and support arrangement significantly affects buckling resistance.

However, installing bearings at both ends does not automatically establish fixed-end conditions. The effective length factor must be justified by the actual structural constraints.

#### Engineering Considerations

Several design details must be confirmed before finalizing the leadscrew selection:

1. **Axial loading direction:** Determine whether the leadscrews experience compression or tension during the maximum tensile test load.

2. **Unsupported length:** Determine the actual distance between lateral supports rather than automatically using the full leadscrew length.

3. **End support conditions:** Verify the rotational and lateral constraints provided by the bearing and mounting arrangement.

4. **Alternative design options:** If the leadscrews experience compression and the required safety factor is not achieved, consider reducing unsupported length, increasing root diameter, or redesigning the support arrangement.

The Roton 1/2"-10 Acme leadscrew remains the preliminary selection while these details are investigated.

#### Engineering Conclusion

The preliminary Euler buckling calculation produced a critical load of approximately **3,286 N** per leadscrew.

Under the assumed pinned-pinned end conditions and 457.2 mm unsupported length, the resulting buckling factor of safety is approximately **3.29**.

This is below the required factor of safety of 4.

Therefore, **buckling verification remains unresolved**, and the selected leadscrew cannot yet be considered fully validated for compressive loading.

The final design must establish the actual axial loading direction, unsupported length, and support conditions before confirming whether the selected leadscrew is acceptable.

#### Handwritten Calculations

![Leadscrew Buckling Calculations](images/A10_Leadscrew_Buckling.png)

*Figure 19. Preliminary Euler buckling calculation for the selected 1/2"-10 Acme leadscrew.*

#### Leadscrew Support Arrangement

![Leadscrew Support Diagram](images/A10_Leadscrew_Support.png)

*Figure 20. Preliminary leadscrew support arrangement used to evaluate possible buckling conditions.*

## Cost Analysis

### 5. Tabulating Costs

The following table lists the commercially purchased components required for the preliminary tensile testing machine design. Custom-designed components, including the crosshead, frame, and specimen grip adapters, are excluded from the cost analysis as permitted by the assignment instructions.

| Item Number | Quantity | Name | Cost/Item | Cost | Purchase Link |
|---|---:|---|---:|---:|---|
| 1 | 2 | Roton #59284 Acme Steel Leadscrew, 1/2"-10 RH, 18 in | $13.65 | $27.30 | [Purchase](https://www.roton.com/family/acme-right-screws-and-nuts-7059284/) |
| 2 | 2 | Roton #90222 Bronze Threaded Mount Nut | $23.57 | $47.14 | [Purchase](https://www.roton.com/family/acme-right-screws-and-nuts-7059284/) |
| 3 | 2 | Roton #89838 Steel Mounting Flange | $49.63 | $99.26 | [Purchase](https://www.roton.com/family/acme-right-screws-and-nuts-7059284/) |
| 4 | 1 pack | M6 × 1.0 × 20 mm Class 8.8 Bolts, 10-pack (provisional length) | $3.00 | $3.00 | [Purchase](https://gavantools.com/products/m6-x-1-0-x-20mm-10pcs-full-thread-grade-8-8-zinc-plated-flanged-hexagon-head-bolts) |
| | | **Subtotal of Priced Components** | | **$176.70** | |

**Additional purchased components requiring final selection:**

- Leadscrew support bearings
- Drive motor
- Motor coupling or synchronized transmission components

These components will be added to the table once their specifications and compatibility with the CAD assembly have been confirmed.

The current subtotal is $176.70, excluding shipping and taxes. It is not the final machine cost.

**Design note:** The selected leadscrews require additional buckling verification. Bolt lengths, bearing supports, and motor mounting details must also be confirmed before purchasing.


## Decide
_Reference your concept selection (Pugh matrix) here. How does this design follow from that decision?_

## Communicate

