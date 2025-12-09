---
layout: project
title: Design and Analysis of a Weight-Lifting Mechanism
description: By Aryaman Roongta
technologies: [None]
image: /assets/images/lifting-geometry.jpeg
---

## Constraints and Goal

This design task requires creating a **rigid planar lifting mechanism** inside a 2D envelope of  
150 cm in length and 50 cm in height. The mechanism must use:

- one rigid bar of chosen fixed length,
- three pin supports (with two pins anchored to ground),
- one linear actuator selected from the provided catalog.

The goal is to **lift the maximum possible weight to the highest possible height**, under the idealization that the bar, actuator, and supports are perfectly rigid.

The combination of a strict **vertical limit** (50 cm) and a relatively large **horizontal footprint** (150 cm) strongly suggests a geometry that:

- converts actuator force into a **large moment** about a ground pivot, and  
- allows the boom tip to approach the **top of the design envelope**.

The most efficient interpretation of these constraints is a **single boom (lever) driven by a linear actuator**, which naturally uses exactly three pins:

1. a boom pivot at ground,  
2. an actuator base pivot at ground,  
3. an actuator-to-boom pin.

---

## Actuator Selection Rationale

From the catalog, I selected an actuator with **maximum force capacity** and **largest stroke length** by a significant margin relative to alternatives. The chosen actuator, the RSX, provides up to

\\( F_{\\max} = 294\\,\\text{kN} \\) and \\( \\text{stroke} = 1.5\\,\\text{m} \\).

This choice aligns directly with the project goal. Under the rigid-body idealization, the limiting performance factor is the **available actuator force** and the **mechanical advantage** of the linkage, not structural yielding, buckling, or joint deformation.

The 1.5 m stroke is far larger than the length change required to rotate a short boom within a 50 cm-tall envelope, so the actuator will **not run out of travel** in the intended motion. Instead, the design can be optimized primarily around **maximizing torque transfer** in the most demanding portion of the lift.

---

## Mechanism Architecture

The mechanism consists of:

- A rigid **boom** pinned to ground at point \\( A \\).
- A **linear actuator** pinned to ground at point \\( B \\).
- The actuator rod end pinned to the boom at point \\( C \\).
- The lifted **load** applied at the boom tip \\( D \\).

This configuration uses the three required pin supports:

1. \\( A \\) (ground),
2. \\( B \\) (ground),
3. \\( C \\) (on the boom).

The load point \\( D \\) is **not** a support pin; it is the application point of the lifted weight.

To maximize height within the 50 cm envelope, the boom length should be chosen so that its tip can approach the **top boundary** when the boom is nearly vertical.

---

## Optimized Geometry Choice

The simplest way to guarantee the greatest lifted height inside the 50 cm envelope is to choose a boom length

\\[
L = 0.50\\,\\text{m},
\\]

so that when the boom nears a vertical orientation, the tip height approaches

\\[
h_{\\max} \\approx L = 0.50\\,\\text{m}.
\\]

This is essentially the **maximum feasible height** inside the 50 cm design space.

Within the 150 cm horizontal allowance, the actuator base can be placed to maximize the **favorable moment arm** during the early portion of the lift. A geometry that provides strong leverage and avoids poor actuator angles is:

- Place the boom pivot at the left end of the ground plane:

  \\[
  A = (0, 0)
  \\]

- Place the actuator base somewhere along the ground line:

  \\[
  B = (0.60\\text{ to }0.80,\\ 0)\\ \\text{m}
  \\]

- Attach the actuator to the boom near its tip:

  \\[
  r_C = 0.48\\,\\text{m}
  \\]

- Apply the load at the boom tip:

  \\[
  r_D = L = 0.50\\,\\text{m}
  \\]

This creates a long effective **lever arm** for the actuator while also keeping the included angle between the actuator line-of-action and the boom **reasonably large** across the motion, which is crucial for torque.

---

## Mechanism Geometry

![Lifting mechanism geometry diagram]({{ "/assets/images/lifting-geometry.jpeg" | relative_url }})

*Figure 1 – Planar lifting mechanism showing boom pivot \\(A\\), actuator base \\(B\\), actuator attachment \\(C\\), and load point \\(D\\) within the 150 cm × 50 cm design envelope.*

---

## Calculations Supporting the Geometry

Let the boom make an angle \\( \alpha \\) measured from the horizontal. The lifted load \\( W \\) acts vertically downward at the tip \\( D \\).

### Moment from the Load

The moment about the boom pivot \\( A \\) due to the load is

$$
M_W = W\,\big(L \cos\alpha\big),
$$

because the perpendicular moment arm of a vertical force equals the **horizontal projection** of the tip position, \\( L\cos\alpha \\).

### Moment from the Actuator

The actuator produces a force \\( F_{\max} \\) along its axis at point \\( C \\).  
The moment about \\( A \\) provided by the actuator is

$$
M_F = F_{\max}\, r_C\, \sin\theta,
$$

where \\( \theta \\) is the angle between the boom radius to point \\( C \\) and the actuator line of action.

Imposing **static equilibrium** about point \\( A \\) in the limiting lift case gives

