# A6 – [Topic]

## Objective
The objective of this assignment was to use the strength and stiffness analysis from the previous bracket assignment to create a parametric solid model and a fully dimensioned engineering drawing. Since stress was the governing design requirement, I used the stress-based design as the basis for the CAD model. The model was created so that important dimensions were controlled by parameters and engineering equations rather than only manually entered dimensions. I then created a third-angle multiview engineering drawing with dimensions, fit tolerances, and a general tolerance block.

## Analyze
### Parametric Design

I created the bracket in SolidWorks using the stress-based design developed in the previous assignment. Instead of treating every dimension as an independent value, I created global variables and equations for the important design inputs and calculated dimensions. This allowed changes to an input parameter to automatically update related dimensions in the model.

I used parameters for the applied force, factor of safety, yield strength, feature dimensions, T-beam interface dimensions, and calculated stress-based dimensions.

### Feature A

Feature A supports the strap and was modeled using the cantilever-beam stress analysis from the previous assignment. I created parameters for the 600 lbf applied force, factor of safety, yield strength, and Feature A length.

The bending moment and required section modulus were calculated parametrically. The required radius was then calculated from the section modulus for a circular cross section, and the diameter was defined as twice the radius. This resulted in a Feature A diameter of approximately 0.849 in.

The actual diameter of Feature A in the CAD model was linked to this calculated diameter rather than manually entering the final value.

### Feature B

Feature B was modeled as an axially loaded member based on the analysis from the previous assignment. The load transferred from Feature A was used with the allowable stress to calculate the required cross-sectional area of Feature B.

The width of Feature B was related to the dimensions established by Feature A, while the required thickness was calculated from the required area. The 1.00 in length of Feature B was maintained as a selected design dimension and was also included as a parameter.

### Feature C

Feature C was modeled as a simply supported beam with a concentrated load at its center. Parameters were created for its span, depth, maximum bending moment, required section modulus, and required thickness.

During the CAD process, I changed the selected depth of Feature C from 4.00 in to 2.00 in to create a more practical overall geometry. Because the thickness was controlled by the stress equation, SolidWorks automatically recalculated the required Feature C thickness when the depth changed. This demonstrated the advantage of using parametric modeling because I did not have to manually redo the geometry after changing the design parameter.
### Features D and E

Features D and E transfer the reactions from Feature C into the rigid T-beam interface. Both were modeled using the axial stress relationships developed in the previous assignment.

The required cross-sectional areas were calculated from the applied load and allowable stress. These areas were then combined with the corresponding T-beam interface dimensions to calculate the required thicknesses. Feature D required approximately 0.040 in, while Feature E required approximately 0.060 in.

These calculated values were included as parameters so changes to the loading or material properties could propagate through the model.
T-Beam Interface Parameters

The supplied rigid T-beam dimensions were also added as parameters so that the mating geometry could be controlled independently from the structural calculations. The interface dimensions used were:

\(a = 0.498\) in
\(b = 0.9992\) in
\(c = 1.499\) in

These parameters controlled the dimensions of the T-shaped opening in the bracket. Separating the interface dimensions from the stress-calculated dimensions made it easier to maintain the required fit while still allowing the structural dimensions to update.

### Final Parametric CAD Model

After linking the important CAD dimensions to the global variables and equations, I rebuilt the model and verified that changing a parameter caused the corresponding geometry to update. The final model maintained the T-shaped interface with the rigid T-beam while using the dimensions determined from the governing stress analysis.

The parametric model also allowed selected design dimensions to be changed while automatically recalculating dependent dimensions. This made the model easier to modify without manually rebuilding individual features.
## Engineering Drawing
### Third-Angle Multiview Drawing

After completing the parametric model, I created an engineering drawing directly from the SolidWorks part. I used third-angle projection and included the front, top, right-side, and isometric views. The top view was placed above the front view, and the right-side view was placed to the right of the front view, following the third-angle projection convention discussed in class.

The orthographic views were dimensioned to communicate the size and location of the important bracket features. The isometric view was included to make the overall geometry easier to visualize but was not used as the primary dimensioned view.

### Dimensioning

I dimensioned the drawing so that the geometry could be interpreted without relying on the 3D CAD model. I used different decimal precision depending on the functional importance of each dimension instead of displaying every dimension with the same number of decimal places.

This follows the purpose of engineering drawings discussed in class, where dimensions communicate size, location, hole information, tolerances, and design intent.

Dimensions that were not critical mating dimensions were given normal drawing precision, while the T-beam interface dimensions retained the precision required for their fits.

