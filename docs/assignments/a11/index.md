# A11 – Motor Selection

## Objective
The objective of this assignment is to continue the design of a 2 kN tensile testing machine using two Acme lead screws. Building on the preliminary design developed in A10, this phase focuses on selecting suitable motors, designing motor mounting brackets and shaft couplers, evaluating frame connections, and designing floating bearing supports.

Engineering calculations will be performed to verify torque requirements, rotational speed, stresses, component dimensions, and structural safety factors. The design must support a maximum tensile load of 2,000 N, provide a crosshead speed range of 1–50 mm/min, and achieve a target factor of safety of 4.

The final design will incorporate a complete CAD assembly, structural finite element analysis (FEA), and a combined bill of materials and engineering cost analysis for A10 and A11.


## Analyze


<section id="motor-selection">

  <h2>Engineering Analysis</h2>
  <h3>1. Motor Selection and Verification</h3>

  <p>
    Two motors are proposed to drive the Acme lead screws of
    the tensile testing machine. The Bodine Electric Model
    4762 DC gearmotor was selected as the preliminary
    candidate based on its torque capacity, rated speed,
    and availability of manufacturer CAD files.
  </p>

  <h4>Selected Motor Specifications</h4>

  <table border="1" cellpadding="8">
    <tr><th>Parameter</th><th>Value</th></tr>
    <tr><td>Motor</td><td>Bodine Electric 4762</td></tr>
    <tr><td>Rated Torque</td><td>32.77 N&#183;m</td></tr>
    <tr><td>Peak Torque</td><td>52.42 N&#183;m</td></tr>
    <tr><td>Rated Speed</td><td>21 rpm</td></tr>
    <tr><td>Gear Ratio</td><td>120:1</td></tr>
    <tr><td>Voltage</td><td>24 V DC</td></tr>
    <tr><td>Rated Current</td><td>8.8 A</td></tr>
    <tr><td>Motor Power Rating</td><td>0.25 hp</td></tr>
    <tr><td>Quantity</td><td>2</td></tr>
  </table>

  <figure>
    <img src="MOTORS.jpg"
         alt="Bodine 4762 motor" width="500">
  </figure>

  <figure>
    <img src="MOTORS2.jpg"
         alt="Motor specifications" width="500">
  </figure>

  <h4>A. Required Force</h4>

  <p>Maximum tensile load:</p>
  <p>F<sub>total</sub> = 2000 N</p>

  <p>Number of lead screws = 2</p>

  <p>
    F<sub>screw</sub> = F<sub>total</sub> / 2
  </p>

  <p>
    F<sub>screw</sub> = 2000 / 2
  </p>

  <p><strong>F<sub>screw</sub> = 1000 N</strong></p>

  <h4>B. Required Rotational Speed</h4>

  <p>Lead screw travel per revolution:</p>
  <p>L = 2.54 mm/rev</p>

  <p>Rotational speed equation:</p>
  <p>n = v / L</p>

  <p><strong>Minimum Speed:</strong></p>
  <p>n<sub>min</sub> = 1 / 2.54</p>
  <p><strong>n<sub>min</sub> = 0.394 rpm</strong></p>

  <p><strong>Maximum Speed:</strong></p>
  <p>n<sub>max</sub> = 50 / 2.54</p>
  <p><strong>n<sub>max</sub> = 19.69 rpm</strong></p>

  <h4>C. Required Design Torque</h4>

  <p>
    From A10, the estimated drive torque per lead screw
    was 1.30 N&#183;m.
  </p>

  <p>Using a conservative torque-sizing factor of 4:</p>

  <p>
    T<sub>design</sub> =
    FS &times; T<sub>required</sub>
  </p>

  <p>T<sub>design</sub> = 4 &times; 1.30</p>

  <p>
    <strong>T<sub>design</sub> = 5.20 N&#183;m</strong>
  </p>

  <h4>D. Motor Torque Verification</h4>

  <p>Rated motor output torque = 32.77 N&#183;m</p>

  <p>
    Torque capacity ratio = 32.77 / 1.30
  </p>

  <p><strong>Torque capacity ratio = 25.21</strong></p>

  <p>
    Since 32.77 N&#183;m exceeds the conservative
    5.20 N&#183;m design target, the motor passes
    the preliminary rated-torque capacity check.
  </p>

  <h4>E. Mechanical Power</h4>

  <p>Angular velocity:</p>

  <p>
    &omega; = (2&pi; &times; n) / 60
  </p>

  <p>
    &omega; = (2&pi; &times; 19.69) / 60
  </p>

  <p>
    <strong>&omega; = 2.062 rad/s</strong>
  </p>

  <p>Power equation:</p>
  <p>P = T &times; &omega;</p>

  <p>P = 1.30 &times; 2.062</p>

  <p><strong>P = 2.68 W per lead screw</strong></p>

  <p>Total power for two lead screws:</p>
  <p>P<sub>total</sub> = 2 &times; 2.68</p>

  <p><strong>P<sub>total</sub> = 5.36 W</strong></p>

  <p>
    This is the preliminary mechanical power
    requirement, excluding additional drivetrain losses.
  </p>

  <h4>F. Estimated Motor Efficiency</h4>

  <p>Mechanical output power at rated conditions:</p>

  <p>
    P<sub>out</sub> =
    T &times; (2&pi;n / 60)
  </p>

  <p>
    P<sub>out</sub> =
    32.77 &times; (2&pi; &times; 21 / 60)
  </p>

  <p><strong>P<sub>out</sub> = 72.07 W</strong></p>

  <p>Electrical input power:</p>

  <p>P<sub>in</sub> = V &times; I</p>
  <p>P<sub>in</sub> = 24 &times; 8.8</p>

  <p><strong>P<sub>in</sub> = 211.2 W</strong></p>

  <p>Estimated overall efficiency:</p>

  <p>
    &eta; =
    (P<sub>out</sub> / P<sub>in</sub>) &times; 100
  </p>

  <p>
    &eta; = (72.07 / 211.2) &times; 100
  </p>

  <p><strong>&eta; = 34.1%</strong></p>

  <p>
    This is an approximate motor-and-gearbox efficiency
    calculated from the published rated operating values.
  </p>

  <h4>G. Speed-Torque Curve</h4>

  <p>
    The ideal DC motor speed-torque relationship is:
  </p>

  <p>
    &omega; = V/k<sub>e</sub> -
    (R &times; T)/(k<sub>e</sub>k<sub>t</sub>)
  </p>

  <p>
    For an illustrative linear model, a no-load
    gearmotor output speed of 25 rpm was assumed.
    Using the manufacturer-rated point of 32.77 N&#183;m
    at 21 rpm:
  </p>

  <p>
    n = 25 - [(25 - 21) / 32.77]T
  </p>

  <p><strong>n = 25 - 0.1221T</strong></p>

  <p>
    The 25 rpm no-load assumption is not verified
    manufacturer data. Therefore, the graph is an
    illustrative engineering estimate, not a validated
    manufacturer speed-torque curve.
  </p>


  <h4>H. Engineering Conclusion</h4>

  <p>
    The Bodine Electric 4762 was retained as the
    preliminary motor selection based on its rated
    torque capacity and maximum rated speed.
    Its rated output torque of 32.77 N&#183;m exceeds
    the conservative design target of 5.20 N&#183;m.
  </p>

  <p>
    Continuous operation across the full required
    speed range of 0.394 to 19.69 rpm has not been
    verified. The minimum operating speed, allowable
    speed-control method, and synchronization of both
    lead screws remain unresolved design items.
  </p>

  <p>
    Manufacturer:
    <a href="https://www.bodine-electric.com/products/dc-right-angle-gearmotors/42a-gb-series-dc-right-angle-gearmotor/4762/">
      Bodine Electric Model 4762
    </a>
  </p>

