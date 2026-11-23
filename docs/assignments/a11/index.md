# A11 – Motor Selection

## Objective
The objective of this assignment is to continue the design of a 2 kN tensile testing machine using two Acme lead screws. Building on the preliminary design developed in A10, this phase focuses on selecting suitable motors, designing motor mounting brackets and shaft couplers, evaluating frame connections, and designing floating bearing supports.

Engineering calculations will be performed to verify torque requirements, rotational speed, stresses, component dimensions, and structural safety factors. The design must support a maximum tensile load of 2,000 N, provide a crosshead speed range of 1–50 mm/min, and achieve a target factor of safety of 4.

The final design will incorporate a complete CAD assembly, structural finite element analysis (FEA), and a combined bill of materials and engineering cost analysis for A10 and A11.


## Analyze

### 1. Motor Selection and Verification

The tensile testing machine requires two motors to drive the Acme lead screws and move the crosshead at a controlled speed. The **Bodine Electric Model 4762 DC gearmotor** was selected as the preliminary design candidate based on its torque capacity, rated speed, and availability of manufacturer CAD files.

**Motor specifications**

| Parameter | Value |
|---|---|
| Motor | Bodine Electric Model 4762 |
| Rated output torque | 32.77 N·m |
| Peak output torque | 52.42 N·m |
| Rated output speed | 21 rpm |
| Gear ratio | 120:1 |
| Supply voltage | 24 V DC |
| Rated current | 8.8 A |
| Rated power | 0.25 hp |
| Quantity | 2 |

Manufacturer: https://www.bodine-electric.com/products/dc-right-angle-gearmotors/42a-gb-series-dc-right-angle-gearmotor/4762/

#### A. Required Force

Maximum tensile load:

\[
F_{\text{total}}=2000\text{ N}
\]

Assuming equal load distribution between the two lead screws:

\[
F_{\text{screw}}=\frac{2000}{2}
=\boxed{1000\text{ N}}
\]

#### B. Required Rotational Speed

From A10, the Acme screw lead is:

\[
L=2.54\text{ mm/rev}
\]

Using:

\[
n=\frac{v}{L}
\]

Minimum:

\[
n_{\min}=\frac{1}{2.54}
=\boxed{0.394\text{ rpm}}
\]

Maximum:

\[
n_{\max}=\frac{50}{2.54}
=\boxed{19.69\text{ rpm}}
\]

#### C. Required Torque

The A10 analysis estimated a drive torque of 1.30 N·m per lead screw.

Applying a conservative torque-sizing factor of 4:

\[
T_{\text{design}}=4(1.30)
\]

\[
\boxed{T_{\text{design}}=5.20\text{ N}\cdot\text{m}}
\]

#### D. Motor Torque Verification

The motor's rated output torque is:

\[
T_{\text{rated}}=32.77\text{ N}\cdot\text{m}
\]

Torque capacity ratio:

\[
\frac{32.77}{1.30}=\boxed{25.21}
\]

Since the rated torque exceeds the 5.20 N·m design target, the motor passes the preliminary rated-torque capacity check.

#### E. Mechanical Power

At maximum required rotational speed:

\[
\omega=\frac{2\pi(19.69)}{60}
=2.062\text{ rad/s}
\]

\[
P=T\omega=(1.30)(2.062)
\]

\[
\boxed{P=2.68\text{ W per screw}}
\]

Total mechanical power:

\[
P_{\text{total}}=2(2.68)=\boxed{5.36\text{ W}}
\]

#### F. Estimated Efficiency

At the motor's rated operating point:

\[
P_{\text{out}}=32.77\left(\frac{2\pi(21)}{60}\right)
=72.07\text{ W}
\]

\[
P_{\text{in}}=VI=(24)(8.8)=211.2\text{ W}
\]

\[
\eta=\frac{72.07}{211.2}(100)
=\boxed{34.1\%}
\]

This represents an approximate overall motor-and-gearbox efficiency calculated from the published rated values.

#### G. Speed–Torque Curve