$$
F_{\max}\, r_C\, \sin\theta = W\,\big(L \cos\alpha\big),
$$

so the load capacity at a given configuration is

$$
\boxed{
W(\alpha)
=
\frac{F_{\max}\, r_C\, \sin\theta}{L \cos\alpha}
}
$$


This expression directly explains the chosen geometry:

- **Maximizing \\( r_C \\):**  
  Placing point \\( C \\) close to the boom tip makes \\( r_C \\) as large as possible without exceeding the bar length. With \\( r_C = 0.48\\,\\text{m} \\) and \\( L = 0.50\\,\\text{m} \\), the actuator torque potential is nearly maximized for this bar length.

- **Maintaining a strong \\( \\sin\\theta \\):**  
  The position of \\( B \\) is chosen so that the actuator never becomes nearly colinear with the boom in the low-to-mid lift range. This preserves a large \\( \\sin\\theta \\), which is critical because actuator torque scales **linearly** with \\( \\sin\\theta \\).

- **Height maximization:**  
  Choosing \\( L = 0.50\\,\\text{m} \\) ensures that as \\( \\alpha \\to 90^\\circ \\), the lifted height approaches the **design-space ceiling**.

---

## Conservative Numerical Illustration (Rigid-Body Idealization)

To show the implications of the selected actuator force with this geometry,  
consider a reasonably favorable early-lift configuration where

$$
\sin\theta \approx 0.9.
$$

Using:

$$
F_{\max} = 294\,\text{kN}, \qquad
r_C = 0.48\,\text{m}, \qquad
L = 0.50\,\text{m},
$$

and considering a near-horizontal boom (\\( \alpha \approx 0^\circ \\)), which is  
**worst-case for the load moment arm** (since \\( \cos\alpha \approx 1 \\)), we obtain

$$
W \approx 
\frac{294{,}000\,\text{N} \cdot 0.48\,\text{m} \cdot 0.9}{0.50\,\text{m}}
\approx 2.54 \times 10^5\,\text{N}.
$$

This corresponds to an idealized lifted mass of approximately

$$
\frac{W}{g}
\approx
\frac{2.54 \times 10^5\,\text{N}}{9.81\,\text{m/s}^2}
\approx 2.6 \times 10^4\,\text{kg}.
$$

This value is best interpreted as a **theoretical upper bound** under the assignment’s rigid-body assumptions. In real hardware:

- joint strength,  
- tipping and overall stability,  
- actuator mounting and buckling limits,  
- and bar bending and buckling

would dominate well before this ideal load is reached.

However, within the stated idealization, this calculation clearly demonstrates why:

- a **short boom** that fully uses the 50 cm height limit,
- with **near-tip actuator attachment** (large \\( r_C \\)),
- driven by a **high-force actuator**,

is the optimal design direction for maximizing lifted weight and achieved height within the given 150 cm × 50 cm planar envelope.

---

## Structural Analysis: Treating the Boom as a Real Beam

After validating the rigid-body concept, I then treated the boom as a **real elastic beam** instead of an ideal rigid link. In this second step, the bar is assumed to **bend under the combined transverse components** of the lifted weight and the actuator force. The goal is to quantify the **maximum deflection** under the most demanding loading configuration and then choose a **cross-section and material** that satisfy a strict deflection limit while remaining as mass-efficient as possible.

This step fundamentally changes the design logic: instead of only optimizing leverage and statics, the solution must now consider **elastic stiffness**, which becomes the new bottleneck once the actuator force is as large as  
\\( F_{\\max} = 294\\,\\text{kN} \\).

---

## Beam Model and Loading Assumptions

To carry out the analysis conservatively, I modeled the boom as an **Euler–Bernoulli cantilever** of length

\\[
L = 0.50\\,\\text{m},
\\]

effectively fixed at the pivot region. Although the mechanism joint at \\( A \\) is a pin in the ideal mechanism description, this assumption is reasonable for early-stage structural design because:

- the physical pivot bracket and surrounding structure would typically provide significant rotational restraint,  
- a cantilever model yields a **consistent, conservative baseline** for deflection calculations.

Additional assumptions:

- small deflections,  
- linear elastic behavior,  
- beam self-weight neglected (first pass),  
- two transverse point loads:  
  - tip load at \\( D \\),  
  - actuator load at \\( C \\), located at \\( a = r_C \\approx 0.48\\,\\text{m} \\).

---

## Transverse Loads Relative to the Boom

At boom angle \\( \alpha \\), the transverse component of the lifted weight is

$$
W_t = W \cos\alpha.
$$

The actuator transverse component is

$$
F_t = F_{\max} \sin\theta,
$$

where \\( \theta \\) is the included angle between the actuator line-of-action and the boom.

Using **superposition** for a cantilevered beam:

- a point load at the free end contributes a deflection  
  \\( \delta_W = W_t L^3 / (3EI) \\) at the tip,
- a point load at an interior point \\( a \\) contributes  
  \\( \delta_F = F_t a^2 (3L - a) / (6EI) \\) at the tip.

Thus the combined maximum deflection is

