# Marine Wiring Sizing Cheatsheet

This cheatsheet provides a reference for selecting appropriate wire sizes for 12V DC marine electrical systems. Proper wire sizing is critical for safety, efficiency, and reliability in marine applications.

## Wire Size Reference Table

| AWG Size | Ancor Marine Wire Cross-sectional Area (mm²) | Standard Cross-sectional Area (mm²) | Maximum Current at 12V (Amps) | Typical Applications |
|----------|----------------------------------------------|-------------------------------------|-------------------------------|----------------------|
| 4/0 (0000) | 120 | 107.2 | 360 | Main battery cables for very high current applications |
| 3/0 (000) | 95 | 85.0 | 310 | Main battery cables, inverter connections |
| 2/0 (00) | 70 | 67.4 | 265 | Battery to bus bar, large inverters |
| 1/0 (0) | 55 | 53.5 | 220 | Battery connections, alternator output |
| 1 | 40 | 42.4 | 170 | Inverter input, windlass |
| 2 | 35 | 33.6 | 145 | Alternator output, large inverters |
| 4 | 25 | 21.2 | 95 | Charging systems, bow thrusters |
| 6 | 16 | 13.3 | 75 | Battery chargers, medium loads |
| 8 | 10 | 8.4 | 55 | Larger appliances, pumps |
| 10 | 6 | 5.3 | 40 | Refrigeration, water pressure pumps |
| 12 | 4 | 3.3 | 25 | General lighting circuits, small pumps |
| 14 | 2.5 | 2.1 | 15 | Lighting, electronics |
| 16 | 1.5 | 1.3 | 10 | Electronics, small lights |

## Voltage Drop Considerations

Wire sizing in marine applications must account for voltage drop, which is the decrease in voltage that occurs along a wire due to resistance. For 12V systems:

- **Critical Circuits** (navigation equipment, electronics): Maximum 3% voltage drop
- **Non-Critical Circuits** (lighting, general use): Maximum 10% voltage drop

### Voltage Drop Formula

Voltage drop can be calculated using:

```
Voltage Drop (V) = Current (A) × Wire Resistance (Ω)
```

Where wire resistance depends on wire length, gauge, and material.

## Length Considerations

The maximum current ratings in the table above are for short runs (under 10 feet). For longer wire runs, you must increase the wire size to minimize voltage drop:

| Wire Length | Adjustment |
|-------------|------------|
| 0-10 feet | Use table value |
| 10-15 feet | Go up 1 gauge size |
| 15-20 feet | Go up 2 gauge sizes |
| 20-25 feet | Go up 3 gauge sizes |
| 25-30 feet | Go up 4 gauge sizes |

## Temperature Considerations

Wire current ratings should be derated for high-temperature environments:

| Temperature | Derating Factor |
|-------------|-----------------|
| Below 86°F (30°C) | 1.0 (no derating) |
| 86-104°F (30-40°C) | 0.9 |
| 104-122°F (40-50°C) | 0.8 |
| Above 122°F (50°C) | 0.7 |

## ABYC Standards

The American Boat and Yacht Council (ABYC) provides standards for marine electrical systems:

- All current-carrying conductors must be properly sized
- Wire insulation must be rated for the environment (marine-grade)
- Proper overcurrent protection must be provided
- Wire must be supported at least every 18 inches
- Connections must be secure and protected from moisture

## Ancor Marine-Grade Wire

Ancor Marine Grade Primary Wire is specifically designed for marine environments and offers several advantages:

- **Tinned copper conductors** for superior corrosion resistance
- **PVC insulation** that resists oil, gas, and moisture
- **Color-coded** for easy circuit identification
- **UL 1426 boat cable** certified for marine applications
- **105°C temperature rating** for engine room applications

Ancor wire is available from marine supply stores and online retailers like [Amazon](https://www.amazon.com/Ancor-Marine-Grade-Primary-Battery/dp/B000NHZY8I).

## Victron Energy Inverter Wiring Requirements

The Victron Energy MultiPlus 12/1200/50-16 120V inverter/charger has specific wiring requirements to ensure safe and efficient operation:

### DC Wiring (Battery to Inverter)

| Model | Recommended Minimum Wire Size | Ancor Marine Wire Size |
|-------|-------------------------------|------------------------|
| MultiPlus 12/1200/50-16 | 35mm² | AWG 2 (35mm²) |

### Key Points for Inverter Installation:

1. **Short Cable Runs**: Keep DC cables as short as possible (ideally under 5 feet)
2. **Equal Length**: DC positive and negative cables should be of equal length
3. **Fusing**: Install appropriate DC fuse protection as close to the battery as possible
4. **Terminal Connections**: Ensure clean, tight connections at all terminals
5. **Temperature Considerations**: Derate wire size for high-temperature environments

## Practical Tips

1. **Always size up**: When in doubt, choose a larger wire gauge than you think you need
2. **Consider future expansion**: Size wiring for potential future load increases
3. **Use marine-grade wire**: Standard automotive or residential wire is not suitable for marine environments
4. **Color coding**: Follow standard marine color codes (red for positive, black or yellow for negative)
5. **Tinned copper**: Use tinned copper wire for corrosion resistance in marine environments
6. **Follow manufacturer specs**: Always adhere to the manufacturer's minimum wire size requirements

## Example Calculation

For a 12V water pump drawing 8 amps with a 15-foot wire run:

1. Base wire size from table: 14 AWG (good for 15 amps)
2. Adjustment for 15-foot length: Go up 1 gauge size to 12 AWG
3. Result: Use 12 AWG wire for this application

This cheatsheet provides general guidelines. Always consult manufacturer specifications and marine electrical standards for specific applications.