The motor lecture describes the ideal DC motor speed–torque relationship as:

\[
\omega=\frac{V}{k_e}-\frac{R}{k_e k_t}T
\]

An illustrative linear curve was created using an assumed 25 rpm no-load output speed and the manufacturer-rated point of 32.77 N·m at 21 rpm:

\[
\boxed{n=25-0.1221T}
\]

The assumed no-load speed is not manufacturer-verified. Therefore, this curve is a preliminary engineering illustration, not a validated performance curve.

**Graph:** Insert `Bodine_4762_illustrative_speed_torque.png` here.

#### H. Motor Selection Conclusion

The Bodine 4762 meets the preliminary rated-torque and maximum-speed requirements for the tensile testing machine.

However, continuous performance across the full 0.394–19.69 rpm range has not been verified. The minimum operating speed, permissible control method, and synchronization of both lead screws require further investigation.

The Bodine 4762 remains the working motor selection for preliminary CAD development, subject to these outstanding checks.

### 2. Motor Mount Bracket Design

Two motor mounting brackets are required to attach the Bodine 4762 gearmotors to the upper frame of the tensile testing machine. The brackets must support the motor weight, resist applied loads and torque reactions, and maintain proper alignment with the Acme lead screws.

6061-T6 aluminum was selected for the brackets because of its strength, machinability, and relatively low weight.

**[INSERT PICTURE 5 — Motor Mount Bracket Concept]**

*Figure 5. Preliminary motor mounting bracket design showing its attachment to the upper aluminum frame.*

#### A. Known Values

| Parameter | Value |
|---|---|
| Motor | Bodine 4762 |
| Motor mass | 8.85 kg |
| Rated output torque | 32.77 N·m |
| Assumed axial load per bracket | 1,000 N |
| Bracket material | 6061-T6 aluminum |
| Yield strength | 276 MPa |
| Factor of safety | 4 |
| Proposed frame mounting bolts | Four M8 |
| Preliminary bolt spacing | 80 × 80 mm |
| Assumed unsupported length | 40 mm |
| Preliminary effective bracket width | 80 mm |

The bolt spacing, unsupported length, and effective width are preliminary geometric assumptions that must be checked against the final CAD assembly. The 1,000 N axial force is conservatively assigned to the bracket until the actual thrust-bearing load path is established.

#### B. Free-Body Diagram

The mounting bracket is analyzed under the motor torque, motor weight, and assumed axial load.

**[INSERT PICTURE 6 — Motor Mount Free-Body Diagram]**

*Figure 6. Free-body diagram showing the assumed 1,000 N axial load, 32.77 N·m torque reaction, motor weight, and frame mounting reactions.*

#### C. Force per Mounting Bolt

Assuming the axial force is distributed equally among four bolts:

\[
F_{\text{axial}}=\frac{1000}{4}
\]

\[
\boxed{F_{\text{axial}}=250\text{ N}}
\]

For the assumed 80 × 80 mm square bolt pattern:

\[
r=\sqrt{40^2+40^2}
\]

\[
\boxed{r=56.57\text{ mm}=0.05657\text{ m}}
\]

Torque-induced tangential force per bolt:

\[
F_T=\frac{T}{4r}
\]

\[
F_T=\frac{32.77}{4(0.05657)}
\]

\[
\boxed{F_T=144.8\text{ N}}
\]

Motor weight:

\[
W=mg
\]

\[
W=(8.85)(9.81)
\]

\[
\boxed{W=86.8\text{ N}}
\]

Weight contribution per bolt:

\[
F_W=\frac{86.8}{4}=21.7\text{ N}
\]

For an illustrative orthogonal force combination:

\[
F_b=\sqrt{250^2+144.8^2+21.7^2}
\]

\[
\boxed{F_b\approx290\text{ N}}
\]

This force estimate assumes perpendicular loading components and equal sharing. The final bolt-group analysis must account for actual load directions, bolt preload, and bracket geometry.

#### D. Allowable Stress

For 6061-T6 aluminum:

\[
\sigma_y=276\text{ MPa}
\]

Using a factor of safety of 4:

\[
\sigma_{\text{allow}}=\frac{\sigma_y}{FS}
\]

\[
\sigma_{\text{allow}}=\frac{276}{4}
\]

\[
\boxed{\sigma_{\text{allow}}=69\text{ MPa}}
\]

#### E. Minimum Thickness — Bearing Stress

The projected bearing-stress relationship is:

\[
\sigma_b=\frac{F_b}{dt}
\]

Rearranging for thickness:

\[
t_{\min}=\frac{F_b}{d\sigma_{\text{allow}}}
\]

Using an 8 mm nominal bolt diameter:

\[
t_{\min}=\frac{290}{8(69)}
\]

\[
\boxed{t_{\min}=0.525\text{ mm}}
\]

This is a preliminary projected bearing calculation. It does not establish the actual bolt-hole bearing allowable, edge-tearout strength, or complete bracket capacity.

#### F. Minimum Thickness — Bending

Modeling the bracket as an equivalent rectangular cantilever:

\[
\sigma=\frac{6FL}{bt^2}
\]

Rearranging:

\[
t=\sqrt{\frac{6FL}{b\sigma_{\text{allow}}}}
\]

Using:

\[
F=1000\text{ N},\quad L=40\text{ mm},\quad b=80\text{ mm}
\]

\[
t=\sqrt{\frac{6(1000)(40)}{80(69)}}
\]

\[
\boxed{t_{\min}=6.59\text{ mm}}
\]

A preliminary plate thickness of 8 mm was selected.

#### G. Bending Stress Verification

\[
\sigma=\frac{6FL}{bt^2}
\]

\[
\sigma=\frac{6(1000)(40)}{80(8)^2}
\]

\[
\boxed{\sigma=46.88\text{ MPa}}
\]

Since:

\[
46.88<69\text{ MPa}
\]

The 8 mm thickness satisfies the simplified bending model.

The actual bracket must also be checked for local stresses, motor mounting forces, connection rigidity, deflection, and bolt-group loading.

#### H. Preliminary Design Specifications

| Feature | Selection |
|---|---|
| Material | 6061-T6 aluminum |
| Preliminary plate thickness | 8 mm |
| Frame attachment | Four M8 bolts |
| Preliminary frame bolt pattern | 80 × 80 mm |
| Motor attachment | Manufacturer mounting interface |
| Quantity | 2 brackets |
| Status | Preliminary design; geometry verification required |

**[INSERT PICTURE 7 — Dimensioned Motor Bracket CAD]**

*Figure 7. CAD drawing showing bracket thickness, overall dimensions, mounting-hole positions, and attachment to the frame.*

**[INSERT PICTURE 8 — Motor and Bracket Assembly]**

*Figure 8. Complete motor-to-bracket assembly showing the motor output shaft aligned with its corresponding lead screw.*

#### I. Engineering Conclusion

An 8 mm thick 6061-T6 aluminum plate satisfies the preliminary cantilever bending calculation under the stated assumptions. The bearing-stress estimate gives a smaller minimum thickness, indicating that bending governs this simplified analysis.

Final bracket approval requires confirmation of the motor mounting geometry, actual support and load path, bolt capacities, and compatibility with the upper aluminum frame.

### 3. Coupler Design and Torsion Analysis

Two shaft couplers are required to connect the Bodine 4762 gearmotors to the Acme lead screws. Each coupler must transmit motor torque while maintaining shaft alignment and preventing excessive torsional stress.

6061-T6 aluminum was selected as the preliminary coupler material because of its strength, machinability, and relatively low weight.

**[INSERT PICTURE 9 — Coupler Design Concept]**

*Figure 9. Preliminary shaft coupler connecting the motor output shaft to the Acme lead screw.*

#### A. Known Values