</section>


<section id="motor-mount-analysis">

  <h3>2. Motor Mount Bracket Design</h3>

  <p>
    Two mounting brackets are required to attach the
    Bodine 4762 gearmotors to the upper frame of the
    tensile testing machine.
  </p>

  <p>
    The brackets must support the motor weight,
    resist applied loads and torque reactions,
    and maintain proper alignment with the
    Acme lead screws.
  </p>

  <p>
    Aluminum 6061-T6 was selected because of its
    strength, machinability, and relatively low weight.
  </p>

  <figure>
    <img src="MOUNTDES.jpg"
         alt="Motor mount bracket design" width="500">
  </figure>

  <h4>A. Known Values</h4>

  <table border="1" cellpadding="8">
    <tr><th>Parameter</th><th>Value</th></tr>
    <tr><td>Motor</td><td>Bodine 4762</td></tr>
    <tr><td>Motor Mass</td><td>8.85 kg</td></tr>
    <tr><td>Rated Output Torque</td>
        <td>32.77 N&#183;m</td></tr>
    <tr><td>Assumed Axial Load</td>
        <td>1000 N</td></tr>
    <tr><td>Bracket Material</td>
        <td>6061-T6 Aluminum</td></tr>
    <tr><td>Yield Strength</td>
        <td>276 MPa</td></tr>
    <tr><td>Factor of Safety</td><td>4</td></tr>
    <tr><td>Mounting Bolts</td><td>4 M8</td></tr>
    <tr><td>Proposed Bolt Pattern</td>
        <td>80 x 80 mm</td></tr>
    <tr><td>Unsupported Length</td>
        <td>40 mm</td></tr>
    <tr><td>Effective Bracket Width</td>
        <td>80 mm</td></tr>
  </table>

  <p>
    These dimensions are preliminary assumptions.
    The final bracket must be checked against the
    motor and frame geometry.
  </p>

  <h4>B. Free-Body Diagram</h4>

  <figure>
    <img src="MOUNTDES2.jpg"
         alt="Motor mount free-body diagram"
         width="500">
  </figure>

  <h4>C. Force per Mounting Bolt</h4>

  <p>
    Assuming the axial load is equally
    distributed between four mounting bolts:
  </p>

  <p>
    F<sub>axial</sub> = 1000 / 4
  </p>

  <p>
    <strong>F<sub>axial</sub> = 250 N</strong>
  </p>

  <p>
    For an 80 x 80 mm square bolt pattern:
  </p>

  <p>
    r = &radic;(40<sup>2</sup> + 40<sup>2</sup>)
  </p>

  <p><strong>r = 56.57 mm = 0.05657 m</strong></p>

  <p>Torque-induced tangential force:</p>

  <p>
    F<sub>T</sub> = T / (4r)
  </p>

  <p>
    F<sub>T</sub> = 32.77 / (4 x 0.05657)
  </p>

  <p><strong>F<sub>T</sub> = 144.8 N</strong></p>

  <p>Motor weight:</p>

  <p>W = mg</p>

  <p>W = 8.85 x 9.81</p>

  <p><strong>W = 86.8 N</strong></p>

  <p>Weight contribution per bolt:</p>

  <p>F<sub>W</sub> = 86.8 / 4</p>

  <p><strong>F<sub>W</sub> = 21.7 N</strong></p>

  <p>
    Illustrative resultant force assuming
    perpendicular loading components:
  </p>

  <p>
    F<sub>b</sub> =
    &radic;(250<sup>2</sup> +
    144.8<sup>2</sup> +
    21.7<sup>2</sup>)
  </p>

  <p><strong>F<sub>b</sub> = 290 N</strong></p>

  <p>
    This is a simplified bolt-force estimate.
    Actual forces depend on the motor orientation,
    bracket geometry, and bolt preload.
  </p>

  <h4>D. Allowable Stress</h4>

  <p>Yield strength:</p>

  <p>&sigma;<sub>y</sub> = 276 MPa</p>

  <p>
    &sigma;<sub>allow</sub> =
    &sigma;<sub>y</sub> / FS
  </p>

  <p>&sigma;<sub>allow</sub> = 276 / 4</p>

  <p>
    <strong>
      &sigma;<sub>allow</sub> = 69 MPa
    </strong>
  </p>

  <h4>E. Minimum Thickness - Bearing Stress</h4>

  <p>Projected bearing stress:</p>

  <p>&sigma;<sub>b</sub> = F<sub>b</sub> / (dt)</p>

  <p>Solving for thickness:</p>

  <p>
    t<sub>min</sub> =
    F<sub>b</sub> /
    (d &times; &sigma;<sub>allow</sub>)
  </p>

  <p>
    t<sub>min</sub> = 290 / (8 x 69)
  </p>

  <p>
    <strong>t<sub>min</sub> = 0.525 mm</strong>
  </p>

  <p>
    This is a simplified projected bearing
    calculation, not a full fastener or
    connection-strength verification.
  </p>

  <h4>F. Minimum Thickness - Bending</h4>

  <p>
    Model the bracket as an equivalent
    rectangular cantilever:
  </p>

  <p>
    &sigma; = 6FL / (bt<sup>2</sup>)
  </p>

  <p>Solving for thickness:</p>

  <p>
    t = &radic;[6FL /
    (b &times; &sigma;<sub>allow</sub>)]
  </p>

  <p>
    F = 1000 N, L = 40 mm, b = 80 mm
  </p>

  <p>
    t = &radic;[(6 x 1000 x 40) / (80 x 69)]
  </p>

  <p><strong>t<sub>min</sub> = 6.59 mm</strong></p>

  <p>Selected preliminary thickness:</p>

  <p><strong>t = 8 mm</strong></p>

  <h4>G. Bending Stress Verification</h4>

  <p>
    &sigma; = 6FL / (bt<sup>2</sup>)
  </p>

  <p>
    &sigma; = (6 x 1000 x 40) /
    (80 x 8<sup>2</sup>)
  </p>

  <p><strong>&sigma; = 46.88 MPa</strong></p>

  <p>Comparison:</p>

  <p>46.88 MPa &lt; 69 MPa</p>

  <p>
    <strong>
      Result: The 8 mm bracket satisfies the
      simplified bending calculation.
    </strong>
  </p>

  <h4>H. Preliminary Design Specifications</h4>

  <table border="1" cellpadding="8">
    <tr><th>Feature</th><th>Specification</th></tr>
    <tr><td>Material</td>
        <td>6061-T6 Aluminum</td></tr>
    <tr><td>Plate Thickness</td><td>8 mm</td></tr>
    <tr><td>Frame Attachment</td>
        <td>Four M8 bolts</td></tr>
    <tr><td>Preliminary Bolt Pattern</td>
        <td>80 x 80 mm</td></tr>
    <tr><td>Motor Attachment</td>
        <td>Manufacturer mounting interface</td></tr>
    <tr><td>Quantity</td><td>2</td></tr>
  </table>

  <h4>I. Engineering Conclusion</h4>

  <p>
    A preliminary 8 mm thick 6061-T6 aluminum
    bracket was selected.
  </p>

  <p>
    The calculated bending stress was 46.88 MPa,
    below the allowable stress of 69 MPa,
    for the assumed cantilever geometry.
  </p>

  <p>
    Final verification must include the actual
    bracket dimensions, motor mounting interface,
    bolt forces, local stresses, and load path
    through the upper frame.
  </p>

</section>



