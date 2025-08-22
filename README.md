# Tank-to-Tank OpenFOAM Simulation

This repository contains a *CFD case in OpenFOAM* that simulates fluid transfer between two connected tanks through a short pipe using the interFoam solver (VOF multiphase model for water–air interaction).

![Preview](docs/preview.jpg)

---

## 🔹 Overview
- *Solver*: interFoam
- *Physics*: Two-phase incompressible flow (water + air), gravity-driven
- *Geometry*:
  - Left Tank → initially filled with water
  - Right Tank → initially filled with air
  - Pipe → connects the two tanks
- *Dimensions*: 2D (extruded 0.01 m in z-direction)
- *Purpose*: Demonstrates free-surface flow, mixing, and turbulence between coupled tanks.

---

## 🔹 Case Setup
- *Mesh*: Generated with blockMesh (3 regions: left tank, pipe, right tank)
- *Initialization*: setFields used to fill left tank with water and right tank with air
- *Boundary Conditions*:
  - Tank walls & pipe → wall
  - Open top → patch (atmospheric pressure)
- *Turbulence*: Default laminar (can be switched to RANS like kOmegaSST)

---

## 🔹 Running the Case
```bash
# Clean old results
./Allclean

# Generate mesh, set fields, and run simulation
./Allrun

# Visualize in ParaView
paraFoam
