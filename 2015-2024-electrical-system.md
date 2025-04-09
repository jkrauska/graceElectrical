# Grace's 2015-2024 Electrical System

This document details the electrical system configuration used on Grace from 2015 to 2024, prior to the 2025 lithium battery upgrade.

## System Overview

The 2015-2024 electrical system utilized traditional AGM (Absorbed Glass Mat) batteries in a dual-battery configuration with basic charging and distribution components.

```mermaid
%%{init: {
  'theme': 'base',
  'themeVariables': {
    'primaryColor': '#ffffff',
    'primaryTextColor': '#000000',
    'primaryBorderColor': '#cccccc',
    'lineColor': '#000000',
    'secondaryColor': '#ffffff',
    'tertiaryColor': '#ffffff'
  }
}}%%
graph TD
  %% Define color constants
  %% powerSourceColor: #d4f1f9
  %% protectionColor: #ffe6cc
  %% distributionColor: #f8cecc
  %% conversionColor: #d5e8d4
  %% loadColor: #e1d5e7
  %% monitorColor: #f5f5f5
  %% noteColor: #fffde7
  
  %% Define nodes with descriptive identifiers and detailed labels
  house_battery["House Battery<br>AGM Type 4D"]
  starter_battery["Starter Battery<br>AGM Type 4D"]
  battery_switch["1/2/Both Switch<br>Battery Selector"]
  alternator["Engine Starter/<br>Alternator<br>Stock Hitachi 129772-77200 55A"]
  shore_power["Shore Power<br>AC Input"]
  charger["Xantrax 20A Charger<br>Battery Charger"]
  dc_panel["DC Panel<br>Circuit Distribution"]
  
  %% Style nodes using direct color values
  style house_battery fill:#d4f1f9,stroke:#333
  style starter_battery fill:#d4f1f9,stroke:#333
  style battery_switch fill:#ffe6cc,stroke:#333
  style alternator fill:#d4f1f9,stroke:#333
  style shore_power fill:#d4f1f9,stroke:#333
  style charger fill:#d5e8d4,stroke:#333
  style dc_panel fill:#f8cecc,stroke:#333

  %% Battery connections
  alternator -->|"Charging"| starter_battery
  shore_power -->|"AC Power"| charger
  charger -->|"Charging"| battery_switch
  battery_switch -->|"Position 1"| house_battery
  battery_switch -->|"Position 2"| starter_battery
  battery_switch -->|"Position Both"| dc_panel
  
  %% Add explanatory notes
  note_house_battery["House battery powers<br>onboard systems"]
  note_starter_battery["Starter battery<br>for engine ignition"]
  note_battery_switch["Switch selects which<br>battery is in use<br>or combines both"]
  note_charger["Charges batteries<br>when connected<br>to shore power"]
  
  style note_house_battery fill:#fffde7,stroke:#d6d6d6
  style note_starter_battery fill:#fffde7,stroke:#d6d6d6
  style note_battery_switch fill:#fffde7,stroke:#d6d6d6
  style note_charger fill:#fffde7,stroke:#d6d6d6
  
  house_battery --- note_house_battery
  starter_battery --- note_starter_battery
  battery_switch --- note_battery_switch
  charger --- note_charger

  %% Title with background
  title["Grace's 2015-2024 Electrical System<br>AGM Battery Configuration"]
  style title fill:#f0f0f0,stroke:#333,color:#000000,font-size:18px,font-weight:bold
  title --- house_battery
```

## System Components

### Power Sources
- **House Battery**: West Marine Group 4D Dual Purpose Marine AGM Battery
  - Capacity: 198Ah
  - Usable capacity: ~99Ah (50% depth of discharge)
  - Cold Cranking Amps: 1110 CCA
  - Marine Cranking Amps: 1420 MCA
  - Reserve Minutes: 380 min
  - Weight: ~120 lbs
  - Dimensions: 21" x 9" x 10"
  - Cost (April 2025): $890

- **Starter Battery**: West Marine Group 4D Dual Purpose Marine AGM Battery
  - Capacity: 198Ah
  - Cold Cranking Amps: 1110 CCA
  - Marine Cranking Amps: 1420 MCA
  - Reserve Minutes: 380 min
  - Weight: ~120 lbs
  - Dimensions: 21" x 9" x 10"
  - Cost (April 2025): $890

- **Alternator**: Stock Hitachi 129772-77200
  - Output: 55A maximum
  - Voltage: 14.4V (typical charging voltage)

- **Shore Power**: AC power connection when docked
  - Standard 30A marine shore power connection

### Battery Management
- **Battery Switch**: 1/2/Both Switch
  - Position 1: House battery only
  - Position 2: Starter battery only
  - Position Both: Batteries connected in parallel
  - Off: All power disconnected

### Charging System
- **Xantrax 20A Charger**
  - Input: 120V AC shore power
  - Output: 20A maximum charging current
  - Basic charging profile for AGM batteries

### Distribution
- **DC Panel**
  - Multiple circuit breakers for different onboard systems
  - Basic power distribution without monitoring

## System Limitations

### Power Capacity Limitations
- AGM batteries limited to 50% depth of discharge for longevity
- Effective usable capacity of ~100Ah from the house battery
- Limited runtime for high-draw devices

### Charging Limitations
- Basic charger with limited charging profile options
- No smart charging capabilities
- No remote monitoring of battery state

### Usage Limitations
- No built-in AC power when away from shore power
- Manual battery management required
- No detailed monitoring of battery health or consumption
- Batteries required replacement every 3-5 years

### Weight Considerations
- Two AGM Type 4D batteries weighed approximately 240 lbs combined
- Significant weight impact on vessel performance

## Maintenance Requirements
- Regular voltage checks
- Terminal cleaning to prevent corrosion
- Careful monitoring of discharge levels to prevent damage

## Conclusion
The 2015-2024 electrical system provided basic functionality but had significant limitations in terms of usable capacity, monitoring capabilities, and power availability when away from shore power. These limitations led to the decision to upgrade to a lithium-based system in 2025.