<section id="coupler-analysis">

  <h3>3. Coupler Design and Torsional Analysis</h3>

  <p>
    Two couplers are required to connect the Bodine 4762
    gearmotor output shafts to the Acme lead screws.
    Each coupler must transmit rotational torque while
    maintaining proper shaft alignment.
  </p>

  <p>
    A preliminary aluminum coupler was evaluated using
    torsional shear stress calculations. The final
    connection geometry must match the motor output
    shaft and the machined lead screw ends.
  </p>

  <figure>
    <img src="COUPLER.jpg"
         alt="Preliminary shaft coupler design"
         width="500">
  </figure>

  <h4>A. Known Values</h4>

  <table border="1" cellpadding="8">
    <tr><th>Parameter</th><th>Value</th></tr>
    <tr><td>Motor Output Shaft Diameter</td>
        <td>19.05 mm (0.75 in)</td></tr>
    <tr><td>Acme Lead Screw Nominal Diameter</td>
        <td>12.7 mm (0.50 in)</td></tr>
    <tr><td>Motor Rated Torque</td>
        <td>32.77 N&#183;m</td></tr>
    <tr><td>Factor of Safety</td><td>4</td></tr>
    <tr><td>Material</td><td>6061-T6 Aluminum</td></tr>
    <tr><td>Yield Strength</td><td>276 MPa</td></tr>
    <tr><td>Selected Outside Diameter</td>
        <td>35 mm</td></tr>
    <tr><td>Quantity</td><td>2</td></tr>
  </table>

  <h4>B. Coupler Design Torque</h4>

  <p>
    The coupler was conservatively sized using four
    times the rated output torque of the motor.
  </p>

  <p>
    T<sub>design</sub> =
    FS &times; T<sub>rated</sub>
  </p>

  <p>
    T<sub>design</sub> = 4 &times; 32.77
  </p>

  <p>
    <strong>
      T<sub>design</sub> = 131.08 N&#183;m
    </strong>
  </p>

  <p>
    Converting to N&#183;mm:
  </p>

  <p>
    T<sub>design</sub> = 131,080 N&#183;mm
  </p>

  <h4>C. Allowable Shear Stress</h4>

  <p>
    For a ductile material, the von Mises estimate
    of shear yield strength is:
  </p>

  <p>
    &tau;<sub>yield</sub> =
    &sigma;<sub>y</sub> / &radic;3
  </p>

  <p>
    &tau;<sub>yield</sub> = 276 / &radic;3
  </p>

  <p>
    <strong>
      &tau;<sub>yield</sub> = 159.35 MPa
    </strong>
  </p>

  <p>
    Because the design torque already includes a
    factor of safety of 4, the design stress is
    compared with the estimated shear yield
    strength without applying that factor again.
  </p>

  <h4>D. Coupler Torsion Equation</h4>

  <p>
    For a uniform hollow circular shaft:
  </p>

  <p>
    &tau;<sub>max</sub> = Tc / J
  </p>

  <p>
    J = &pi;(D<sub>o</sub><sup>4</sup> -
    D<sub>i</sub><sup>4</sup>) / 32
  </p>

  <p>
    c = D<sub>o</sub> / 2
  </p>

  <p>
    Substituting:
  </p>

  <p>
    &tau;<sub>max</sub> =
    16TD<sub>o</sub> /
    [&pi;(D<sub>o</sub><sup>4</sup> -
    D<sub>i</sub><sup>4</sup>)]
  </p>

  <p>
    The maximum bore diameter was taken as
    19.05 mm to represent the motor shaft end.
  </p>

  <h4>E. Preliminary Coupler Diameter</h4>

  <p>
    Using:
  </p>

  <p>
    T = 131,080 N&#183;mm
  </p>

  <p>
    D<sub>i</sub> = 19.05 mm
  </p>

  <p>
    &tau;<sub>yield</sub> = 159.35 MPa
  </p>

  <p>
    Solve:
  </p>

  <p>
    159.35 =
    (16 &times; 131,080 &times; D<sub>o</sub>) /
    [&pi;(D<sub>o</sub><sup>4</sup> -
    19.05<sup>4</sup>)]
  </p>

  <p>
    <strong>
      Minimum outside diameter is approximately
      21.9 mm.
    </strong>
  </p>

  <p>
    A larger preliminary diameter was selected:
  </p>

  <p>
    <strong>D<sub>o</sub> = 35 mm</strong>
  </p>

  <h4>F. Coupler Wall Thickness</h4>

  <p>
    Minimum wall thickness at the larger bore:
  </p>

  <p>
    t = (D<sub>o</sub> - D<sub>i</sub>) / 2
  </p>

  <p>
    t = (35 - 19.05) / 2
  </p>

  <p>
    <strong>t = 7.975 mm</strong>
  </p>

  <h4>G. Torsional Stress Verification</h4>

  <p>
    Substitute the selected dimensions into the
    hollow-shaft torsion equation:
  </p>

  <p>
    &tau;<sub>max</sub> =
    (16 &times; 131,080 &times; 35) /
    [&pi;(35<sup>4</sup> - 19.05<sup>4</sup>)]
  </p>

  <p>
    <strong>
      &tau;<sub>max</sub> &asymp; 17.07 MPa
    </strong>
  </p>

  <p>
    Since:
  </p>

  <p>
    17.07 MPa &lt; 159.35 MPa
  </p>

  <p>
    The selected 35 mm outside diameter passes
    this preliminary idealized torsional
    stress check.
  </p>

  <h4>H. Coupler Load Diagram</h4>

  <figure>
    <img src="COUPLER2.jpg"
         alt="Coupler torsional loading diagram"
         width="500">
  </figure>

  <h4>I. Preliminary Design Specifications</h4>

  <table border="1" cellpadding="8">
    <tr><th>Feature</th><th>Specification</th></tr>
    <tr><td>Material</td>
        <td>6061-T6 Aluminum</td></tr>
    <tr><td>Outside Diameter</td><td>35 mm</td></tr>
    <tr><td>Motor-Side Bore</td><td>19.05 mm</td></tr>
    <tr><td>Lead Screw Side</td>
        <td>Machined shaft journal required</td></tr>
    <tr><td>Connection Method</td>
        <td>To be finalized</td></tr>
    <tr><td>Quantity</td><td>2</td></tr>
  </table>

  <h4>J. Engineering Conclusion</h4>

  <p>
    A preliminary 35 mm outside diameter
    aluminum coupler was selected.
  </p>

  <p>
    At a design torque of 131.08 N&#183;m,
    the idealized maximum torsional shear stress
    is approximately 17.07 MPa, below the
    estimated material shear yield strength
    of 159.35 MPa.
  </p>

  <p>
    This calculation assumes an uninterrupted
    hollow circular section. Keyways, set screws,
    shaft engagement, stress concentrations,
    misalignment, and the actual machined lead screw
    journal must still be verified before fabrication.
  </p>

</section>