| Parameter | Value |
|---|---|
| Motor | Bodine 4762 |
| Rated motor torque | 32.77 N·m |
| Peak motor torque | 52.42 N·m |
| Motor output shaft | 19.05 mm nominal |
| Acme screw diameter | 12.70 mm nominal |
| Coupler material | 6061-T6 aluminum |
| Yield strength | 276 MPa |
| Factor of safety | 4 |
| Number of couplers | 2 |

The coupler must accommodate two different shaft diameters. The Acme screw end will require a suitable machined journal or adapter.

#### B. Free-Body Diagram

The coupler transmits torque from the motor to the lead screw.

**[INSERT PICTURE 10 — Coupler Torsion FBD]**

*Figure 10. Free-body diagram showing motor input torque, resisting torque, and the coupler's torsional loading.*

From rotational equilibrium:

\[
\sum M_x=0
\]

\[
T_{\text{motor}}-T_{\text{screw}}=0
\]

#### C. Design Torque

For a conservative preliminary analysis, apply a factor of safety of 4 to the rated motor torque:

\[
T_d=FS(T_{\text{rated}})
\]

\[
T_d=4(32.77)
\]

\[
\boxed{T_d=131.08\text{ N}\cdot\text{m}}
\]

Converting:

\[
\boxed{T_d=131080\text{ N}\cdot\text{mm}}
\]

This design torque exceeds the manufacturer's published peak motor torque and provides a conservative initial sizing load.

#### D. Allowable Shear Stress

Using the von Mises shear-yield approximation:

\[
\tau_y=\frac{\sigma_y}{\sqrt{3}}
\]

\[
\tau_y=\frac{276}{\sqrt{3}}
\]

\[
\boxed{\tau_y=159.35\text{ MPa}}
\]

The factor of safety has already been applied to the design torque, so the same factor is not applied again to the allowable stress.

#### E. Minimum Coupler Outside Diameter

For a hollow circular shaft:

\[
\tau_{\max}=\frac{Tc}{J}
\]

Where:

\[
c=\frac{D_o}{2}
\]

\[
J=\frac{\pi}{32}(D_o^4-D_i^4)
\]

Substituting:

\[
\boxed{\tau_{\max}=\frac{16TD_o}{\pi(D_o^4-D_i^4)}}
\]

Using:

\[
D_i=19.05\text{ mm}
\]

\[
T=131080\text{ N}\cdot\text{mm}
\]

The minimum diameter is determined from:

\[
159.35=\frac{16(131080)D_o}{\pi(D_o^4-19.05^4)}
\]

Solving numerically:

\[
\boxed{D_{o,\min}\approx21.9\text{ mm}}
\]

This calculation applies to an ideal, unkeyed hollow circular section.

#### F. Select Coupler Diameter

A preliminary outside diameter of 35 mm was selected to provide additional material for the keyed connection and machining.

\[
\boxed{D_o=35\text{ mm}}
\]

Check maximum shear stress:

\[
\tau_{\max}=\frac{16(131080)(35)}{\pi(35^4-19.05^4)}
\]

\[
\boxed{\tau_{\max}\approx17.07\text{ MPa}}
\]

Since:

\[
17.07<159.35\text{ MPa}
\]

The selected diameter passes the simplified torsional shear calculation.

#### G. Coupler Wall Thickness

The minimum wall thickness occurs around the larger motor-side bore.

\[
t=\frac{D_o-D_i}{2}
\]

\[
t=\frac{35-19.05}{2}
\]

\[
\boxed{t=7.98\text{ mm}}
\]

#### H. Preliminary Coupler Specifications

| Feature | Selection |
|---|---|
| Material | 6061-T6 aluminum |
| Outer diameter | 35 mm |
| Motor-side bore | 19.05 mm nominal |
| Lead screw-side bore | 12.70 mm nominal, subject to journal design |
| Motor-side radial wall thickness | 7.98 mm |
| Motor connection | Keyed interface |
| Coupler quantity | 2 |
| Overall length | To be confirmed from shaft engagement requirements |

The selected dimensions provide a preliminary coupler envelope. Final CAD must establish shaft engagement lengths, bore tolerances, keyway dimensions, and a suitable lead screw-end connection.

