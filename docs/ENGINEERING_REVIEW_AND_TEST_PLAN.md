# Engineering Review and Validation Plan

## Known facts from the supplied project and designer

- Intended use: vehicle-powered 5 V USB charger.
- PCB is reported as single-sided.
- Copper thickness: 35 µm (1 oz).
- Minimum track width: 1.0 mm.
- The updated schematic shows an LM2576HVS-5V regulator, a 100 µF input capacitor, a 1000 µF output capacitor, a 330 µH inductor, and an SS36 Schottky diode.
- Dedicated automotive input protection was not included in the original design.
- The board reportedly operated in a vehicle for approximately 5–6 years or longer without observed malfunction or abnormal heating.

## Do not claim without measurements

- 3 A continuous output capability;
- a specific efficiency percentage;
- a specific ripple/noise value;
- automotive transient or load-dump immunity;
- reverse-battery protection;
- automotive qualification or certification.

A 1.0 mm track on 35 µm copper is not, by itself, enough information to establish a safe current rating. Track length, actual current, allowable temperature rise, copper geometry, airflow, and surrounding copper all matter.

## Recommended validation sequence

1. **Document verification**
   - Verify the regulator part marking and confirm the schematic, BOM, PCB footprint, and project libraries are consistent.
   - Confirm the SS36 diode's exact manufacturer and datasheet.

2. **Electrical inspection**
   - Run Altium electrical-rule and design-rule checks.
   - Check polarity and pin mapping for the USB connector.
   - Verify the inductor value, saturation current, DCR, and package.
   - Verify capacitor voltage ratings, ripple-current ratings, and polarity.

3. **Bench testing**
   - Use a current-limited DC supply.
   - Start at a light load and increase load in controlled steps.
   - Record input voltage/current and output voltage/current.
   - Measure output ripple with a suitable oscilloscope setup.
   - Monitor regulator, diode, inductor, and PCB temperatures.
   - Stop if any component exceeds its rated limits.

4. **Automotive input protection redesign**
   - Evaluate a fuse, reverse-polarity protection, TVS, and input filtering.
   - Select protection components using the vehicle's expected electrical environment and the regulator's verified absolute maximum ratings.
   - Do not assume a TVS alone guarantees compliance with automotive transient requirements.

5. **Manufacturing release**
   - Generate Gerber files and NC drill files from the final, verified PCB revision.
   - Include fabrication notes, board outline, copper weight, and stack-up.
   - Save a DRC report and a PDF schematic.
   - Review the generated manufacturing files in a Gerber viewer before sending them to a board house.

## Current evidence status

| Evidence | Status |
|---|---|
| Altium project / schematic / PCB source | Supplied |
| PCB 3D render | Supplied |
| PCB layout screenshot | Supplied |
| Updated schematic screenshot | Supplied |
| Fabricated prototype field use | Designer-reported |
| Measured output-current test | Not supplied |
| Efficiency / ripple / thermal test report | Not supplied |
| Gerber / NC drill package | Not supplied |
| Formal DRC report | Not supplied |