<section id="frame-connection-analysis">

  <h3>4. Frame Connections and Twisting Analysis</h3>

  <p>
    The tensile testing machine uses heavy-duty
    40-series aluminum T-slot extrusions to form
    its supporting frame.
  </p>

  <p>
    The upper frame connections must resist the
    reaction torque transmitted by the motors while
    maintaining alignment of the two Acme lead screws.
  </p>

  <p>
    Preliminary calculations were performed to estimate
    frame twisting loads and identify suitable
    connection hardware.
  </p>

  <figure>
    <img src="FRAME.jpg"
         alt="Frame connection design" width="500">
  </figure>

  <h4>A. Known Values</h4>

  <table border="1" cellpadding="8">
    <tr><th>Parameter</th><th>Value</th></tr>
    <tr><td>Frame Material</td>
        <td>40-Series Aluminum T-Slot</td></tr>
    <tr><td>Motor Quantity</td><td>2</td></tr>
    <tr><td>Rated Torque per Motor</td>
        <td>32.77 N&#183;m</td></tr>
    <tr><td>Estimated Operating Torque per Screw</td>
        <td>1.30 N&#183;m</td></tr>
    <tr><td>Preliminary Force Couple Spacing</td>
        <td>200 mm</td></tr>
    <tr><td>Proposed Bracket</td>
        <td>80/20 Part 40-4303</td></tr>
    <tr><td>Proposed Bracket Quantity</td>
        <td>4</td></tr>
  </table>

  <p>
    The 200 mm distance is an assumed effective
    moment-resisting lever arm. The actual connection
    spacing must be confirmed from the CAD assembly.
  </p>

  <h4>B. Total Motor Reaction Torque</h4>

  <p>
    For a conservative preliminary loading case,
    assume both motors transmit rated torque
    in the same rotational direction.
  </p>

  <p>
    M<sub>total</sub> = T<sub>1</sub> + T<sub>2</sub>
  </p>

  <p>
    M<sub>total</sub> = 32.77 + 32.77
  </p>

  <p>
    <strong>M<sub>total</sub> = 65.54 N&#183;m</strong>
  </p>

  <p>
    The corresponding estimated normal operating
    torque is:
  </p>

  <p>
    M<sub>operating</sub> = 2 &times; 1.30
  </p>

  <p>
    <strong>M<sub>operating</sub> = 2.60 N&#183;m</strong>
  </p>

  <p>
    The rated-torque case was used to investigate
    a more conservative frame loading condition.
  </p>

  <h4>C. Equivalent Connection Reaction Force</h4>

  <p>
    Approximate the twisting moment as a pair
    of equal and opposite forces separated by
    an effective distance S.
  </p>

  <p>
    M = R &times; S
  </p>

  <p>
    R = M / S
  </p>

  <p>
    Assumed spacing:
  </p>

  <p>S = 200 mm = 0.200 m</p>

  <p>
    R = 65.54 / 0.200
  </p>

  <p>
    <strong>R = 327.7 N</strong>
  </p>

  <p>
    Therefore, the preliminary rated-torque
    load case corresponds to an equivalent
    force couple of 327.7 N.
  </p>

  <p>
    This is an equivalent static reaction estimate.
    It is not necessarily the load carried by
    an individual bracket or bolt.
  </p>

  <h4>D. Frame Connection Free-Body Diagram</h4>

  <figure>
    <img src="FRAME2.jpg"
         alt="Frame twisting free-body diagram"
         width="500">
  </figure>

  <h4>E. Connection Bolt Group Analysis</h4>

  <p>
    For a bolt group subjected to an in-plane
    moment, a preliminary elastic distribution
    of the moment-induced shear force is:
  </p>

  <p>
    F<sub>i</sub> =
    M &times; r<sub>i</sub> /
    &Sigma;(r<sub>j</sub><sup>2</sup>)
  </p>

  <p>Where:</p>

  <ul>
    <li>
      F<sub>i</sub> = moment-induced force at bolt i
    </li>
    <li>
      M = moment acting on the bolt group
    </li>
    <li>
      r<sub>i</sub> = distance from the bolt
      group centroid to bolt i
    </li>
    <li>
      &Sigma;(r<sub>j</sub><sup>2</sup>) =
      sum of squared bolt distances
    </li>
  </ul>

  <p>
    A numerical bolt-group force cannot be
    finalized until the actual bracket locations,
    number of bolts, and load distribution are
    established in CAD.
  </p>

  <h4>F. Preliminary Bracket Selection</h4>

  <p>
    The proposed connection uses the 80/20
    heavy-duty four-hole inside corner bracket,
    part number 40-4303.
  </p>

  <p>
    Four brackets are included in the preliminary
    parts list to reinforce the upper frame
    connections.
  </p>

  <table border="1" cellpadding="8">
    <tr><th>Feature</th><th>Specification</th></tr>
    <tr><td>Bracket Manufacturer</td><td>80/20</td></tr>
    <tr><td>Bracket Part Number</td><td>40-4303</td></tr>
    <tr><td>Bracket Type</td>
        <td>Four-Hole Wide Inside Corner</td></tr>
    <tr><td>Proposed Quantity</td><td>4</td></tr>
    <tr><td>Frame Type</td>
        <td>Heavy 40-Series T-Slot</td></tr>
    <tr><td>Fasteners</td>
        <td>Compatible T-slot hardware, TBD</td></tr>
  </table>

  <h4>G. Factor of Safety Requirement</h4>

  <p>
    The target factor of safety for the
    design is 4.
  </p>

  <p>
    FS = Connection Capacity / Applied Load
  </p>

  <p>
    For the preliminary force-couple model,
    the relevant applied force is 327.7 N.
  </p>

  <p>
    To meet a factor of safety of 4 in
    this simplified loading model:
  </p>

  <p>
    Required Capacity = 4 &times; 327.7
  </p>

  <p>
    <strong>
      Required Capacity = 1310.8 N
    </strong>
  </p>

  <p>
    This value is the required capacity for
    the modeled reaction force, not an
    independently verified manufacturer
    rating for the selected bracket.
  </p>

  <p>
    A completed connection safety-factor check
    requires the actual load path and published
    bracket, fastener, and T-slot connection
    capacities.
  </p>

  <h4>H. Engineering Conclusion</h4>

  <p>
    The combined rated motor reaction torque
    is estimated as 65.54 N&#183;m.
  </p>

  <p>
    Using an assumed 200 mm effective lever
    arm, this corresponds to an equivalent
    reaction force of 327.7 N.
  </p>

  <p>
    Four 80/20 part 40-4303 corner brackets
    are proposed for the upper frame.
  </p>

  <p>
    Final verification of bracket capacity,
    fastener shear, T-slot resistance,
    extrusion twisting, and the factor of
    safety must be completed using the
    actual CAD geometry and manufacturer data.
  </p>

</section>