[INSERT PICTURE 11 — Dimensioned Coupler CAD]

Figure 11. CAD model showing the coupler's stepped bores, outside diameter, keyway, and overall length.

[INSERT PICTURE 12 — Motor, Coupler, and Lead Screw Assembly]

Figure 12. Coupler installed between the Bodine 4762 output shaft and the Acme lead screw.

I. Engineering Conclusion

A preliminary coupler outside diameter of 35 mm was selected. The simplified torsional analysis produced a maximum shear stress of approximately 17.07 MPa under the conservative design torque of 131.08 N·m.

The selected diameter satisfies the ideal hollow-shaft torsion calculation. Final verification must account for keyway stresses, shaft connections, machining tolerances, alignment, and any coupling flexibility required by the assembly.

The preliminary geometry will be incorporated into the CAD model and evaluated for fit with the motor and lead screw.
### 4. Frame Connection Analysis

The tensile testing machine uses a Heavy 40 Series aluminum extrusion frame to support the two Acme lead screws, moving crosshead, and motor assemblies.

During operation, motor reaction torques and tensile forces are transferred into the upper frame through the motor mounts and lead screw supports. The frame connections must resist these loads without excessive movement or failure.

A preliminary analysis was performed to determine the applied twisting moment, support reactions, and suitable T-slot connectors.

**[INSERT PICTURE 13 — Top Frame Connection Concept]**

*Figure 13. Upper aluminum frame showing the two motor locations and connections to the vertical supports.*

#### A. Known Values

| Parameter | Value |
|---|---|
| Maximum tensile load | 2,000 N |
| Number of motors | 2 |
| Load per lead screw | 1,000 N |
| Motor | Bodine Electric 4762 |
| Rated motor torque | 32.77 N·m |
| Lead screw spacing | 200 mm |
| Frame material | Heavy 40 Series aluminum |
| Required factor of safety | 4 |

The actual frame support spacing and connector locations will be established from the final CAD geometry.

#### B. Free-Body Diagram

The upper frame is subjected to motor reaction torques, lead screw support forces, and reactions from the vertical frame connections.

**[INSERT PICTURE 14 — Frame Connection FBD]**

*Figure 14. Free-body diagram of the upper frame showing two motor reaction torques, vertical screw-support loads, and frame connection reactions.*

#### C. Calculate Motor-Induced Twisting Moment

Assuming the two motor reaction torques act in the same direction:

\[
M_{\text{total}}=T_1+T_2
\]

\[
M_{\text{total}}=32.77+32.77
\]

\[
\boxed{M_{\text{total}}=65.54\text{ N}\cdot\text{m}}
\]

This is a conservative combined rated-torque loading case.

Under the nominal operating condition:

\[
M_{\text{nominal}}=2(1.30)
\]

\[
\boxed{M_{\text{nominal}}=2.60\text{ N}\cdot\text{m}}
\]

Both loading cases are considered in the preliminary design.

Actual net frame torque depends on the motor rotation directions and mounting orientation.

#### D. Frame Connection Reactions

For a simplified equivalent force couple resisting the twisting moment:

\[
\sum M=0
\]

\[
R(S)=M_{\text{total}}
\]

Rearranging:

\[
\boxed{R=\frac{M_{\text{total}}}{S}}
\]

Where:

- \(R\) = equivalent reaction force (N)
- \(S\) = separation between the opposing reaction force lines (m)
- \(M_{\text{total}}\) = applied twisting moment (N·m)

For an illustrative reaction separation of 200 mm:

\[
S=0.200\text{ m}
\]

\[
R=\frac{65.54}{0.200}
\]

\[
\boxed{R=327.7\text{ N}}
\]

The 200 mm distance comes from the lead screw spacing and is used here only as an illustrative moment arm. It is not yet the verified frame connection spacing.

Final reactions must be recalculated using the actual connection geometry.

#### E. T-Slot Connector Selection

The preliminary connector selected is:

