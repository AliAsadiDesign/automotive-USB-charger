# Automotive USB Charger — 12 V to 5 V DC-DC Converter

A practical PCB design project for an in-vehicle USB phone charger, designed in Altium Designer, fabricated as a single-sided PCB, and installed in a vehicle.

## Project snapshot

- **Function:** Convert a vehicle electrical supply to a regulated 5 V USB output
- **Regulator:** LM2576HVS-5V (as labelled in the supplied schematic)
- **PCB:** Single-sided copper, 35 µm (1 oz)
- **Minimum routed track width:** 1.0 mm
- **Output connector:** USB Type-A
- **Design tool:** Altium Designer
- **Field use:** The designer reports approximately 5–6 years or more of regular in-vehicle use without observed malfunction or abnormal heating.

## Repository contents

- `images/` — supplied 3D PCB render, 2D PCB layout, and updated schematic screenshot
- `source_altium/` — original Altium project, schematic, and PCB documents supplied for this portfolio case
- `docs/` — project case study and engineering review / validation plan

## Design overview

The circuit is a non-isolated step-down (buck) converter intended to power a USB phone-charging port from a vehicle electrical system. The supplied schematic shows:
- an LM2576HVS-5V regulator;
- an SS36 Schottky diode in the switching stage;
- a 100 µF input capacitor;
- a 1000 µF output capacitor;
- a 330 µH inductor;
- a USB Type-A output connector;
- a red power indicator LED with a 1 kΩ series resistor.

The PCB screenshots show a broad ground copper region and power routing with a stated minimum track width of 1.0 mm. Copper thickness was specified by the designer as 35 µm.

## Engineering notes and known limitations

This is an honest record of a working prototype, not a claim of automotive qualification.

- The original design did **not** include dedicated automotive input protection for reverse battery connection or transient/load-dump events.
- Output current, efficiency, ripple, and component temperatures were not measured or recorded.
- The project file references an `SS36.PcbLib` library document that was not among the supplied files. Check library dependencies and footprint availability before attempting a clean rebuild in Altium.
- No Gerber, drill, fabrication drawing, assembly drawing, or formal DRC report is included in this initial portfolio package.

## Validation status

**Demonstrated:** The designer reports that the fabricated board was installed in a vehicle and used regularly for phone charging for approximately 5–6 years or longer, with no observed operating issues or excessive heating.

**Not yet demonstrated by recorded test data:** maximum continuous output current, output-voltage regulation under load, ripple/noise, efficiency, thermal rise, input transient immunity, reverse-polarity protection, and formal design-rule compliance.

See `docs/ENGINEERING_REVIEW_AND_TEST_PLAN.md` for the proposed next validation steps.

## Important

This repository documents a prototype design and its known history. It must not be represented as automotive-qualified, safety-certified, or tested to an automotive transient standard.