<section id="top-frame-fea">

  <h3>5. Top Horizontal Frame FEA</h3>

  <p>
    Finite Element Analysis (FEA) was performed
    in SolidWorks Simulation on the top horizontal
    frame member of the tensile testing machine.
  </p>

  <p>
    The purpose of this analysis was to evaluate
    stress distribution and determine whether
    the frame member satisfies the required
    factor of safety of 4.
  </p>

  <h4>A. Simulation Setup</h4>

  <p>
    The simulation model represents a horizontal
    T-slot aluminum frame member with loads
    applied near the motor mounting locations.
  </p>

  <p>
    The screenshots show restrained regions
    at the beam ends and loads applied near
    two mounting holes.
  </p>

  <p>
    The simulation identifies a material yield
    strength of 215 MPa. The exact material
    assignment, applied force magnitudes,
    torque values, and boundary conditions
    should be verified against the saved
    SolidWorks simulation study.
  </p>

  <h4>B. Coarse Mesh Stress Analysis</h4>

  <figure>
    <img src="stresscoarse.png"
         alt="Coarse mesh von Mises stress"
         width="600">
    <figcaption>
      Figure F1. Coarse mesh von Mises
      stress distribution.
    </figcaption>
  </figure>

  <p>
    Maximum von Mises stress:
  </p>

  <p>
    <strong>34.80 MPa</strong>
  </p>

  <p>
    The greatest stress concentrations appear
    near the loaded mounting holes.
  </p>

  <h4>C. Balanced Mesh Stress Analysis</h4>

  <figure>
    <img src="stressbalanced.png"
         alt="Balanced mesh von Mises stress"
         width="600">
    <figcaption>
      Figure F2. Balanced mesh von Mises
      stress distribution.
    </figcaption>
  </figure>

  <p>
    Maximum von Mises stress:
  </p>

  <p>
    <strong>35.41 MPa</strong>
  </p>

  <h4>D. Fine Mesh Stress Analysis</h4>

  <figure>
    <img src="stressfine.png"
         alt="Fine mesh von Mises stress"
         width="600">
    <figcaption>
      Figure F3. Fine mesh von Mises
      stress distribution.
    </figcaption>
  </figure>

  <p>
    Maximum von Mises stress:
  </p>

  <p>
    <strong>35.15 MPa</strong>
  </p>

  <p>
    The fine mesh shows stress concentrations
    near the mounting holes, while most
    of the beam has considerably lower stress.
  </p>

  <h4>E. Mesh Convergence Comparison</h4>

  <table border="1" cellpadding="8">
    <tr>
      <th>Mesh</th>
      <th>Maximum Stress</th>
    </tr>
    <tr>
      <td>Coarse</td>
      <td>34.80 MPa</td>
    </tr>
    <tr>
      <td>Balanced</td>
      <td>35.41 MPa</td>
    </tr>
    <tr>
      <td>Fine</td>
      <td>35.15 MPa</td>
    </tr>
  </table>

  <p>
    Percent difference between balanced
    and fine mesh stress results:
  </p>

  <p>
    Difference =
    |35.41 - 35.15| / 35.15 x 100
  </p>

  <p>
    <strong>Difference = 0.74%</strong>
  </p>

  <p>
    The maximum stresses are relatively
    consistent across all three mesh settings.
  </p>

  <p>
    This provides preliminary evidence of
    stress-result convergence. A complete
    mesh convergence study should additionally
    report element sizes or element counts
    and confirm consistent loading and
    boundary conditions.
  </p>

  <h4>F. Factor of Safety Analysis</h4>

  <p>
    The factor of safety was evaluated
    relative to yielding.
  </p>

  <p>
    FS = Yield Strength / Maximum Stress
  </p>

  <p>
    Yield strength = 215 MPa
  </p>

  <p>
    Fine mesh maximum stress = 35.15 MPa
  </p>

  <p>
    FS = 215 / 35.15
  </p>

  <p>
    <strong>FS = 6.12</strong>
  </p>

  <p>
    Required factor of safety = 4
  </p>

  <p>
    <strong>6.12 &gt; 4</strong>
  </p>

  <p>
    Therefore, the modeled top horizontal
    frame meets the target factor of
    safety under the simulated loading.
  </p>

  <h4>G. Factor of Safety Results</h4>

  <figure>
    <img src="FOScoarse.png"
         alt="Coarse mesh factor of safety"
         width="600">
    <figcaption>
      Figure F4. Coarse mesh factor
      of safety distribution.
    </figcaption>
  </figure>

  <figure>
    <img src="FOSbalanced.png"
         alt="Balanced mesh factor of safety"
         width="600">
    <figcaption>
      Figure F5. Balanced mesh factor
      of safety distribution.
    </figcaption>
  </figure>

  <figure>
    <img src="FOSfine.png"
         alt="Fine mesh factor of safety"
         width="600">
    <figcaption>
      Figure F6. Fine mesh factor
      of safety distribution.
    </figcaption>
  </figure>

  <table border="1" cellpadding="8">
    <tr>
      <th>Mesh</th>
      <th>Approx. Minimum FS</th>
    </tr>
    <tr>
      <td>Coarse</td>
      <td>6.18</td>
    </tr>
    <tr>
      <td>Balanced</td>
      <td>6.07</td>
    </tr>
    <tr>
      <td>Fine</td>
      <td>6.12</td>
    </tr>
  </table>

  <p>
    The minimum factors of safety shown
    in all three simulation screenshots
    exceed the required value of 4.
  </p>

  <h4>H. Displacement Verification</h4>

  <p>
    A numerical displacement result for
    the isolated top beam was not included
    among the supplied screenshots.
  </p>

  <p>
    The maximum displacement and its
    location should be added from the
    SolidWorks simulation study.
  </p>

  <h4>I. Engineering Conclusion</h4>

  <p>
    The fine mesh simulation reported a
    maximum von Mises stress of 35.15 MPa
    and a minimum factor of safety of
    approximately 6.12.
  </p>

  <p>
    The balanced and fine mesh stress
    results differed by approximately
    0.74 percent, suggesting that the
    reported maximum stress is reasonably
    stable across these mesh settings.
  </p>

  <p>
    The frame passes the preliminary
    strength check for the modeled
    loading conditions.
  </p>

  <p>
    Final validation requires confirmation
    of the applied loads, supports,
    mesh settings, and displacement
    results in SolidWorks.
  </p>

</section>

<section id="vertical-frame-fea">

  <h3>6. Vertical Frame FEA</h3>

  <p>
    Finite Element Analysis was performed in
    SolidWorks Simulation on the supporting frame
    of the tensile testing machine.
  </p>

  <p>
    The purpose of this analysis was to examine
    stress distribution throughout the frame,
    including the vertical support members,
    under the applied loading conditions.
  </p>

  <h4>A. Frame Model and Loading</h4>

  <p>
    The frame consists of vertical aluminum
    T-slot extrusion members connected by
    upper and lower horizontal supports.
  </p>

  <p>
    The provided simulation screenshots show
    applied loads near the motor mounting
    locations on the upper horizontal member.
  </p>

  <p>
    Restraints are visible near the base
    of the frame.
  </p>

  <figure>
    <img src="coarsedisp.png"
         alt="Frame simulation model and restraints"
         width="600">
    <figcaption>
      Figure V1. Frame simulation model showing
      loading locations and support restraints.
    </figcaption>
  </figure>

  <p>
    The image illustrates the simulation setup.
    It does not provide a numerical displacement
    result.
  </p>

  <h4>B. Von Mises Stress Analysis</h4>

  <p>
    The provided full-frame simulation shows
    the von Mises stress distribution across
    the supporting structure.
  </p>

  <figure>
    <img src="framecoarse.png"
         alt="Full frame von Mises stress analysis"
         width="600">
    <figcaption>
      Figure V2. Coarse mesh stress analysis
      of the complete supporting frame.
    </figcaption>
  </figure>

  <p>
    Maximum von Mises stress:
  </p>

  <p>
    <strong>
      Maximum Stress = 34.54 MPa
    </strong>
  </p>

  <p>
    The highest stresses appear near the
    loaded regions of the upper horizontal
    frame member.
  </p>

  <p>
    Most of the vertical frame members
    appear blue in the stress plot,
    indicating comparatively lower stresses
    within the displayed color scale.
  </p>

  <p>
    The 34.54 MPa maximum applies to the
    full-frame model. It should not be
    interpreted as a separately measured
    maximum stress in the vertical members.
  </p>

  <h4>C. Material Yield Strength</h4>

  <p>
    The SolidWorks stress plot identifies
    the material yield strength as:
  </p>

  <p>
    <strong>
      Yield Strength = 215 MPa
    </strong>
  </p>

  <h4>D. Factor of Safety Calculation</h4>

  <p>
    The estimated factor of safety
    against yielding is calculated using:
  </p>

  <p>
    FS = Yield Strength / Maximum Stress
  </p>

  <p>
    FS = 215 / 34.54
  </p>

  <p>
    <strong>FS = 6.22</strong>
  </p>

  <p>
    Required factor of safety:
  </p>

  <p><strong>FS(required) = 4</strong></p>

  <p>
    Comparison:
  </p>

  <p><strong>6.22 &gt; 4</strong></p>

  <p>
    The full-frame model therefore satisfies
    the preliminary yield-strength criterion
    under the simulated loading conditions.
  </p>

  <h4>E. Mesh Analysis</h4>

  <p>
    The available full-frame stress screenshot
    corresponds to a coarse mesh simulation.
  </p>

  <p>
    A separate balanced and fine mesh
    comparison for the complete frame
    was not included in the provided files.
  </p>

  <p>
    Therefore, numerical mesh convergence
    for the vertical frame analysis
    cannot be established from the
    available screenshots.
  </p>

  <h4>F. Displacement Analysis</h4>

  <p>
    The supplied frame images show the
    geometry, applied loads, and constraints,
    but do not display a numerical
    displacement contour result.
  </p>

  <p>
    Consequently, the maximum displacement
    of the vertical supports cannot
    be reported from the available data.
  </p>

  <h4>G. Engineering Conclusion</h4>

  <p>
    The full-frame SolidWorks simulation
    reported a maximum von Mises stress
    of approximately 34.54 MPa.
  </p>

  <p>
    Using the material yield strength
    of 215 MPa shown in the simulation,
    the estimated factor of safety
    against yielding is 6.22.
  </p>

  <p>
    This exceeds the required factor
    of safety of 4 for the modeled
    static loading conditions.
  </p>

  <p>
    The available results provide
    preliminary evidence that the
    overall frame can withstand the
    simulated loads without yielding.
  </p>

  <p>
    However, vertical-member-specific
    results, displacement values,
    mesh convergence, and possible
    buckling behavior require further
    verification before the structure
    can be considered fully validated.
  </p>