**80/20 Part 40-4303 — Four-Hole Wide Inside Corner Bracket**

This bracket is designed for right-angle connections in compatible 40 Series aluminum extrusion assemblies.

Manufacturer reference:

https://airinc.net/wp-content/uploads/2021/04/40-4303-Tech-Sheet.pdf

Proposed connection arrangement:

| Feature | Preliminary selection |
|---|---|
| Frame | Heavy 40 Series aluminum extrusion |
| Connector | 80/20 Part 40-4303 |
| Connection type | Right-angle corner bracket |
| Preliminary quantity | 4 brackets |
| Fasteners | Compatible T-slot bolts and T-nuts |
| Factor of safety target | 4 |

The proposed arrangement places reinforced connections at the upper horizontal frame member and vertical supports.

**[INSERT PICTURE 15 — T-Slot Connector]**

*Figure 15. Selected 80/20 40-4303 four-hole corner bracket with manufacturer dimensions.*

#### F. Connection Stress Verification

For a symmetric four-fastener bolt group resisting a moment:

\[
F_i=\frac{Mr_i}{\sum r_j^2}
\]

If all four fasteners are the same distance \(r\) from the bolt-group centroid:

\[
\boxed{F_i=\frac{M}{4r}}
\]

The actual force calculation requires the finalized connector geometry, fastener positions, and load distribution.

Connection safety factor:

\[
FS=\frac{\text{Allowable connection capacity}}{\text{Applied connection load}}
\]

The design target is:

\[
\boxed{FS\geq4}
\]

The final analysis must account for fastener shear, tension, bracket bending, T-slot retention, and the manufacturer's allowable connection loads. A numerical safety factor cannot be established from the preliminary geometry alone.

#### G. CAD and FEA Verification

The CAD assembly will establish the final frame connection locations and the arrangement of the T-slot brackets.

**[INSERT PICTURE 16 — Completed Frame Connection CAD]**

*Figure 16. Final CAD close-up showing the selected corner brackets, fasteners, and connections between the upper horizontal frame and vertical supports.*

FEA will be used to evaluate stresses and deflections in the horizontal and vertical frame members. The connection load cases must be consistent with the actual motor and lead screw load paths.

#### H. Engineering Conclusion

The preliminary analysis produced a combined rated motor reaction torque of 65.54 N·m and a nominal operating torque of 2.60 N·m.

The 80/20 40-4303 corner bracket was selected as a preliminary connection component because of its compatibility with 40 Series T-slot framing.

Final connection geometry, fastener loading, allowable capacities, and structural safety factors must be verified using the completed CAD assembly and manufacturer specifications.

### 7. Floating Bearing Mount Analysis

The tensile testing machine requires two floating bearing supports at the bottom of the Acme lead screws. These supports allow the screws to rotate while providing radial support and accommodating small axial movements.

The upper fixed bearings are intended to resist the lead screw's axial thrust, while the lower floating bearings prevent excessive lateral movement and avoid overconstraining the screws.

**[INSERT PICTURE 17 — Fixed and Floating Bearing Arrangement Diagram]**

*Figure 17. Engineering diagram illustrating the fixed upper bearing and floating lower bearing arrangement.*

#### A. Known Values

| Parameter | Value |
|---|---|
| Number of lead screws | 2 |
| Lead screw type | 1/2"-10 Acme |
| Nominal screw diameter | 12.70 mm |
| Minimum screw length | 457.2 mm |
| Lead screw center spacing | 200 mm |
| Bearing mount material | 6061-T6 aluminum |
| Required fit | RC3 precision running fit |
| Required factor of safety | 4 |

#### B. Preliminary Design Dimensions

| Feature | Preliminary dimension |
|---|---|
| Mount width | 80 mm |
| Mount height | 40 mm |
| Mount thickness | 20 mm |
| Proposed machined journal diameter | 12 mm |
| Mounting fasteners | Two M8 bolts |
| Nominal bolt clearance holes | 9 mm |
| Number of mounts | 2 |

The dimensions above are preliminary design selections and must be checked against the actual lower frame geometry.

