# Modular Multinuclear RF Front Ends

Hardware design files for interchangeable, nucleus-specific RF front-end drawers for **¹H, ²³Na, and ³¹P MRI and spectroscopy at 3T**.

The project uses frequency-specific transmit/receive (T/R) switches, quadrature hybrids, and commercial low-noise preamplifiers in removable drawers. A shared housing allows the front end to be reconfigured for a different nucleus by replacing the drawer. Individual shielding enclosures surround the RF components.

## Research context

This project accompanies *An Open-Source, Modular Approach to Multinuclear RF Front Ends* (ISMRM abstract #07003), by Atakan Ozfidan, Jacob Degitz, Aaliyah K Fisher, Alexander Davis, Travis Carrell, and Mary P McDougall, Texas A&M University.

The approach addresses the need for narrowband front-end components when working with multiple nuclei. Each drawer combines a T/R switch, a quadrature hybrid, and a WanTcom preamplifier: WMM123P for ¹H, WMM32P for ²³Na, and WMM50P for ³¹P. The abstract describes 3D-printed PLA enclosures lined with copper tape and a sliding common housing.

The abstract reports independent benchtop characterization of the T/R switches and quadrature hybrids. Validation with RF coils and imaging or spectroscopy acquisitions remains necessary to establish integrated performance. The design files here should be understood in that research context.

## Repository contents

| Folder | Contents |
| --- | --- |
| [`1_H/`](1_H/) | Proton front-end drawer and assembly, T/R switch circuit and shield, quadrature combiner circuit and shield, and preamplifier shield. |
| [`23_Na/`](23_Na/) | Sodium front-end drawer and assembly, T/R switch circuit and shield, quadrature combiner circuit and shield, and preamplifier shield. |
| [`31_P/`](31_P/) | Phosphorus front-end drawer and assembly, T/R switch circuit and shield, quadrature combiner circuit and shield, and preamplifier shield. |
| [`Common Housing/`](Common%20Housing/) | Shared housing bodies, dowels, assembly, and manufacturing exports. |
| [`Preamplifier_Mounting_Board/`](Preamplifier_Mounting_Board/) | KiCad project for the preamplifier mounting board. |

Within each nucleus folder, `Front_End` contains mechanical drawer designs, `TR_Switch` contains the switch circuit and enclosure, `Quad_Combiner` contains the quadrature hybrid circuit and enclosure, and `Preamp_Shield` contains the preamplifier enclosure. Folder prefixes and spelling vary slightly between nuclei; the original names are preserved.

### File formats

- **KiCad:** `.kicad_pro` projects, `.kicad_sch` schematics, and `.kicad_pcb` board layouts.
- **SolidWorks:** `.SLDPRT` parts and `.SLDASM` assemblies.
- **Manufacturing exports:** `.STL` meshes and selected `.3mf` files for fabrication workflows.

The current tree contains circuit and mechanical design files. Standalone bills of materials, characterization datasets, fabrication instructions, and acquisition software are not currently included. The source abstract is kept locally and excluded from version control.

## Working with the designs

1. Choose the nucleus-specific folder for your application.
2. Open a circuit's `.kicad_pro` file in KiCad to inspect its schematic and PCB layout. Inspected board files identify KiCad 9.0 as their generator; use a compatible version.
3. Open the SolidWorks parts and assemblies to inspect or modify the mechanical design. Preserve the folder structure so assembly references can resolve.
4. Use the supplied STL or 3MF exports in a compatible slicer when preparing parts for printing. Confirm dimensions, fit, material, shielding, and assembly requirements for your hardware before fabrication.

The preamplifiers are commercial components; the repository includes their enclosure designs and a separate mounting-board project.

## Design background

The abstract identifies the T/R switch design as adapted from B. Thapa et al., *Design and Development of a General-Purpose Transmit/Receive (T/R) Switch for 3T MRI, Compatible for a Linear, Quadrature and Double-Tuned RF Coil* (2016), and the quadrature hybrid design as adapted from *NMR Probeheads for Biophysical and Biomedical Experiments*.

## Version-control housekeeping

The `.gitignore` excludes the local abstract, Windows and macOS metadata, editor temporary files, SolidWorks temporary lock files, and KiCad local settings, caches, autosaves, and backup directories. Editable design sources and STL/3MF exports are retained.