</section>



<section id="floating-bearing-analysis">

  <h3>7. Floating Bearing Mount Design</h3>

  <p>
    Two floating bearing mounts are proposed for
    the lower ends of the Acme lead screws in the
    tensile testing machine.
  </p>

  <p>
    The upper fixed bearing supports are intended
    to carry the axial thrust loads, while the lower
    floating bearings provide radial support and
    allow axial movement caused by thermal expansion
    and manufacturing tolerances.
  </p>

  <p>
    The floating mounts must maintain proper
    alignment without overconstraining the
    lead screws.
  </p>

  <figure>
    <img src="FLOAT.jpg"
         alt="Floating bearing mount concept"
         width="500">
  </figure>

  <h4>A. Preliminary Design Specifications</h4>

  <table border="1" cellpadding="8">
    <tr><th>Parameter</th><th>Value</th></tr>
    <tr><td>Number of Floating Mounts</td>
        <td>2</td></tr>
    <tr><td>Support Material</td>
        <td>6061-T6 Aluminum</td></tr>
    <tr><td>Proposed Mount Length</td>
        <td>80 mm</td></tr>
    <tr><td>Proposed Mount Width</td>
        <td>40 mm</td></tr>
    <tr><td>Proposed Mount Thickness</td>
        <td>20 mm</td></tr>
    <tr><td>Proposed Shaft Journal Diameter</td>
        <td>12 mm</td></tr>
    <tr><td>Proposed Mounting Bolts</td>
        <td>2 M8 per mount</td></tr>
    <tr><td>Proposed Bolt Clearance Holes</td>
        <td>9 mm</td></tr>
    <tr><td>Requested Fit Classification</td>
        <td>RC3</td></tr>
  </table>

  <p>
    These dimensions are preliminary and must
    be checked against the final bearing selection,
    lead screw end machining, and CAD assembly.
  </p>

  <h4>B. Fixed and Floating Bearing Arrangement</h4>

  <p>
    The lead screw support arrangement uses
    two different bearing functions:
  </p>

  <ul>
    <li>
      Fixed bearing support: locates the screw
      axially and carries thrust loads.
    </li>
    <li>
      Floating bearing support: supports radial
      loading while allowing axial displacement.
    </li>
  </ul>

  <p>
    This prevents the lead screw from being
    constrained axially at both ends.
  </p>

  <h4>C. Shaft Journal Design</h4>

  <p>
    The Acme lead screw has a nominal outside
    diameter of 12.7 mm.
  </p>

  <p>
    A proposed 12 mm diameter machined journal
    is used at the floating bearing location.
  </p>

  <p>
    <strong>
      d<sub>journal</sub> = 12 mm
    </strong>
  </p>

  <p>
    The bearing must contact the smooth
    machined journal rather than the
    Acme screw threads.
  </p>

  <p>
    Final journal length, shoulder geometry,
    surface finish, and bearing engagement
    must be determined after selecting
    the actual bearing.
  </p>

  <h4>D. RC3 Running Fit</h4>

  <p>
    An RC3 precision running fit is proposed
    for the shaft and mating bore where
    relative sliding or rotation is intended.
  </p>

  <p>
    Diametral clearance is calculated by:
  </p>

  <p>
    C = D<sub>bore</sub> - d<sub>shaft</sub>
  </p>

  <p>
    Minimum clearance:
  </p>

  <p>
    C<sub>min</sub> =
    D<sub>bore,min</sub> -
    d<sub>shaft,max</sub>
  </p>

  <p>
    Maximum clearance:
  </p>

  <p>
    C<sub>max</sub> =
    D<sub>bore,max</sub> -
    d<sub>shaft,min</sub>
  </p>

  <p>
    The exact RC3 limits for the selected
    nominal diameter must be taken from
    the applicable ANSI B4.1 fit table.
  </p>

  <p>
    <strong>
      [INSERT VERIFIED RC3 SHAFT AND BORE
      TOLERANCE TABLE HERE]
    </strong>
  </p>

  <p>
    The exact minimum and maximum shaft and
    bore dimensions have not yet been
    established. The final drawing must
    specify both sets of limits.
  </p>

  <p>
    If a rolling-element bearing is selected,
    its shaft and housing fits must instead
    be checked against the bearing
    manufacturer's recommendations.
  </p>

  <h4>E. Floating Bearing Free-Body Diagram</h4>

  <figure>
    <img src="FLOAT2.jpg"
         alt="Floating bearing loading diagram"
         width="500">
  </figure>

  <p>
    The floating bearing provides radial
    reactions but is not intended to
    carry the primary axial thrust.
  </p>

  <p>
    The actual radial reaction must be
    determined from the complete lead screw
    loading and support geometry.
  </p>

  <h4>F. Bearing Pressure Calculation</h4>

  <p>
    For a preliminary plain-bearing model,
    projected bearing pressure is:
  </p>

  <p>
    p = R / (dL<sub>b</sub>)
  </p>

  <p>Where:</p>

  <ul>
    <li>R = radial bearing reaction (N)</li>
    <li>d = journal diameter (mm)</li>
    <li>
      L<sub>b</sub> = effective bearing
      contact length (mm)
    </li>
  </ul>

  <p>
    For an illustrative 12 mm journal and
    20 mm effective bearing length:
  </p>

  <p>
    p = R / (12 &times; 20)
  </p>

  <p>
    <strong>p = R / 240 MPa</strong>
  </p>

  <p>
    In this expression, R is entered in
    newtons and the resulting pressure
    is in N/mm<sup>2</sup>, or MPa.
  </p>

  <p>
    A numerical pressure cannot be completed
    until the actual radial reaction and
    bearing contact length are confirmed.
  </p>

  <h4>G. Mounting Arrangement</h4>

  <p>
    Each floating support is preliminarily
    attached to the lower frame using
    two M8 fasteners.
  </p>

  <p>
    Proposed bolt clearance hole diameter:
  </p>

  <p>
    <strong>d<sub>hole</sub> = 9 mm</strong>
  </p>

  <p>
    Fastener spacing, edge distances, and
    attachment to the 40-series extrusion
    must be finalized in CAD.
  </p>

  <h4>H. Preliminary Design Summary</h4>

  <table border="1" cellpadding="8">
    <tr><th>Feature</th><th>Selection</th></tr>
    <tr><td>Mount Material</td>
        <td>6061-T6 Aluminum</td></tr>
    <tr><td>Mount Dimensions</td>
        <td>80 x 40 x 20 mm (preliminary)</td></tr>
    <tr><td>Journal Diameter</td>
        <td>12 mm (preliminary)</td></tr>
    <tr><td>Fit Type</td>
        <td>RC3 proposed, limits pending</td></tr>
    <tr><td>Mounting Hardware</td>
        <td>2 M8 bolts per mount</td></tr>
    <tr><td>Quantity</td><td>2</td></tr>
  </table>

  <h4>I. Engineering Conclusion</h4>

  <p>
    Two lower floating bearing mounts are
    proposed to support the Acme lead screws
    while permitting axial displacement.
  </p>

  <p>
    A preliminary 6061-T6 aluminum mounting
    block measuring 80 x 40 x 20 mm was
    selected, with a proposed 12 mm
    machined lead screw journal.
  </p>

  <p>
    The actual bearing type, radial load,
    required RC3 dimensional limits, and
    mount strength must still be verified
    before fabrication.
  </p>

