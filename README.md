# Differential Amplifier using TSMC 180nm CMOS – LTspice

This project simulates a fully differential amplifier using the TSMC 180nm CMOS process in LTspice. It includes schematic, simulation setup, and waveform results for transient and AC analysis. The design meets key analog performance targets including gain, bandwidth, and slew rate.

## Folder Structure

- `tsmc_180nm/` – Contains the TSMC 180nm model library file (`tsmc_180nm.lib`).
- `schematic/` – LTspice schematic file (`DifferentialAmplifier.asc`).
- `netlist/` – LTspice-exported netlist (`.net`).
- `simulation/` – Raw output files generated after simulation (`.raw`, `.op.raw`, `.log`).
- `results/` – Exported waveform plots and schematic screenshots (`.jpg`, `.png`).
- `docs/` – (To be added) PDF documentation with design specifications and design process.

## Design Specifications

- **Technology**: TSMC 180nm
- **Supply Voltage**: 1.8 V
- **Load**: 10 pF capacitive load
- **Target Gain**: 100 (differential mode)
- **Input Common-Mode Range**: 0.8 V – 1.6 V
- **Slew Rate**: ≥ 5 V/μs
- **Unity-Gain Bandwidth (UGB)**: ≥ 5 MHz

## Transistor Sizing and Biasing

- **Tail node current**: 150 μA
- **W/L ratios**:
  - M1, M2: 45 μm / 0.18 μm
  - M3, M4: 9 μm / 0.18 μm
  - M5 (Tail NMOS): 6 μm / 0.18 μm
  - Load transistors (M6, M7): 12 μm / 0.18 μm

## Schematic
![Differential Amplifier Schematic](results/Circuit_Schematic.png)


## How to Run

1. Copy the model and symbol files to LTspice directories:
   - Place `cmosn.asy` and `cmosp.asy` into:
     ```
     Documents/LTspice/lib/sym
     ```
   - Place `tsmc_180nm.lib` into:
     ```
     Documents/LTspice/lib
     ```

2. Open the schematic:
    ```
    schematic/DifferentialAmplifier.asc
    ```

3. Update the `.lib` directive path in the schematic to match your system's location of `tsmc_180nm.lib`.

4. Uncomment the appropriate simulation directive (e.g., `.tran`, `.ac`) based on the desired analysis.

5. Run the simulation in LTspice and observe outputs in the waveform viewer.

## Schematic

![Differential Amplifier Schematic](results/Circuit_Schematic.png)

## Simulation Results

### AC Analysis

![AC Response](results/ACAnalysis.png)

### Transient Simulation

![Transient Output](results/TransientSimulation.png)