#### C. Free-Body Diagram

The floating support is designed to resist radial reactions while allowing axial movement of the lead screw.

**[INSERT PICTURE 18 — Floating Bearing Free-Body Diagram]**

*Figure 18. Free-body diagram showing radial bearing reactions and the intended axial freedom at the lower lead screw support.*

For radial equilibrium:

\[
\sum F_x=0,\qquad \sum F_y=0
\]

For the ideal floating support:

\[
R_{\text{axial}}=0
\]

The axial load is intended to be carried by the upper fixed bearing arrangement.

#### D. Bearing Pressure Analysis

Projected bearing pressure is calculated using:

\[
p=\frac{R}{dL_b}
\]

Where:

- \(R\) = radial bearing reaction (N)
- \(d\) = journal diameter (mm)
- \(L_b\) = effective bearing length (mm)

Using the proposed 12 mm journal diameter and 20 mm bearing length:

\[
p=\frac{R}{12(20)}
\]

\[
\boxed{p=\frac{R}{240}\text{ MPa}}
\]

A numerical bearing pressure cannot be determined until the radial reaction and selected bearing arrangement are established.

The 1,000 N axial load per lead screw is not automatically equivalent to the radial bearing reaction.

#### E. RC3 Running Fit

An RC3 precision running fit was specified for the rotating bearing interface.

The purpose of the fit is to provide controlled clearance for smooth rotation while maintaining accurate shaft alignment.

Proposed nominal journal diameter:

\[
\boxed{d=12.00\text{ mm}}
\]

The final upper and lower tolerance limits must be selected from an applicable ANSI B4.1 RC3 fit table for the corresponding basic size.

The fit must be applied to the correct rotating shaft and mating bearing surface. If a rolling-element bearing is selected, its manufacturer-specified shaft and housing fits must also be respected.

**[INSERT PICTURE 19 — RC3 Fit and Tolerance Diagram]**

*Figure 19. Shaft and mating bore tolerance zones illustrating the required precision running fit.*

#### F. Mounting Bolt Clearance

Two M8 bolts were provisionally selected to attach each support to the lower frame.

Using a normal clearance hole:

\[
\boxed{d_h=9.0\text{ mm}}
\]

The mounting-hole locations and bolt loads will be finalized using the actual lower frame connections.

#### G. Engineering Conclusion

A preliminary 6061-T6 aluminum floating bearing mount measuring 80 × 40 × 20 mm was selected for each lead screw.

A 12 mm machined journal and RC3 running fit are proposed to provide controlled rotational clearance.

The bearing-pressure equation and mounting requirements have been established. Final validation requires the actual radial reactions, selected bearing dimensions, numerical RC3 tolerance limits, and verification of the fixed–floating support arrangement.

## Cost Analysis and Bill of Materials

### 8. Combined A10 and A11 Cost Analysis

A preliminary cost analysis was performed to estimate the total cost of designing and constructing the 2 kN tensile testing machine. The analysis includes components selected during A10 and A11, purchased materials, custom-manufactured components, and engineering labor.

Supplier prices were used where available. Components without confirmed prices are identified separately and will be updated after final CAD verification.

#### A. Purchased Components

| Component | Quantity | Unit Cost | Total |
|---|---:|---:|---:|
| Bodine 4762 DC gearmotor | 2 | $1,145.44 | $2,290.88 |
| Roton #59284 Acme lead screw | 3 ft | $9.10/ft | $27.30 |
| Roton #90222 bronze nut | 2 | $23.57 | $47.14 |
| 80/20 40-4303 corner bracket | 4 | $8.79 | $35.16 |
| Roton #89838 mounting flange | 2 | TBD | TBD |
| Bearings and bearing hardware | TBD | TBD | TBD |
| Motor/frame fasteners | TBD | TBD | TBD |

**Subtotal of priced purchased components:**

\[
C_{\text{purchased}}=2290.88+27.30+47.14+35.16
\]

\[
\boxed{C_{\text{purchased}}=\$2400.48}
\]