### Fit Tolerances

The three rigid T-beam interface dimensions were given explicit unilateral tolerances based on the supplied fit requirements.

For dimension \(a\):

$$ \boxed{0.498^{+0.000}_{-0.001}\text{ in}} $$

For dimension \(b\):

$$ \boxed{0.9992^{+0.0000}_{-0.0005}\text{ in}} $$

For dimension \(c\):

$$ \boxed{1.499^{+0.000}_{-0.001}\text{ in}} $$

These dimensions received explicit tolerances because they control how the bracket interfaces with the rigid T-beam. Their specific tolerances override the general tolerance block on the drawing.
### General Tolerance Block

I added a general tolerance block to the engineering drawing for dimensions that do not have an individually specified tolerance:

$$ X.X\pm0.02\text{ in} $$ $$ X.XX\pm0.01\text{ in} $$ $$ X.XXX\pm0.005\text{ in} $$

I also specified that all drawing dimensions are in inches. This allows the number of displayed decimal places to communicate the default manufacturing tolerance when a separate tolerance is not provided.
## Decide


### Equation-Driven CAD Parameter

One equation that directly controlled the CAD geometry was the bending-stress analysis for Feature A. Feature A was modeled as a cantilever supporting the distributed strap load.

I first defined the design inputs in SolidWorks, including the applied force \(F\), factor of safety \(SF\), yield strength \(S_y\), and Feature A length \(L_A\). The maximum bending moment was then calculated as:

$$ M_A=F L_A $$

The required section modulus was calculated using:

$$ Z_A=\frac{SF\,M_A}{S_y} $$

For the circular cross section of Feature A:

$$ r_A=\sqrt[3]{\frac{4Z_A}{\pi}} $$

and:

$$ D_A=2r_A $$

These equations were entered into the SolidWorks Global Variables/Equations table. The diameter dimension in the Feature A sketch was then linked directly to the calculated \(D_A\) parameter.

This resulted in a diameter of approximately:

$$ \boxed{D_A=0.849\text{ in}} $$

Because the CAD dimension is linked to the analytical equation, changing an input such as the applied force or yield strength causes SolidWorks to recalculate the required diameter and rebuild the model automatically.

[Insert Feature A equation chain screenshot here]

Effect of Parametric Changes

The effect of parametric modeling was also demonstrated when I changed the selected depth of Feature C. The required thickness of a rectangular section was controlled by:

$$ h_C=\sqrt{\frac{6Z_C}{b_C}} $$

When I reduced the selected depth \(b_C\), the required thickness \(h_C\) automatically increased. The CAD geometry rebuilt using the new calculated value without requiring me to manually calculate and re-enter the thickness.

This showed how an analytical engineering relationship can directly control the geometry of a CAD model and maintain the design requirements during design changes.

### Tight vs. Loose Tolerances

A tight tolerance was necessary on the 0.9992 in T-beam interface dimension, which was specified as:

$$ 0.9992^{+0.0000}_{-0.0005}\text{ in} $$

This feature directly affects the fit between the bracket and rigid T-beam, so a small variation could create excessive play or prevent the parts from fitting correctly.

In comparison, a noncritical overall dimension displayed to two decimal places can use the general tolerance:

$$ X.XX\pm0.01\text{ in} $$

because small changes in that dimension do not significantly affect the mating function of the bracket.

The tighter tolerance requires greater manufacturing accuracy and would generally be more difficult and expensive to produce. Therefore, tight tolerances should be applied only where the function of the design requires them.


## Communicate
### Lessons Learned

This assignment helped me understand the connection between engineering analysis, parametric CAD, and manufacturing drawings. In the previous assignment, I calculated the minimum dimensions needed for strength and stiffness, but this assignment showed how those calculations can directly control the CAD geometry instead of only being used to produce numerical answers.

I also learned why it is important to clearly define parameters and understand which dimensions are calculated, selected, or determined by a mating component. Changing Feature C demonstrated how useful parametric modeling can be because dependent dimensions automatically changed with the design.

Creating the engineering drawing also helped me understand why drawings are considered a technical language. A CAD model may make sense to the person who created it, but dimensions, tolerances, views, and standards are necessary for someone else to manufacture the design without having to guess the designer's intent. This matches the course emphasis that drawings communicate what is intended to be built and reduce ambiguity.

### Time Spent

I spent approximately [ENTER TOTAL TIME] hours completing the parametric CAD model, engineering drawing, tolerances, and documentation.