$$
\delta_{\max}
\approx
\frac{W_t L^3}{3EI}
+
\frac{F_t a^2 (3L - a)}{6EI}.
$$


This expression directly shows why the **near-tip actuator attachment** that was optimal for lifting capacity in Step 1 also **increases bending demand** in Step 2: placing the actuator force close to the end of the boom increases deflection unless the section stiffness \\( EI \\) is sufficiently large.

---

## Deflection Limit and Required Section Stiffness

The design requirement states that vertical deflection must be below **2% of beam length**.  
For \\( L = 0.50\,\text{m} \\):

$$
\delta_{\text{allow}} = 0.02L = 0.01\,\text{m}.
$$

Rearranging the deflection expression provides the required second moment of area:

$$
I_{\text{req}}
\ge
\frac{1}{E\,\delta_{\text{allow}}}
\left[
\frac{W_t L^3}{3}
+
\frac{F_t a^2 (3L - a)}{6}
\right].
$$

In words:

The boom’s cross-section must be selected primarily to resist the **combined bending** from  
1. the transverse component of the tip load, and  
2. the transverse actuator load near the tip,  

evaluated at the most demanding configuration.

This reinforces the earlier observation that the **1.5 m actuator stroke is not the limiting factor**—once actuator force is this high, **stiffness and mass-efficient section design** dominate.

---

## Cross-Section Choice for Mass-Efficient Stiffness

The objective is to maximize **specific stiffness**, meaning both:

- high material modulus \\( E/\\rho \\), and  
- high **geometric stiffness**, meaning material placed far from the neutral axis (large \\( I \\) for a given mass).

Under these criteria:

- a **thin-walled closed section** (circular or rectangular tube) is far superior to a solid bar,  
- composites offer extremely high stiffness-to-weight ratio,  
- but if metal is preferred, a thin-walled **aluminum or steel tube** can be sized to meet \\( I_{\\text{req}} \\) efficiently.

The final cross-section is chosen by iterating:

1. tube outer diameter,  
2. wall thickness,  
3. material selection,

until the computed \\( I \\) exceeds  
\\( I_{\\text{req}} \\) with **minimum mass per unit length**, followed by verifying the deflection expression in the worst-case lift configuration.

---

## Final Boom Design (Stiffness-Driven Section Sizing)

For the final boom design, I sized the cross-section **directly from the minimum stiffness requirement implied by the deflection constraint**, rather than picking a “reasonable-looking” tube first.  

From the Step 2 cantilever model with two transverse point loads —  
the transverse component of the lifted weight at the tip \\( D \\) and  
the transverse component of the actuator force at the attachment \\( C \\) —  
the required second moment of area must satisfy:

$$
I_{\text{req}}
\;\ge\;
\frac{1}{E\,\delta_{\text{allow}}}
\left[
\frac{W_t L^3}{3}
+
\frac{F_t a^2 (3L - a)}{6}
\right].
$$

Using the geometry already selected for maximum height,  
\\( L = 0.50\,\text{m} \\) and \\( a = r_C \approx 0.48\,\text{m} \\),  
and the 2% deflection limit \\( \delta_{\text{allow}} = 0.01\,\text{m} \\),  
I evaluated a demanding early-lift case consistent with the high-force actuator choice where  
\\( \alpha \approx 0^\circ \\) and \\( \sin\theta \approx 0.9 \\).

This gives:

$$
F_t \approx 294\,\text{kN} \times 0.9 = 264.6\,\text{kN},
$$

and from Step 1 equilibrium at low angle:

$$
W_t \approx W \approx 254\,\text{kN}.
$$

Substituting these values yields a stiffness demand on the order of:

$$
I_{\text{req}} \sim 3.0 \times 10^{-5}\,\text{m}^4,
$$

if a material near aluminum’s modulus is used.  

---

## Final Section Selection

To meet this requirement in the most mass-efficient and manufacturable way, I kept the same  
**“material far from the neutral axis”** strategy and selected a **large-diameter thin-walled tube**.

A practical final geometry that satisfies the stiffness inequality is:

- **Material:** 6061-T6 aluminum (\\( E \approx 69\,\text{GPa} \\))  
- **Outer diameter:** \\( D_o \approx 350\,\text{mm} \\)  
- **Wall thickness:** \\( t \approx 2\,\text{mm} \\)

This section provides:

$$
I \approx 3.31 \times 10^{-5}\,\text{m}^4,
$$

which is **greater than the required** \\( I_{\text{req}} \\) from the inequality above for the chosen worst-case loading interpretation.  
Thus the predicted tip deflection remains within the **< 2% limit**.

Despite the large diameter, the mass remains reasonable for a short boom:

- tube linear mass \\( \approx 5.9\,\text{kg/m} \\)  
- for \\( 0.50\,\text{m} \\), total mass \\( \approx 3.0\,\text{kg} \\)

---

## Final Beam Cross-Section Sketch

![Final boom cross-section placeholder]({{ "/assets/images/boom-cross-section.png" | relative_url }})

*Figure 2 — Final thin-walled aluminum tube sized to meet stiffness requirement with minimum mass.*

