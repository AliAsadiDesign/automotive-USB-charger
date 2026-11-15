# Automotive USB Charger — PCB Design Case Study

## Project summary

I designed an in-vehicle DC-DC converter PCB to provide a 5 V USB output from a vehicle electrical supply. The circuit uses an LM2576HVS-5V buck regulator as labelled in the supplied schematic and was designed in Altium Designer. The PCB was fabricated as a single-sided board and installed in a vehicle.

The designer reports that the unit remained in regular use for approximately 5–6 years or longer, charging a mobile phone, without observed malfunction or abnormal heating. This is field-use experience, not a substitute for instrumented qualification testing.

## Design requirements

| Item | Project information |
|---|---|
| Input source | Vehicle electrical system, nominal 12 V |
| Output | 5 V USB |
| Regulator | LM2576HVS-5V (as labelled in supplied schematic) |
| Switching diode | SS36 Schottky diode |
| Input capacitor | 100 µF |
| Output capacitor | 1000 µF |
| Inductor | 330 µH |
| Output interface | USB Type-A |
| PCB construction | Single-sided copper |
| Copper thickness | 35 µm (1 oz) |
| Minimum track width | 1.0 mm |
| EDA tool | Altium Designer |

## Design work

- Created the circuit schematic and PCB layout in Altium Designer.
- Placed the regulator, switching diode, inductor, capacitors, and USB connector.
- Used wide power tracks and a broad ground copper region.
- Produced a 3D PCB view to review component placement and mechanical arrangement.
- Fabricated and installed the prototype for real-world use.

## Prototype evidence

The repository includes:
- a 3D render of the PCB;
- a 2D PCB layout screenshot;
- the updated schematic screenshot supplied for this portfolio revision;
- the supplied native Altium project, schematic, and PCB documents.

## Practical lessons and redesign opportunities

The original prototype did not include dedicated input protection for automotive electrical transients or reverse battery connection. A revised design should evaluate:
- input fuse and reverse-polarity protection;
- an appropriately selected automotive TVS and input filter;
- input capacitor voltage rating and transient stress;
- switching-current loop geometry and return-current paths;
- thermal performance at defined output-current levels;
- USB output voltage and ripple under load.

## Test data and limitations

No measured maximum output current, efficiency, ripple, load regulation, or thermal-rise data were supplied for this project. These values are intentionally not claimed.

The supplied Altium project references an `SS36.PcbLib` library file that was not included in the upload. The project may need its library dependency restored before it can be rebuilt cleanly.

## Suggested next revision

The next revision will focus on automotive input protection, verified component selection, documented current/thermal testing, and a complete manufacturing output set (Gerber, NC drill, fabrication notes, and DRC report).