**[INSERT PICTURE 20 — Selected Purchased Components and Supplier Prices]**

*Figure 20. Manufacturer and supplier references for the selected motors, lead screws, nuts, and frame connectors.*

#### B. Aluminum Frame Cost

The preliminary frame design uses Heavy 40 Series aluminum T-slot extrusion.

Estimated extrusion length:

\[
L=2160\text{ mm}
\]

Estimated price:

\[
C_{\text{unit}}=\$0.0821/\text{mm}
\]

Material cost:

\[
C_{\text{material}}=(2160)(0.0821)
\]

\[
\boxed{C_{\text{material}}=\$177.34}
\]

Assuming four cuts at $3.79 per cut:

\[
C_{\text{cutting}}=4(3.79)=\$15.16
\]

Total preliminary frame cost:

\[
C_{\text{frame}}=177.34+15.16
\]

\[
\boxed{C_{\text{frame}}=\$192.50}
\]

The extrusion length and number of cuts are preliminary estimates and must be updated using the final CAD cut list.

#### C. Custom Manufactured Components

The following components require fabrication or additional sourcing.

| Component | Quantity | Material | Cost |
|---|---:|---|---|
| Moving crosshead | 1 | 6061-T6 aluminum | TBD |
| Motor mounting brackets | 2 | 6061-T6 aluminum | TBD |
| Shaft couplers | 2 | 6061-T6 aluminum | TBD |
| Floating bearing mounts | 2 | 6061-T6 aluminum | TBD |
| Fixed bearing supports | 2 | To be selected | TBD |
| Specimen grips/adapters | 2 sets | To be selected | TBD |

These components will be priced using the final material dimensions, stock requirements, and estimated fabrication costs.

**[INSERT PICTURE 21 — Custom Component Material and Cost References]**

*Figure 21. Material selections and supplier references for the custom components.*

#### D. Engineering Labor Cost

The required engineering labor rate is:

\[
R=\$35/\text{hour}
\]

Labor cost is calculated using:

\[
C_{\text{labor}}=R(H_{\text{total}})
\]

Where \(H_{\text{total}}\) represents the team's actual engineering hours for A10 and A11.

For an illustrative estimate of 20 total engineering hours:

\[
C_{\text{labor}}=35(20)
\]

\[
\boxed{C_{\text{labor}}=\$700.00}
\]

The 20-hour value is an example and will be replaced with actual recorded hours before final submission.

#### E. Preliminary Total Cost

Purchased components:

\[
C_{\text{purchased}}=\$2400.48
\]

Aluminum frame:

\[
C_{\text{frame}}=\$192.50
\]

Illustrative engineering labor:

\[
C_{\text{labor}}=\$700.00
\]

Combined partial estimate:

\[
C_{\text{partial}}=2400.48+192.50+700.00
\]

\[
\boxed{C_{\text{partial}}=\$3292.98}
\]

This is a partial cost estimate, not the final machine cost. It excludes unpriced components, custom fabrication costs, shipping, taxes, and other required hardware.

The complete cost will be calculated using:

\[
\boxed{C_{\text{total}}=C_{\text{materials}}+C_{\text{purchased}}+C_{\text{fabrication}}+C_{\text{labor}}}
\]

**[INSERT PICTURE 22 — Final BOM and Cost Summary]**

*Figure 22. Updated bill of materials showing confirmed component quantities, supplier prices, fabrication costs, and total engineering labor.*

#### F. Engineering Conclusion

The preliminary combined A10 and A11 cost analysis produced a partial estimate of $3,292.98, including an illustrative 20-hour engineering labor allowance.

The two Bodine 4762 gearmotors represent the largest identified purchased-component expense. Material costs were estimated using supplier pricing, while custom components and additional hardware remain subject to final design confirmation.

The bill of materials will be updated after the CAD assembly is completed and actual engineering labor hours are recorded.


## Decide
_Reference your concept selection (Pugh matrix) here. How does this design follow from that decision?_

## Communicate
