# Grace Electrical System Documentation

This repository documents the electrical system of Grace, a Catalina 320 sailboat, focusing on the 2025 upgrade from a pair of AGM batteries to modern lithium battery technology.

## Project Motivation

The motivation for updating Grace's electrical system was to leverage newer lithium battery technology and add monitoring systems to track battery health. The 2025 Electrical upgrade had two primary goals:

1. **Move to Lithium Battery Technology**: Transition to lithium batteries for their longer life and higher capacity compared to traditional AGM batteries.
2. **Add Inverter Capability**: Incorporate an inverter to provide low wattage AC service when off the dock.

These upgrades significantly improve the vessel's electrical capabilities, providing more usable power, better monitoring, and increased reliability for extended cruising.

## System Overview

### Previous System (2024)

The previous electrical setup consisted of:
- Two AGM Type 4D batteries (200Ah each) for house power
- A 1/2/Both switch for battery selection
- A Xantrax 20a charger for shore power charging

This system provided basic functionality but had limitations in terms of usable capacity, monitoring capabilities, and power availability when away from shore power.

### Upgraded System (2025)

The upgraded electrical system features:
- LiTime 12V 230Ah LiFePO4 Deep Cycle Battery for house power
- Victron Energy MultiPlus 12/1200/50-16 120V Inverter/Charger
- Victron Orion XS Smart 12/12 50A DC-DC Charger
- DC SmartShunt monitors for battery health tracking
- Improved protection and distribution components

This system provides longer battery life, increased usable capacity, better monitoring, and AC power availability when away from shore power.

## Documentation Structure

This repository contains detailed documentation on various aspects of Grace's electrical system:

### [2024 Electrical System](./2024-electrical-system.md)
Detailed documentation of the previous electrical setup with AGM batteries, including:
- System diagram
- Component specifications
- Limitations and challenges

### [2025 Electrical Upgrade](./2025-electrical-upgrade.md)
Comprehensive documentation of the upgraded electrical system with lithium batteries, including:
- Detailed system diagram
- Component specifications and connections
- Power flow in different scenarios
- Benefits of the upgrade

### [Battery Selection](./battery-selection.md)
In-depth analysis of the battery selection process, including:
- Comparison between AGM and LiFePO4 technologies
- Selection criteria and decision process
- Cost analysis and long-term benefits
- Implementation considerations

### [Wiring Sizing Cheatsheet](./wiring-sizing-cheatsheet.md)
Reference guide for marine electrical wiring, including:
- Wire gauge sizes and current ratings
- Cross-sectional area measurements
- Voltage drop considerations
- Length and temperature adjustments
- ABYC standards and practical tips

## Key Improvements

The 2025 electrical system upgrade delivered several significant improvements:

1. **Increased Usable Capacity**: The 230Ah lithium battery provides ~200Ah of usable power (90% DoD), effectively doubling the ~100Ah usable capacity of the previous 200Ah AGM battery (50% DoD).

2. **Extended Battery Life**: LiFePO4 batteries typically last 2000+ cycles compared to 300-500 cycles for AGM batteries, significantly reducing replacement frequency.

3. **Weight Reduction**: The lithium battery weighs approximately 60 lbs, compared to 240 lbs for the two AGM batteries it replaced, improving vessel performance.

4. **Enhanced Monitoring**: SmartShunt monitors provide real-time tracking of battery state and health, enabling better power management.

5. **AC Power Availability**: The 1200W inverter provides AC power when away from shore power, improving comfort and functionality when cruising.

## System Comparison

| Feature | 2024 System (AGM) | 2025 System (LiFePO4) |
|---------|------------------|------------------------|
| House Battery | Two West Marine Group 4D (198Ah each) | LiTime 12V 230Ah LiFePO4 |
| Usable Capacity | ~99Ah (50% DoD) | ~200Ah (90% DoD) |
| Total Weight | ~240 lbs | ~60 lbs |
| Battery Cost | $1,780 (2 x $890) | $430 |
| Charging | Xantrax 20A Charger | Victron MultiPlus 12/1200/50-16 |
| Inverter | None | Victron MultiPlus 1200VA Pure Sine Wave ($480) |
| Monitoring | Basic voltage monitoring | Victron SmartShunt IP65 300A ($72 each) |
| AC Power | Shore power only | Inverter (1200W) + Shore power |
| Expected Life | 3-5 years | 8-10+ years |
| Battery Management | Manual (1/2/Both switch) | Automated with protection circuits |
| Standards | Marine rated | Meets ABYC E-13 Standard |

## Conclusion

The 2025 electrical system upgrade represents a significant improvement in Grace's power capabilities. By adopting lithium battery technology, adding comprehensive monitoring, and incorporating inverter functionality, the vessel now enjoys longer battery life, increased usable capacity, better power management, and AC power availability when away from shore power.

These improvements enhance both the functionality and comfort of the vessel during extended cruising, while also providing long-term cost benefits through reduced maintenance and fewer battery replacements.
