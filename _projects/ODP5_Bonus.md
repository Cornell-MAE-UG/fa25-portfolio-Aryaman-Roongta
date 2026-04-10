---
layout: project
title: Passive SLF Pre-harvest Trap for NYS Industrial Vineyards
description: Functional Prototype — Team Buzzkill / Cornell CALS Extension / E&J Gallo Winery / National Grape
technologies: [Jekyll, Markdown, CAD, Laser Cutting, 3D Printing, Prototyping, Testing]
image: assets/images/ThumbnailODP5.png
---

<div style="border:1px solid #ddd; border-radius:10px; padding:1rem 1.25rem; margin:1rem 0 1.5rem 0; background:#fafafa;">
  <h2 style="margin-top:0;">Project Navigation</h2>
  <p style="margin-bottom:0.5rem;">Use the links below to jump directly to each portfolio milestone.</p>
  <ul style="margin-bottom:0;">
    <li><a href="#client-pitch">Client Pitch</a></li>
    <li><a href="#functional-prototype">Functional Prototype</a></li>
  </ul>
</div>

This page documents the evolution of our passive pre-harvest spotted lanternfly (SLF) trap, from the original problem framing to the first functional prototype.

---

## <a id="client-pitch"></a>Client Pitch

For this project, we are developing a **passive, pre-harvest trap** to help **New York State industrial vineyards** keep harvested grapes clear of **spotted lanternflies (SLFs)** while minimizing additional labor.

### Problem Statement

New York State farmers are trying to keep harvested grapes clear of spotted lanternflies in industrial vineyards, but they lack the human labor to do so efficiently. Since a large amount of grapes are machine-harvested as **juice/must**, it is difficult to remove SLFs post-harvest without **yield loss** or **contamination**. Our approach is therefore to **lure and capture SLFs pre-harvest** with a modular trap design.

### Proposed Direction

Our concept combines:

- a **box enclosure** to contain captured SLFs,
- a **chemical diffuser** using methyl salicylate,
- a **funnel entrance** to guide insects inward,
- an **adjustable iris opening** to control entry,
- and a **removable side panel** for maintenance and replacement of internal components.

### Intended Impact

This design aims to:

- reduce **labor burden** on vineyard operators,
- protect **grape quality** by limiting SLF contamination,
- support **pre-harvest pest management**,
- and create a **serviceable modular trap** that can be improved through future iterations.

---

## <a id="functional-prototype"></a>Functional Prototype

The purpose of this prototype was to test the **mechanical feasibility** of the trap architecture before full field testing. Rather than proving final trapping performance, this iteration focused on whether the main subsystems could be fabricated, assembled, and operated as intended.

---

## Prototype Overview

The functional prototype consists of the following main subsystems:

- **Box housing** made from laser-cut wooden plates
- **Removable side panel** for user access
- **3D-printed funnel**
- **3D-printed iris mechanism**
- **Chemical diffuser holder and connector**

---

## Design Documentation

### Box Housing

The main box was fabricated by laser cutting the **top, base, left, right, and back plates** from sheets of wood.

<img src='{{ "/assets/images/LaserBox1.png" | relative_url }}' alt="LaserBox1" style="width:100%; max-width:700px; height:auto; display:block; margin:1rem auto;" />
<img src='{{ "/assets/images/LaserBox2.png" | relative_url }}' alt="LaserBox2" style="width:100%; max-width:700px; height:auto; display:block; margin:1rem auto;" />

### Removable Side Panel

The removable side panel was made by laser cutting the plate and two mounts from sheets of wood.

<img src='{{ "/assets/images/RemovablePanel.png" | relative_url }}' alt="RemovablePanel" style="width:100%; max-width:700px; height:auto; display:block; margin:1rem auto;" />

### Funnel

The funnel was **3D printed** and mounted above the top plate.

<img src='{{ "/assets/images/Funnel.png" | relative_url }}' alt="Funnel" style="width:100%; max-width:700px; height:auto; display:block; margin:1rem auto;" />

### Iris

The iris mechanism was made by **3D printing all parts**.

<img src='{{ "/assets/images/Iris.png" | relative_url }}' alt="Iris" style="width:100%; max-width:700px; height:auto; display:block; margin:1rem auto;" />

### Chemical Diffuser

The chemical diffuser used a separately **3D-printed diffuser holder and connector**, along with **cotton balls** as the absorbent material for methyl salicylate.

<img src='{{ "/assets/images/Diffuser.png" | relative_url }}' alt="Diffuser" style="width:100%; max-width:700px; height:auto; display:block; margin:1rem auto;" />

---

## Assembly

The overall trap was assembled as follows:

1. Press fit the five plates of the box, orienting the left, right, and base plates so that the smooth edges face the edge with two shorter slots and one longer slot of the top plate.
2. Glue one M4 screw to the hole on each of the mounts, orient the mounts so that the screws aim outward from the box, and glue the extrusions of the mounts to the shorter slots on the top plate. Then hang the removable side panel on the screws.
3. Screw the funnel from above the top plate with M4 screws and bolts, letting the opening of the funnel face the removable side panel.
4. Screw the diffuser connector from below the top plate with M3 screws and bolts, aligning the circular ring of the connector to the bottom of the funnel.
5. Place one cotton ball in the diffuser holder and slide the holder onto the connector.
6. Place the iris blades on the bottom plate, orient the blades so that the iris is at maximum opening, then put on the top plate and adjust the opening to the required size.

---

## What Was Tested

This prototype focused on testing three main features:

1. **Iris mechanism**
2. **Integration of diffuser attachment**
3. **Removable side panel**

---

## Test 1: Iris Mechanism

The iris consists of the adjustable opening on the top of the box. We tested this feature because it allows the chemical to diffuse into the environment while also providing an opening large enough to attract SLFs into the box.

### Success Criteria

The iris should:

- open to a diameter greater than the maximum SLF size,
- operate smoothly,
- and avoid mechanical failure during repeated use.

### Outcome

The iris mechanism partially succeeded. The iris opened to **80 mm in diameter**, while the size of an adult SLF is approximately **12.7–25.4 mm**, so the opening size requirement was satisfied.

However, some components of the iris broke during assembly, and we were not able to attach the iris to the box ceiling in this prototype. This means the concept worked in principle, but the durability and integration need improvement in the next iteration.

Chemical diffusion effectiveness was not tested in this prototype and will be evaluated in future experiments.

---

## Test 2: Integration of Diffuser Attachment

The diffuser attachment holds the methyl salicylate chemical. This test was intended to determine whether the diffuser could be integrated into the trap assembly without interfering with the operation of the iris.

### Success Criteria

The diffuser should:

- attach securely,
- allow the diffuser holder to slide in and out,
- and avoid interfering with the iris mechanism.

### Outcome

The diffuser holder was able to **slide in and out successfully**, showing that the serviceability concept worked.

However, the connector to the iris interfered with assembly inside the box due to **spatial conflict**. Because of this, the part of the connector that causes interference should be removed or redesigned in the next prototype so that the diffuser and iris can coexist properly.

---

## Test 3: Removable Side Panel

This panel opens and closes the trap box and allows the user to access the inside when the sticky trap or chemical needs to be replaced.

### Success Criteria

The removable side panel should:

- fully enclose the trap without gaps,
- be easy to remove and reattach,
- and provide practical maintenance access.

### Outcome

The side panel could be **opened and closed successfully**, so the access concept worked.

However, there was a **gap at the bottom of the box** where chemical could diffuse out and where SLFs could potentially escape. To solve this, we plan to add **two additional M4 screws on the bottom corners** in the next iteration to create a more secure enclosure.

---

## What the Prototype Showed

This functional prototype showed that:

- the box housing concept is viable,
- the iris can open large enough for SLFs,
- the diffuser can function as a removable module,
- and the side panel can provide maintenance access.

At the same time, the prototype revealed important design issues:

- the iris needs improved assembly robustness,
- the diffuser connector interferes with iris integration,
- and the removable panel needs better sealing.

Even though the prototype was not fully successful in every area, it was valuable because it exposed integration problems that were not obvious from concept design alone.

---

## Success Criteria for the Full Project

Our project aims to design a trap to lure and kill adult SLF using methyl salicylate as a chemical attractant combined with sticky surfaces in outdoor environments.

The full project success criteria are:

- The trap should capture **at least 100 adult SLF per box** before requiring servicing.
- The trap should remain **structurally intact and functional after at least 14 consecutive days** of outdoor exposure, including rain and wind.
- A user should be able to replace both the **chemical diffuser and sticky trap components in under 2 minutes**.
- The methyl salicylate diffuser should provide a **steady, detectable release for at least 14 days**, with a consistent daily mass loss of at least **0.1 g/day**.

---

## End-of-Semester Demonstration

For the end-of-semester exhibition, we will demonstrate the **serviceability criterion** with a live demonstration of removing and replacing the chemical diffuser and sticky trap components using the removable side panel mechanism in under two minutes.

---

## Next Iteration

The next prototype should focus on:

- redesigning the iris for better durability and assembly,
- removing geometric interference between the diffuser connector and iris,
- improving sealing at the removable side panel,
- and testing chemical diffusion effectiveness experimentally.

---

## Supporting Documentation

[View full design documentation PDF]({{ "/assets/ODP5PDF.pdf" | relative_url }})