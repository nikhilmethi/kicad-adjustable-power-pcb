# KiCad + SPICE: Adjustable Power Interface PCB

End-to-end circuit design, simulation, and PCB implementation of a voltage divider system, extended into a configurable analog output interface.

## Overview
This project implements a simple voltage regulation concept (9 V → ~5 V) and evolves it into a physically realizable PCB capable of producing an adjustable output voltage from 0–9 V.

The focus was on translating a basic circuit into a robust, manufacturable hardware design.

## Design Objectives
- Step down a 9 V input to a usable lower voltage  
- Maintain controlled current draw  
- Enable adjustable output for flexibility in downstream use  
- Transition from schematic design to a clean PCB layout  

## Circuit Design
- Designed a resistive voltage divider with clearly defined +9V, GND, and output (Vin) nets  
- Structured the schematic for clarity and correct power definition  
- Ensured electrical correctness through rule checking and validation  

## System Evolution
- Initial design: fixed voltage divider (~5 V output)  
- Final design: replaced fixed resistor with a **3-terminal potentiometer**, enabling a continuous output range from ~0 V to 9 V  

This shift prioritized flexibility and practical usability over a single operating point.

## PCB Implementation
- Single-sided, through-hole PCB (50 mm × 50 mm)  
- Ground plane for improved stability and routing simplicity  
- External interfaces:
  - 9 V input via connector
  - Vin/GND output for integration with other systems  
- Mechanical considerations:
  - Standard mounting holes for integration into larger systems  

## Key Takeaways
- Bridging circuit theory to hardware requires layout, grounding, and interfacing considerations beyond schematic design  
- Simple circuits can be made significantly more useful through small design changes (e.g., fixed → adjustable output)  
- PCB constraints (size, routing, connectors) directly influence design decisions  

## Files
- KiCad schematic and PCB layout  
- SPICE simulation files (used for validation)