</section>



<section id="cost-analysis">

  <h3>8. Combined A10/A11 Bill of Materials and Cost Analysis</h3>

  <p>
    A preliminary bill of materials (BOM) was
    developed for the 2 kN tensile testing machine.
    The BOM combines components selected during
    A10 and A11, including the frame, Acme lead screws,
    drive motors, couplers, mounting brackets,
    and bearing supports.
  </p>

  <p>
    Purchased components, custom-fabricated parts,
    and estimated labor are considered separately.
    Some component prices and manufacturing
    requirements remain to be finalized.
  </p>

  <h4>A. Purchased Components</h4>

  <table border="1" cellpadding="8">
    <tr>
      <th>Component</th>
      <th>Qty.</th>
      <th>Unit Cost</th>
      <th>Total</th>
    </tr>
    <tr>
      <td>Bodine 4762 Gearmotor</td>
      <td>2</td>
      <td>$1,145.44</td>
      <td>$2,290.88</td>
    </tr>
    <tr>
      <td>Roton 59284 Acme Lead Screw</td>
      <td>3 ft total</td>
      <td>$9.10/ft</td>
      <td>$27.30</td>
    </tr>
    <tr>
      <td>Roton 90222 Bronze Nut</td>
      <td>2</td>
      <td>$23.57</td>
      <td>$47.14</td>
    </tr>
    <tr>
      <td>80/20 40-4303 Corner Bracket</td>
      <td>4</td>
      <td>$8.79</td>
      <td>$35.16</td>
    </tr>
    <tr>
      <td colspan="3">
        <strong>Priced Components Subtotal</strong>
      </td>
      <td><strong>$2,400.48</strong></td>
    </tr>
  </table>

  <p>
    The listed prices are preliminary estimates
    and should be verified with current supplier
    quotations before final purchasing.
  </p>

  <p>
    The 3 ft lead screw estimate assumes two
    18-inch pieces can be obtained without
    additional material or cutting allowances.
  </p>

  <h4>B. Frame Material Cost</h4>

  <p>
    Heavy 40-series aluminum T-slot extrusion
    was selected for the supporting frame.
  </p>

  <p>Estimated total extrusion length:</p>

  <p><strong>L = 2160 mm</strong></p>

  <p>Estimated cost per millimeter:</p>

  <p><strong>C = $0.0821/mm</strong></p>

  <p>Material cost:</p>

  <p>C<sub>material</sub> = L &times; C</p>

  <p>C<sub>material</sub> = 2160 &times; 0.0821</p>

  <p><strong>C<sub>material</sub> = $177.34</strong></p>

  <p>Estimated cutting cost:</p>

  <p>4 cuts &times; $3.79/cut = $15.16</p>

  <p>Total estimated frame cost:</p>

  <p>C<sub>frame</sub> = 177.34 + 15.16</p>

  <p><strong>C<sub>frame</sub> = $192.50</strong></p>

  <p>
    The 2160 mm frame length and number of
    cuts are preliminary assumptions.
    The final material cost must be updated
    from the completed CAD frame dimensions.
  </p>

  <h4>C. Additional Components Requiring Pricing</h4>

  <table border="1" cellpadding="8">
    <tr>
      <th>Component</th>
      <th>Qty.</th>
      <th>Status</th>
    </tr>
    <tr>
      <td>Roton 89838 Nut Mounting Flanges</td>
      <td>2</td>
      <td>Price pending</td>
    </tr>
    <tr>
      <td>Custom Crosshead</td>
      <td>1</td>
      <td>Material and machining cost pending</td>
    </tr>
    <tr>
      <td>Motor Mounting Brackets</td>
      <td>2</td>
      <td>Material and fabrication cost pending</td>
    </tr>
    <tr>
      <td>Motor-to-Lead-Screw Couplers</td>
      <td>2</td>
      <td>Material and fabrication cost pending</td>
    </tr>
    <tr>
      <td>Floating Bearing Mounts</td>
      <td>2</td>
      <td>Material and fabrication cost pending</td>
    </tr>
    <tr>
      <td>Fixed Bearing Supports</td>
      <td>2</td>
      <td>Selection and pricing pending</td>
    </tr>
    <tr>
      <td>Bearings</td>
      <td>TBD</td>
      <td>Selection and pricing pending</td>
    </tr>
    <tr>
      <td>Specimen Grips</td>
      <td>2 sets</td>
      <td>Selection and pricing pending</td>
    </tr>
    <tr>
      <td>Fasteners and T-Slot Hardware</td>
      <td>TBD</td>
      <td>Quantity and pricing pending</td>
    </tr>
  </table>

  <p>
    These components must be included in the
    final complete BOM. The current subtotal
    does not include their costs.
  </p>

  <h4>D. Labor Cost Analysis</h4>

  <p>
    The assignment specifies a labor rate
    of $35 per hour.
  </p>

  <p>
    Labor Cost = Total Hours &times; Hourly Rate
  </p>

  <p>
    For a preliminary example, assume
    20 total engineering and fabrication hours:
  </p>

  <p>Labor Cost = 20 &times; $35</p>

  <p><strong>Estimated Labor Cost = $700.00</strong></p>

  <p>
    The 20-hour value is an example only.
    It must be replaced with the team's
    actual recorded engineering, CAD,
    analysis, and fabrication hours.
  </p>

  <h4>E. Preliminary Cost Summary</h4>

  <table border="1" cellpadding="8">
    <tr>
      <th>Category</th>
      <th>Estimated Cost</th>
    </tr>
    <tr>
      <td>Priced Purchased Components</td>
      <td>$2,400.48</td>
    </tr>
    <tr>
      <td>Estimated Frame Material and Cuts</td>
      <td>$192.50</td>
    </tr>
    <tr>
      <td>Example Labor Estimate</td>
      <td>$700.00</td>
    </tr>
    <tr>
      <td>
        <strong>Preliminary Partial Total</strong>
      </td>
      <td><strong>$3,292.98</strong></td>
    </tr>
  </table>

  <p>
    Total = $2,400.48 + $192.50 + $700.00
  </p>

  <p><strong>Total = $3,292.98</strong></p>

  <p>
    This is a partial cost estimate, not
    the complete manufacturing cost.
    Additional components, machining,
    hardware, and actual labor hours
    must be included before the final
    project cost can be determined.
  </p>

  <h4>F. Supporting Documentation</h4>

  <p>
    The final submission should include
    supplier pricing evidence and the
    completed bill of materials.
  </p>

  <p>
    <strong>
      [INSERT SUPPLIER PRICE SCREENSHOTS HERE]
    </strong>
  </p>

  <p>
    <strong>
      [INSERT COMPLETE BOM IMAGE OR TABLE HERE]
    </strong>
  </p>

  <h4>G. Engineering Conclusion</h4>

  <p>
    The preliminary combined A10/A11
    cost estimate is $3,292.98, including
    an illustrative labor allowance.
  </p>

  <p>
    The two Bodine 4762 gearmotors represent
    the largest identified purchased cost.
  </p>

  <p>
    The final BOM must be updated after
    component selection, CAD verification,
    supplier pricing, and team labor
    documentation are completed.
  </p>

</section>



## Decide

