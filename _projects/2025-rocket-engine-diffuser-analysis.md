---
layout: project
title: Rocket Engine Diffuser Analysis
description: By Kate Ainley-Zoll & Aryaman Roongta
technologies: [None]
image: assets/images/RocketEngineDiffuserThumbnail.jpg
---

For this project we chose to analyze a **rocket-engine diffuser**. The diffuser is the downstream geometry that receives the high-speed exhaust from a converging–diverging rocket nozzle and slows it down in a controlled way so that kinetic energy is converted into static pressure or used for mixing and flow conditioning.

---

## How a Jet Diffuser Works

A **jet diffuser** is widely used in HVAC systems, aircraft engine test cells, and propulsion test facilities wherever a high-speed jet of air must be slowed down smoothly and efficiently.

- As the flow enters the diffuser, the **cross-sectional area gradually increases**.
- Because mass flow is (approximately) conserved, the **flow velocity decreases** as area increases.
- The reduction in velocity converts **kinetic energy into static pressure** – this is called **pressure recovery**.
- To keep this process efficient, the flow must remain **attached** to the diffuser walls.
- If the **expansion (divergence) angle** is too large, the boundary layer separates, producing turbulence, energy loss, and a sharp drop in pressure recovery.

The diffuser’s performance is usually characterized by a **pressure-recovery coefficient**, which measures how effectively the diffuser converts velocity head into static pressure. Its value is very sensitive to both geometry and operating conditions:

- Increasing the expansion angle makes the diffuser **shorter and more compact**, but greatly **increases the risk of flow separation**, reducing pressure recovery.
- Using a smaller expansion angle keeps the flow attached and **improves efficiency**, but requires a **longer diffuser**.
- Higher inlet velocities provide more kinetic energy to recover, but also make the flow more prone to separation.
- Surface roughness and very large area ratios increase losses and can further reduce efficiency.

Overall, a jet diffuser performs best when its design promotes **smooth, gradual deceleration** with attached, steady flow.

---

## Qualitative Description in a Rocket-Engine Context

In a rocket-engine application, the diffuser is placed **downstream of the nozzle** and is designed either to:

- decelerate and interrogate the **supersonic exhaust plume** inside a test stand, or  
- enable **mixing and pressure recovery** in air-augmented or altitude-compensating propulsion systems.

Key qualitative features:

- The exhaust leaves the converging–diverging nozzle at **high Mach number** and enters a larger-area diffuser.
- Inside the diffuser, the flow experiences **controlled deceleration** through a combination of:
  - gradual **area expansion**,
  - **oblique or normal shocks** (for supersonic regimes),
  - and **mixing** with entrained ambient air.
- The goal is to convert **dynamic pressure into higher static pressure** or to produce a flow state that can be safely exhausted, measured, or further processed.

Performance depends strongly on:

- the **shock structure** (location and strength of shocks),
- **boundary-layer growth** along the walls,
- whether the flow remains **quasi-attached** through the expansion.

Flow separation or unsteady shock motion leads to large losses, high entropy generation, and poor diffuser performance.

---

## Photos and Schematics of the Diffuser

<style>
/* Local override just for this page’s diffuser figures */
.diffuser-figure-img {
  width: 100%;
  max-width: 100%;
  height: auto !important;
  max-height: none !important;
  object-fit: contain !important;
  display: block;
  margin: 0 auto 0.5rem;
}
</style>

![Cross Section Rocket Engine Schematic]({{ "assets/images/RocketDiffuserSchematic1.png" | relative_url }}){: .diffuser-figure-img }

*Figure 1 – Cross Section Rocket Engine Schematic.*

![Rocket Engine Anatomy]({{ "assets/images/RocketDiffuserSchematic2.png" | relative_url }}){: .diffuser-figure-img }

*Figure 2 – Rocket Engine Anatomy.*

![SCRAMJET vs RAMJET]({{ "assets/images/RocketDiffuserSchematic3.png" | relative_url }}){: .diffuser-figure-img }

*Figure 3 – SCRAMJET vs RAMJET.*

---

## System Diagram: Heat, Work, and Mass Flow

![Control-volume diagram for diffuser]({{ "assets/images/RocketDiffuserSystemDiagram.png" | relative_url }}){: .inline-image-l}

*Figure 4 – Control-volume representation of the diffuser showing mass flow, heat transfer, and work interactions.*

---

## Mass and Energy Balance

We treat the diffuser and the immediate rocket-exhaust region as a **steady-flow control volume**.

### Mass balance

The total mass flow rate is conserved between inlet (1) and outlet (2):

$$
\dot{m}_1 = \dot{m}_2
$$

At the outlet, the flow may consist of **nozzle exhaust plus entrained air**:

$$
\dot{m}_2 = \dot{m}_\text{exhaust} + \dot{m}_\text{entrained}
$$

### Steady-flow energy equation

The general steady-flow energy balance for the control volume is

$$
\dot{m}\left(h_1 + \frac{V_1^2}{2} + g z_1\right)
+ \dot{Q} - \dot{W}_s
=
\dot{m}\left(h_2 + \frac{V_2^2}{2} + g z_2\right)
+ \dot{E}_\text{loss}
$$

For the diffuser we typically assume:

- shaft work is negligible, \\( \dot{W}_s \approx 0 \\)
- elevation changes are small, $ z_1 \approx z_2 $
- heat transfer is small compared to the flow energy

Under these assumptions, the balance simplifies to

$$
\dot{m}\left(h_1 + \frac{V_1^2}{2}\right)
\;\approx\;
\dot{m}\left(h_2 + \frac{V_2^2}{2}\right)
+ \dot{E}_\text{loss}
$$

### Bernoulli-style form with losses

For a single-phase flow we can rewrite the same physics in a Bernoulli-style relation that includes a head-loss term \\(h_L\\):

$$
p_1 + \frac{1}{2}\rho_1 V_1^2 + \rho_1 g z_1
=
p_2 + \frac{1}{2}\rho_2 V_2^2 + \rho_2 g z_2 + \rho\,h_L
$$

Here \\(h_L\\) represents losses from friction, mixing, shocks, and separation in the diffuser.

### Thrust relation and impact of the diffuser

The rocket thrust at the exit plane (before the diffuser) can be approximated by

$$
F = \dot{m}\,V_e + \left(p_e - p_\infty\right) A_e ,
$$

where \\(V_e\\) and \\(p_e\\) are the exhaust velocity and static pressure at the nozzle exit, \\(p_\infty\\) is ambient (test-cell) pressure, and \\(A_e\\) is the nozzle exit area.

A diffuser that **raises the downstream static pressure** (and therefore modifies \\(p_e\\) or the effective back pressure) will:

- change the pressure term \\(\left(p_e - p_\infty\right)A_e\\),
- modify the exit velocity \\(V_e\\),
- and therefore **change the net thrust and the engine/test-cell back-pressure condition**.

If the diffuser effectively raises static pressure downstream without causing severe losses, it increases the pressure contribution in the thrust relation while still allowing useful deceleration and conditioning of the exhaust.

---

## Entropy Balance and Irreversibility

For the same control volume, the **entropy balance** is

$$
\dot{m}\left(s_2 - s_1\right)
=
\dot{S}_\text{gen}
+
\frac{\dot{Q}}{T_\text{wall, avg}},
$$

<p>
where \( \dot{S}_{\text{gen}} \ge 0 \) is the rate of entropy generation
and \( T_{\text{wall, avg}} \) is an average wall temperature where heat
transfer occurs.
</p>

If the heat transfer is small, the entropy change is dominated by irreversibilities:

$$
s_2 - s_1 \;\approx\; s_\text{gen} \ge 0 .
$$

Entropy generation in the diffuser comes from

- **viscous dissipation** in the boundary layer,
- **shock waves** in supersonic regions,
- **heating**, **mixing**, and **flow separation**.

Each of these irreversibilities **reduces total pressure** and the **effective recoverable work** that can be obtained from the flow, which is why minimizing separation and shock losses is crucial for a high-performance diffuser.

---

## Effect of Design and Operating Conditions on Performance

The performance of a jet-engine diffuser depends strongly on both **geometry** and **operating conditions**:

- **Divergence angle**
  - Increasing the divergence angle or surface roughness promotes **boundary-layer separation**, dramatically reducing pressure recovery and increasing total-pressure losses.
  - Using a smaller angle keeps the flow attached and **improves pressure recovery**, but makes the diffuser **longer and heavier**.

- **Inlet Mach number**
  - Higher inlet Mach numbers can enhance pressure recovery **if the internal flow remains subsonic**.
  - If the flow inside the diffuser becomes **supersonic**, shock waves form, causing large stagnation-pressure losses and possible flow unsteadiness.

- **Surface condition and area ratio**
  - Rough walls and very high area ratios increase viscous losses and make separation more likely.
  - Smooth surfaces and carefully chosen area ratios help maintain attached flow.

- **Ambient conditions / altitude**
  - At high altitudes, lower air density leads to larger boundary-layer thicknesses and a greater tendency to separate, reducing diffuser effectiveness.

In summary, diffuser performance is **optimal** when the internal flow is **attached, shock-free, and gradually decelerated**. Even small changes in geometry or operating conditions can noticeably impact **pressure recovery**, **losses**, and overall effectiveness of the rocket-engine test system.
