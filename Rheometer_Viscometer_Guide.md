# Rheometer & Viscometer: Protocol & User Guide

A practical guide to measuring viscosity and rheological properties using **rotational rheometers** and common **viscometers** (rotational/Brookfield-type, capillary, and falling-ball).

> This is a general, vendor-neutral guide. Always follow your instrument manufacturer's manual and your lab's SOPs and safety rules. Menu names and parameters vary between instruments and software (e.g., Anton Paar RheoCompass, TA Instruments TRIOS, Malvern rSpace, Brookfield/AMETEK Rheocalc).

---

## Table of Contents

1. [Rheometer vs. Viscometer](#rheometer-vs-viscometer)
2. [Key Concepts](#key-concepts)
3. [Part A: Rotational Rheometer Protocol](#part-a-rotational-rheometer-protocol)
4. [Part B: Rotational Viscometer (Brookfield-Type) Protocol](#part-b-rotational-viscometer-brookfield-type-protocol)
5. [Part C: Capillary Viscometer Protocol](#part-c-capillary-viscometer-protocol)
6. [Part D: Falling-Ball Viscometer Protocol](#part-d-falling-ball-viscometer-protocol)
7. [Choosing a Geometry](#choosing-a-geometry)
8. [Data Analysis & Models](#data-analysis--models)
9. [Troubleshooting](#troubleshooting)
10. [Cleaning & Maintenance](#cleaning--maintenance)
11. [Standards & References](#standards--references)

---

## Rheometer vs. Viscometer

| Feature | Viscometer | Rheometer |
|---|---|---|
| Measures | Viscosity (usually at one or a few shear rates) | Viscosity *and* viscoelastic properties (G′, G″, yield stress, creep, thixotropy) |
| Fluids | Mainly Newtonian, or simple QC of non-Newtonian fluids | Newtonian, non-Newtonian, gels, pastes, melts, soft solids |
| Test modes | Rotation or flow | Rotation, oscillation, creep/recovery, stress relaxation |
| Typical use | QC, routine checks | R&D, formulation, structure characterization |
| Cost/complexity | Lower | Higher |

---

## Key Concepts

- **Shear stress (τ, Pa)**: force per unit area applied to the fluid.
- **Shear rate (γ̇, s⁻¹)**: velocity gradient across the gap.
- **Dynamic viscosity (η, Pa·s)**: η = τ / γ̇. 1 mPa·s = 1 cP. Water ≈ 1.0 mPa·s at 20 °C.
- **Kinematic viscosity (ν, mm²/s = cSt)**: ν = η / ρ (measured by capillary viscometers).
- **Newtonian fluid**: viscosity is independent of shear rate (water, oils, glycerol).
- **Shear-thinning (pseudoplastic)**: viscosity decreases with shear rate (polymer solutions, paints, blood).
- **Shear-thickening (dilatant)**: viscosity increases with shear rate (concentrated starch suspensions).
- **Yield stress (τ₀)**: the minimum stress needed before the material flows (toothpaste, ketchup).
- **Thixotropy**: time-dependent decrease in viscosity under shear, with recovery at rest.
- **Viscoelasticity**: combined solid-like and liquid-like behavior.
  - **G′ (storage modulus)**: elastic (solid-like) part.
  - **G″ (loss modulus)**: viscous (liquid-like) part.
  - **tan δ = G″/G′**: below 1 the material is gel-like; above 1 it is liquid-like.
- **LVR (Linear Viscoelastic Region)**: the strain/stress range where the moduli are independent of amplitude. Oscillation tests must be run inside the LVR.

---

## Part A: Rotational Rheometer Protocol

### A1. Preparation
1. **Check the environment**: place the instrument on a stable, vibration-free bench.
2. **Turn on the air supply** first (for air-bearing rheometers). Typical supply is clean, dry, oil-free air at the pressure the manufacturer specifies. **Never rotate the spindle/bearing without air.**
3. **Turn on the temperature control** unit (Peltier, circulator, or oven) and allow it to equilibrate.
4. **Switch on the rheometer** and launch the software. Allow warm-up (typically 15–30 min).
5. **Initialize** the instrument (the software usually prompts for this).

### A2. Install the Geometry
1. Select the geometry (see [Choosing a Geometry](#choosing-a-geometry)).
2. Attach the measuring system to the motor shaft (coupling or magnetic quick-connect). Avoid touching the measuring surfaces.
3. Confirm the software recognizes the geometry, or select it manually.

### A3. Calibration & Zero Gap
1. **Inertia calibration**: perform with no sample (needed when the geometry is changed).
2. **Zero gap**: let the instrument lower the upper geometry to touch the lower plate and set the zero position. Do this **at the measurement temperature**, because thermal expansion changes the gap.
3. Periodically verify accuracy with a **certified viscosity standard** (Newtonian silicone oil). Results should be within the stated tolerance (often ±1–2%).

### A4. Load the Sample
1. Raise the geometry to the loading position.
2. Place the sample in the center of the lower plate, or fill the cup to the mark.
   - Use a spatula or a positive-displacement pipette for viscous samples.
   - Avoid air bubbles. Degas or centrifuge if needed.
   - Estimate the required volume from the geometry (e.g., 25 mm plate at 1 mm gap ≈ 0.5 mL).
3. Lower to the **trim gap** (typically measurement gap + 2–5%).
4. **Trim** excess sample flush with the geometry edge using a trimming tool.
5. Lower to the **measurement gap**.
6. For volatile samples, use a **solvent trap** or apply low-viscosity oil around the edge to prevent drying.
7. **Equilibrate**: wait for thermal and structural equilibrium (typically 2–5 min; longer for structured samples).

### A5. Choose and Run Tests

#### A5.1 Flow Curve (Rotation: Viscosity vs. Shear Rate)
- **Purpose**: viscosity profile, Newtonian vs. shear-thinning behavior.
- **Typical settings**: shear rate 0.1 → 1000 s⁻¹ (logarithmic ramp), 5–10 points per decade, steady-state criterion or a fixed time per point.
- **Output**: η vs. γ̇ and τ vs. γ̇.

#### A5.2 Amplitude Sweep (Oscillation)
- **Purpose**: find the **LVR**, yield point, and flow point. **Always run this first** for an unknown sample before frequency sweeps.
- **Typical settings**: frequency 1 Hz (6.28 rad/s) or 10 rad/s, strain 0.01 → 100% (or a stress ramp).
- **Output**: G′, G″ vs. strain. The LVR ends where G′ drops more than ~5% from its plateau value.

#### A5.3 Frequency Sweep (Oscillation)
- **Purpose**: structure and time-dependent behavior (gel vs. liquid, crossover point).
- **Typical settings**: strain fixed **within the LVR**, frequency 100 → 0.1 rad/s.
- **Output**: G′, G″, η*, tan δ vs. ω.

#### A5.4 Temperature Sweep / Ramp
- **Purpose**: gelation/melting temperature, Tg, curing.
- **Typical settings**: fixed strain (within the LVR) and frequency, ramp 1–5 °C/min.
- **Output**: G′, G″ vs. T. The G′/G″ crossover often indicates gel/sol transition.

#### A5.5 Time Sweep
- **Purpose**: curing, gelation kinetics, stability, structure recovery.
- **Settings**: fixed strain, frequency, and temperature, recorded over time.

#### A5.6 Creep & Recovery
- **Purpose**: viscoelastic deformation under constant stress; zero-shear viscosity.
- **Settings**: apply constant stress (in the LVR) for a set time, release, then record recovery.

#### A5.7 Thixotropy (3-Interval Thixotropy Test, 3ITT)
- **Interval 1**: low shear (rest), e.g., 0.1 s⁻¹ for 60 s.
- **Interval 2**: high shear (structure breakdown), e.g., 100 s⁻¹ for 30 s.
- **Interval 3**: low shear again (recovery), e.g., 0.1 s⁻¹ for 120 s or more.
- **Output**: % recovery of viscosity (or G′) over time.

#### A5.8 Yield Stress
- Stress ramp (rotation), or the flow point from an amplitude sweep, or fitting a model (Herschel–Bulkley, Bingham) to the flow curve.

### A6. After the Measurement
1. Save and export data (CSV/Excel).
2. Raise the geometry. Remove and discard the sample per waste rules.
3. Clean the geometry and plate (see [Cleaning & Maintenance](#cleaning--maintenance)).
4. Return the temperature to standby, and lock the bearing if required.
5. Shut down the software, then the rheometer. **Turn off the air supply last.**
6. Record usage in the instrument logbook.

---

## Part B: Rotational Viscometer (Brookfield-Type) Protocol

### B1. Setup
1. Place the viscometer on its stand and **level it** using the bubble level.
2. Switch it on and perform **autozero** with no spindle attached (digital models).
3. Bring the sample to the test temperature (use a water bath or a thermosel). Viscosity is highly temperature-dependent, roughly 2–10% per °C for many liquids.

### B2. Select Spindle & Speed
1. Choose the spindle (e.g., LV-1 to LV-4, or RV-1 to RV-7) and speed (RPM) according to the expected viscosity, using the manufacturer's range table.
2. **Target torque reading: 10–100%** (ideally above 25%) for accurate results.
   - Torque too high: use a smaller spindle or a lower speed.
   - Torque too low: use a larger spindle or a higher speed.

### B3. Measurement
1. Use a standard container (e.g., a 600 mL low-form beaker for standard spindles), or the small-sample adapter / UL adapter.
2. Attach the spindle (left-hand thread on most models). **Lift the coupling nut slightly while threading** to protect the pivot.
3. Immerse the spindle at an angle to avoid trapping air, then center it. Immerse **to the groove mark on the shaft**.
4. Attach the guard leg if required by the method.
5. Start the motor at the selected speed.
6. Wait for a **stable reading** (typically 30–60 s, or a fixed time defined in your method).
7. Record viscosity (cP / mPa·s), % torque, spindle, speed, temperature, and time.
8. For non-Newtonian fluids, record readings at several speeds (low → high → low) to characterize shear-thinning and thixotropy.

### B4. Finish
1. Stop the motor, remove the spindle, and clean it immediately.
2. Store the spindles in their case. Never leave the instrument with the spindle attached during transport.

> **Note:** Brookfield results with standard spindles in a beaker are *apparent* viscosities. The shear rate is not uniquely defined, so always report the spindle, speed, container, and temperature.

---

## Part C: Capillary Viscometer Protocol

(Ostwald, Ubbelohde, or Cannon-Fenske glass viscometers; measures **kinematic viscosity**.)

1. **Select the viscometer size** so that the flow time is **200 s or more** (per ASTM D445), to minimize kinetic-energy errors.
2. **Clean and dry** the viscometer (solvent rinse, then dry with filtered air). Filter the sample if it contains particles.
3. **Charge** the exact sample volume specified for the viscometer type.
4. Mount it **vertically** in a constant-temperature bath (control to ±0.02 °C for precise work). Equilibrate for 10–30 min.
5. Apply suction or pressure to raise the liquid above the upper timing mark.
6. Release and **time** the meniscus as it flows from the upper mark to the lower mark.
7. Repeat at least 2–3 times. Readings should agree within the method's tolerance (≈0.2–0.35%).
8. **Calculate**:
   - Kinematic viscosity: **ν = C × t** (C = viscometer constant in mm²/s², t = flow time in s)
   - Dynamic viscosity: **η = ν × ρ**
9. Clean the viscometer immediately after use.

---

## Part D: Falling-Ball Viscometer Protocol

(e.g., Höppler type; used for transparent Newtonian fluids.)

1. Fill the tube with sample, avoiding bubbles, and equilibrate at the test temperature.
2. Insert the selected ball (choose by viscosity range).
3. Close the tube, tilt it to the starting position, and allow the ball to roll/fall.
4. Time the ball between the two marks. Repeat 3 or more times, and invert the tube between runs.
5. **Calculate**: **η = K × (ρ_ball − ρ_fluid) × t**, where K is the ball constant from the calibration certificate.

---

## Choosing a Geometry

| Geometry | Best For | Pros | Cons |
|---|---|---|---|
| **Cone & Plate (CP)** | Homogeneous fluids, polymer solutions, small samples | Uniform shear rate; small volume | Not suitable for particles larger than ~1/10 of the truncation gap; sensitive to gap setting |
| **Parallel Plate (PP)** | Gels, pastes, melts, samples with particles; temperature sweeps | Adjustable gap; easy loading | Shear rate varies with radius |
| **Concentric Cylinder (CC / Couette / Bob & Cup)** | Low-viscosity fluids, suspensions, volatile samples | High sensitivity; less evaporation | Large volume; harder cleaning |
| **Double Gap** | Very low viscosity (water-like) | Very high sensitivity | Large volume; difficult cleaning |
| **Vane** | Yield-stress materials, pastes, slurries | Minimal wall slip and sample disturbance | Mainly for yield/flow, not precise viscosity |
| **Serrated/Sandblasted plates** | Samples that slip (emulsions, pastes, foods) | Reduces wall slip | Harder to clean |

**Gap rule of thumb (parallel plates):** the gap should be at least **10× the largest particle size**. A typical gap is 0.5–1.0 mm.

---

## Data Analysis & Models

| Model | Equation | Applies To |
|---|---|---|
| Newtonian | τ = η·γ̇ | Simple liquids |
| Power Law (Ostwald–de Waele) | τ = K·γ̇ⁿ | Shear-thinning (n < 1) or thickening (n > 1) |
| Bingham | τ = τ₀ + η_p·γ̇ | Yield-stress fluids with linear flow |
| Herschel–Bulkley | τ = τ₀ + K·γ̇ⁿ | Yield-stress, shear-thinning fluids |
| Casson | √τ = √τ₀ + √(η_∞·γ̇) | Chocolate, blood, inks |
| Cross / Carreau | η = η_∞ + (η₀ − η_∞) / [1 + (λγ̇)ᵐ] | Polymer solutions with zero-shear and infinite-shear plateaus |
| Arrhenius (temperature) | η = A·exp(Eₐ / RT) | Temperature dependence of viscosity |

### Reporting Checklist
- Instrument model and software version
- Geometry (type, diameter, cone angle, gap)
- Temperature and equilibration time
- Test type and parameters (strain, frequency, shear-rate range, points per decade)
- Sample preparation and loading history (pre-shear, rest time)
- Number of replicates, mean ± SD
- Model fitted and goodness of fit (R²)

---

## Troubleshooting

| Problem | Likely Cause | Solution |
|---|---|---|
| Viscosity drops sharply at high shear rate | Edge fracture, sample ejection, or secondary flow | Lower the max shear rate, use a cup geometry, reduce the gap |
| Noisy data at low shear | Torque below the instrument limit | Use a larger geometry; increase the measuring time per point |
| Apparent viscosity increases over time | Evaporation / skin formation | Use a solvent trap or oil seal; shorten the test |
| Results lower than expected for pastes | Wall slip | Use serrated plates or a vane geometry |
| Poor reproducibility | Inconsistent loading or structure history | Standardize loading, pre-shear, and rest time |
| G′ and G″ change in a frequency sweep at fixed strain | Strain outside the LVR | Repeat the amplitude sweep; pick a lower strain |
| Values off at high frequency | Instrument inertia effects | Check the raw phase angle; recalibrate inertia; limit the frequency range |
| Brookfield reading unstable or above 100% | Wrong spindle/speed | Change the spindle/speed to reach 10–100% torque |
| Capillary flow time too short | Viscometer too wide for the sample | Use a smaller-bore viscometer (flow time ≥ 200 s) |
| Readings drift with temperature | Not equilibrated | Wait longer; verify the bath/Peltier with a calibrated probe |

---

## Cleaning & Maintenance

1. Clean geometries **immediately** after use with a suitable solvent (water, ethanol, isopropanol, acetone, or detergent, depending on the sample). Use soft lint-free wipes; **never scratch measuring surfaces**.
2. Do not immerse electronic parts or bearings in solvent.
3. Store geometries in their protective cases.
4. Verify calibration regularly with certified standard oils, and keep calibration records.
5. For air-bearing rheometers: keep the air supply dry and oil-free; check filters regularly.
6. Schedule annual manufacturer service and calibration.

---

## Safety Notes

- Wear PPE (lab coat, gloves, safety glasses). Use heat-resistant gloves for high-temperature tests.
- Keep fingers clear of the geometry during gap movements. Use the emergency stop if needed.
- Use fume hoods or extraction when testing volatile or hazardous samples.
- Allow hot plates and ovens to cool before cleaning.

---

## Standards & References

- **ASTM D445**: Kinematic viscosity of transparent and opaque liquids (capillary viscometers)
- **ASTM D2196**: Rheological properties of non-Newtonian materials by rotational viscometer
- **ASTM D4287**: High-shear viscosity using a cone/plate viscometer
- **ISO 3219**: Determination of viscosity using a rotational viscometer with defined shear rate
- **ISO 3104**: Petroleum products: kinematic viscosity
- **ISO 6721-10**: Plastics: dynamic mechanical properties (parallel-plate oscillatory rheometer)
- **DIN 53019**: Viscometry with rotational viscometers
- Mezger, T. G. *The Rheology Handbook*. Vincentz Network.
- Macosko, C. W. *Rheology: Principles, Measurements, and Applications*. Wiley-VCH.
- Barnes, H. A., Hutton, J. F., & Walters, K. *An Introduction to Rheology*. Elsevier.
- Manufacturer manuals: Anton Paar, TA Instruments, Malvern Panalytical, Brookfield (AMETEK), Thermo Fisher HAAKE.

---

*This guide is for educational purposes. Always follow the instrument manufacturer's instructions and your institution's SOPs and safety requirements.*