<section id="cad-design">

  <h2>Design</h2>
  <h3>CAD Modeling and Assembly</h3>

  <p>
    The A11 design builds upon the tensile testing
    machine developed during A10. Additional
    components were modeled in SolidWorks to
    incorporate the motor drive system, motor
    mounting plates, shaft couplers, and
    supporting frame.
  </p>

  <p>
    The CAD models allow the team to visualize
    component positioning, examine mounting
    interfaces, and assess the overall
    assembly configuration.
  </p>

  <h4>A. Selected Motor</h4>

  <p>
    The proposed drive system uses two Bodine
    Electric Model 4762 DC gearmotors, with
    one motor positioned above each lead screw.
  </p>

  <p>
    Motor dimensions and mounting features
    must be checked against the manufacturer
    drawing to ensure proper assembly.
  </p>

  <figure>
    <img src="motor.png"
         alt="Bodine 4762 gearmotor"
         width="500">
    <figcaption>
      Figure D1. Selected Bodine Electric
      Model 4762 gearmotor.
    </figcaption>
  </figure>

  <h4>B. Motor Mounting Plate</h4>

  <p>
    A mounting plate was modeled to support
    the motor and provide an attachment
    interface to the testing machine frame.
  </p>

  <p>
    The CAD images show the plate geometry,
    mounting hole arrangement, and the
    motor-to-plate interface.
  </p>

  <figure>
    <img src="plate.png"
         alt="Motor mounting plate"
         width="500">
    <figcaption>
      Figure D2. Motor mounting plate model.
    </figcaption>
  </figure>

  <figure>
    <img src="plateholes.png"
         alt="Mounting plate dimensions and holes"
         width="500">
    <figcaption>
      Figure D3. Mounting plate hole layout
      and dimensional features.
    </figcaption>
  </figure>

  <figure>
    <img src="boltholes.png"
         alt="Motor mounting hole configuration"
         width="500">
    <figcaption>
      Figure D4. Motor mounting hole
      arrangement.
    </figcaption>
  </figure>

  <figure>
    <img src="boltsholesonplate.png"
         alt="Motor and mounting plate alignment"
         width="500">
    <figcaption>
      Figure D5. Motor and mounting plate
      attachment alignment.
    </figcaption>
  </figure>

  <figure>
    <img src="plateandmotor.png"
         alt="Motor and mounting plate"
         width="500">
    <figcaption>
      Figure D6. Motor and mounting plate
      CAD components.
    </figcaption>
  </figure>

  <h4>C. Motor Mount Assembly</h4>

  <p>
    The motor and mounting plate were
    assembled to illustrate the proposed
    connection between the motor housing
    and the support structure.
  </p>

  <figure>
    <img
      src="Screenshot 2026-11-23 210526.png"
      alt="Motor mounting assembly"
      width="500">
    <figcaption>
      Figure D7. Motor mounting assembly
      modeled in SolidWorks.
    </figcaption>
  </figure>

  <h4>D. Shaft Coupler</h4>

  <p>
    A shaft coupler was modeled to connect
    the motor output shaft to the lead screw.
  </p>

  <p>
    The CAD model shows a cylindrical body
    with an internal bore and keyway feature.
    The final mating dimensions must match
    the selected motor shaft and machined
    lead screw end.
  </p>

  <figure>
    <img src="coupler.png"
         alt="Shaft coupler CAD model"
         width="500">
    <figcaption>
      Figure D8. Shaft coupler model.
    </figcaption>
  </figure>

  <p>
    The associated SolidWorks part and
    drawing files are provided with the
    team's CAD deliverables.
  </p>

  <h4>E. Updated Tensile Testing Assembly</h4>

  <p>
    The existing A10 frame assembly was
    updated to incorporate the proposed
    motor arrangement.
  </p>

  <p>
    The assembly image shows two motors
    at the upper portion of the frame,
    with a horizontal crosshead positioned
    between the vertical supports.
  </p>

  <figure>
    <img src="finished.png"
         alt="Updated tensile testing assembly"
         width="600">
    <figcaption>
      Figure D9. Updated tensile testing
      machine assembly.
    </figcaption>
  </figure>

  <h4>F. Assembly Verification</h4>

  <p>
    The CAD models provide a preliminary
    representation of the motor mounting
    arrangement, coupler design, and
    overall machine configuration.
  </p>

  <p>
    Before fabrication, the final assembly
    must be checked for shaft alignment,
    bearing support locations, fastener
    clearances, crosshead travel, and
    compatibility between mating components.
  </p>

  <p>
    The provided assembly screenshots do
    not independently establish the final
    bearing arrangement or verify all
    mechanical interfaces.
  </p>

  <h4>G. SolidWorks Deliverables</h4>

  <p>
    The CAD package includes the following
    native SolidWorks files:
  </p>

  <ul>
    <li>finalassembly.SLDASM</li>
    <li>motorandbracketassm.SLDASM</li>
    <li>coupler.SLDPRT</li>
    <li>couplerdrawing.SLDDRW</li>
    <li>motordrawing.SLDDRW</li>
  </ul>

  <p>
    These files should be included in the
    downloadable CAD package. Assembly
    dependencies should be checked so the
    models open correctly on another computer.
  </p>

</section>


## Communicate

<section id="communication">

  <h2>Communication and Lessons Learned</h2>

  <h3>Team Member Contributions</h3>

  <p>
    The A11 tensile testing machine project was
    completed through collaboration between
    three team members. Responsibilities were
    divided between engineering analysis,
    CAD modeling, simulation, and documentation.
  </p>

  <table border="1" cellpadding="8">
    <tr>
      <th>Team Member</th>
      <th>Responsibilities</th>
    </tr>
    <tr>
      <td>Mason</td>
      <td>
        Engineering calculations, motor selection,
        motor mounting analysis, coupler analysis,
        frame connection analysis, floating bearing
        analysis, bill of materials, cost analysis,
        and GitHub documentation.
      </td>
    </tr>
    <tr>
      <td>Jakub</td>
      <td>
        CAD modeling, component design, and
        assembly development in SolidWorks.
      </td>
    </tr>
    <tr>
      <td>Amaha</td>
      <td>
        CAD modeling, component design, and
        assembly development in SolidWorks.
      </td>
    </tr>
  </table>

  <h3>Time Spent on Project</h3>

  <table border="1" cellpadding="8">
    <tr>
      <th>Work</th>
      <th>Hours</th>
    </tr>
    <tr>
      <td>CAD Modeling and Assembly
          (Jakub and Amaha combined)</td>
      <td>12 hours</td>
    </tr>
    <tr>
      <td>Engineering Analysis and Documentation
          (Mason)</td>
      <td>To be recorded</td>
    </tr>
  </table>

  <p>
    The labor rate used for the project cost
    analysis is $35 per hour.
  </p>

  <p>
    CAD labor cost = 12 x $35
  </p>

  <p>
    <strong>CAD Labor Cost = $420</strong>
  </p>

  <p>
    The total team labor cost will be updated
    when all individual work hours are recorded.
  </p>

  <h3>Lessons Learned</h3>

  <p>
    One important lesson from A11 was the
    relationship between component selection,
    engineering calculations, and CAD design.
    The motor, couplers, brackets, and bearing
    supports must be compatible for the complete
    machine to function properly.
  </p>

  <p>
    The project also demonstrated the importance
    of using finite element analysis to evaluate
    stresses and factors of safety in structural
    components before manufacturing.
  </p>

  <p>
    Another lesson was the importance of team
    communication. Dividing the engineering
    analysis and CAD responsibilities allowed
    different parts of the design to be developed,
    but required coordination to ensure that
    the final models matched the calculations.
  </p>

  <p>
    Overall, A11 provided experience in
    mechanical design, CAD assembly,
    structural analysis, cost estimation,
    and collaborative engineering.
  </p>

</section>

