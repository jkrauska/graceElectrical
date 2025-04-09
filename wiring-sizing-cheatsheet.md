# Marine Wiring Sizing Cheatsheet

This cheatsheet provides a reference for selecting appropriate wire sizes for 12V DC marine electrical systems. Proper wire sizing is critical for safety, efficiency, and reliability in marine applications.

## Wire Size Reference Table

| AWG Size | Cross-sectional Area (mm²) | Maximum Current at 12V (Amps) | Typical Applications |
|----------|----------------------------|-------------------------------|----------------------|
| 4/0 (0000) | 107.2 | 360 | Main battery cables for very high current applications |
| 3/0 (000) | 85.0 | 310 | Main battery cables, inverter connections |
| 2/0 (00) | 67.4 | 265 | Battery to bus bar, large inverters |
| 1/0 (0) | 53.5 | 220 | Battery connections, alternator output |
| 1 | 42.4 | 170 | Inverter input, windlass |
| 2 | 33.6 | 145 | Alternator output, large inverters |
| 4 | 21.2 | 95 | Charging systems, bow thrusters |
| 6 | 13.3 | 75 | Battery chargers, medium loads |
| 8 | 8.4 | 55 | Larger appliances, pumps |
| 10 | 5.3 | 40 | Refrigeration, water pressure pumps |
| 12 | 3.3 | 25 | General lighting circuits, small pumps |
| 14 | 2.1 | 15 | Lighting, electronics |
| 16 | 1.3 | 10 | Electronics, small lights |

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

## Practical Tips

1. **Always size up**: When in doubt, choose a larger wire gauge than you think you need
2. **Consider future expansion**: Size wiring for potential future load increases
3. **Use marine-grade wire**: Standard automotive or residential wire is not suitable for marine environments
4. **Color coding**: Follow standard marine color codes (red for positive, black or yellow for negative)
5. **Tinned copper**: Use tinned copper wire for corrosion resistance in marine environments

## Example Calculation

For a 12V water pump drawing 8 amps with a 15-foot wire run:

1. Base wire size from table: 14 AWG (good for 15 amps)
2. Adjustment for 15-foot length: Go up 1 gauge size to 12 AWG
3. Result: Use 12 AWG wire for this application

This cheatsheet provides general guidelines. Always consult manufacturer specifications and marine electrical standards for specific applications.
