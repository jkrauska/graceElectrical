# Grace's 2025 Electrical System Upgrade

This document details the upgraded electrical system implemented on Grace in 2025, featuring lithium battery technology and enhanced monitoring capabilities.

## System Overview

The 2025 electrical system upgrade replaced the traditional AGM batteries with modern LiFePO4 (Lithium Iron Phosphate) technology, added comprehensive monitoring, and incorporated an inverter for AC power when away from shore power.

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
  %% Define color constants (for documentation, not directly used)
  %% powerSourceColor: #d4f1f9
  %% protectionColor: #ffe6cc
  %% distributionColor: #f8cecc
  %% conversionColor: #d5e8d4
  %% loadColor: #e1d5e7
  %% monitorColor: #f5f5f5
  %% noteColor: #fffde7
  %% positiveLineColor: #ff0000
  %% negativeLineColor: #0066cc

  %% Define nodes with descriptive identifiers and detailed labels
  house_battery["House Battery<br>LiTime 12V 230Ah LiFePO4"]
  main_fuse["Class T Fuse 200A<br>Overcurrent Protection"]
  disconnect_switch["Main Disconnect Switch<br>Emergency Cutoff"]
  positive_bus["Positive Bus Bar<br>Power Distribution"]
  inverter_charger["Inverter/Charger<br>Victron Energy MultiPlus<br>12/1200/50-16 120V"]
  windlass["Windlass<br>Anchor System"]
  dc_panel["DC Panel<br>Circuit Distribution"]
  dc_dc_charger["DC-DC Charger<br>Victron Orion XS Smart<br>12/12 50A (700W)"]
  negative_bus["Negative Bus Bar<br>Ground Return"]
  starter_battery["Starter Battery<br>12V AGM 1000 CCA"]
  alternator["Engine Starter/Alternator<br>Hitachi 129772-77200 55A"]
  house_shunt["DC SmartShunt<br>Victron SmartShunt IP65 300A"]
  starter_shunt["DC SmartShunt<br>Victron SmartShunt IP65 300A"]
  
  %% Style nodes using direct color values
  style house_battery fill:#d4f1f9,stroke:#333
  style main_fuse fill:#ffe6cc,stroke:#333
  style disconnect_switch fill:#ffe6cc,stroke:#333
  style positive_bus fill:#f8cecc,stroke:#333
  style inverter_charger fill:#d5e8d4,stroke:#333
  style windlass fill:#e1d5e7,stroke:#333
  style dc_panel fill:#fff2cc,stroke:#333
  style dc_dc_charger fill:#d5e8d4,stroke:#333
  style house_shunt fill:#f5f5f5,stroke:#333
  style negative_bus fill:#f5f5f5,stroke:#333
  style starter_battery fill:#d4f1f9,stroke:#333
  style alternator fill:#d4f1f9,stroke:#333
  style starter_shunt fill:#f5f5f5,stroke:#333

  %% House battery wiring flow with gauges and colors (positive connections)
  house_battery -->|2/0 AWG| main_fuse
  main_fuse -->|"Link Bar"| disconnect_switch
  disconnect_switch -->|"Link Bar"| positive_bus
  positive_bus -->|AWG 1| inverter_charger
  positive_bus -->|AWG ?| windlass
  positive_bus -->|AWG ?| dc_panel
  
  %% Starter battery and alternator connections
  alternator -->|AWG ?| starter_battery
  starter_battery -->|AWG ?| dc_dc_charger
  dc_dc_charger -->|AWG ?| positive_bus
  
  %% Ground connections (dotted lines in blue for better visibility)
  house_battery -.->|Ground| house_shunt
  house_shunt -.->|Ground| negative_bus
  starter_battery -.->|Ground| starter_shunt
  starter_shunt -.->|Ground| negative_bus
  alternator -.->|Ground| negative_bus
  inverter_charger -.->|Ground| negative_bus
  windlass -.->|Ground| negative_bus
  dc_panel -.->|Ground| negative_bus
  dc_dc_charger -.->|Ground| negative_bus

  %% Add explanatory notes
  note_inverter["Converts 12V DC<br>to 120V AC power<br>1200W capacity"]
  note_dc_dc["Charges LiFePO4 house <br>via alternator with current limiting"]
  note_alternator["Charges batteries<br>when running"]
  
  style note_inverter fill:#fffde7,stroke:#d6d6d6
  style note_dc_dc fill:#fffde7,stroke:#d6d6d6
  style note_alternator fill:#fffde7,stroke:#d6d6d6
  
  inverter_charger --- note_inverter
  dc_dc_charger --- note_dc_dc
  alternator --- note_alternator

  %% Title with background to ensure visibility in dark mode
  title["Grace's 2025 Electrical System Upgrade<br>LiFePO4 Battery Installation"]
  style title fill:#f0f0f0,stroke:#333,color:#000000,font-size:18px,font-weight:bold
  title --- house_battery

  %% Styling for positive and negative connections
  linkStyle 0,1,2,3,4,5,6,7,8 stroke:#ff0000,stroke-width:2px
  linkStyle 9,10,11,12,13,14,15,16,17 stroke:#0066cc,stroke-width:2.5px,stroke-dasharray:3
  linkStyle 18,19,20 stroke:#d6d6d6,stroke-width:1px
  linkStyle 21 stroke:#d6d6d6,stroke-width:1px

```

## Upgrade Motivation

The 2025 electrical system upgrade was motivated by several factors:

1. **Longer Battery Life**: LiFePO4 batteries offer 2000+ cycles compared to 300-500 for AGM batteries, reducing the frequency of replacements.
2. **Higher Capacity**: Lithium batteries provide 80-90% usable capacity compared to 50% for AGM, effectively doubling usable power.
3. **Battery Health Monitoring**: Adding SmartShunt monitors allows for precise tracking of battery state and health.
4. **AC Power Availability**: The addition of an inverter provides AC power when away from shore power.
5. **Weight Reduction**: Lithium batteries offer significant weight savings over equivalent AGM batteries.

## System Components

### Power Sources
- **LiTime 12V 230Ah LiFePO4 Deep Cycle Battery**: Main house battery providing power to all onboard systems
  - Capacity: 230Ah
  - Usable capacity: ~200Ah (90% depth of discharge)
  - Weight: ~60 lbs (half the weight of the previous AGM battery)
  - Dimensions: 19" x 6.7" x 9.5"
  - Cost (April 2025): $430
  - Meets ABYC E-13 Standard for marine applications

- **12V AGM 1000 CCA Starter Battery**: High cranking power battery dedicated to engine starting
  - Retained from previous system for engine starting reliability

- **Stock Hitachi 129772-77200 55A Alternator**: Provides power to charge both batteries when the engine is running

### Protection Devices
- **Class T Fuse 200A**: Overcurrent protection for the main battery
- **Main Disconnect Switch**: Emergency cutoff for the electrical system

### Power Distribution
- **Positive Bus Bar**: Central distribution point for positive connections
- **DC Panel**: Circuit distribution for various DC loads
- **Negative Bus Bar**: Common ground return for all components

### Power Conversion
- **Victron Energy MultiPlus Pure Sine Wave Inverter Charger, UL-Certified, 12/1200/50-16 120V VE.Bus**: Inverter/charger converting 12V DC to 120V AC (1000W)
  - Provides 120V AC power from the house battery
  - Charges the house battery when connected to shore power
  - 50A charging capability
  - Cost (April 2025): $480
  - [Specifications datasheet](./specs/MultiPlus-500-1200VA-120V-EN.pdf) (Source: [Victron Energy](https://www.victronenergy.com/upload/documents/Datasheet-MultiPlus-500-1200VA-120V-EN.pdf))
  - [Full manual](./manuals/MultiPlus_500-1200VA_120Vac-manual.pdf) (Source: [Victron Energy](https://www.victronenergy.com/upload/documents/MultiPlus_12V_500-1200VA_120Vac/155314-MultiPlus_500-1200VA_120Vac-pdf-en.pdf))
  - 1200VA model chosen over 2000VA to avoid requiring larger wiring while still providing sufficient capacity for onboard needs

- **Victron Orion XS Smart 12/12 50A (700W)**: DC-DC charger that safely charges the LiFePO4 house battery from the alternator with current limiting protection
  - Protects lithium battery from alternator voltage spikes
  - Provides proper charging profile for lithium chemistry
  - [Specifications datasheet](./specs/Orion-XS-DC-DC-battery-charger-EN.pdf) (Source: [Victron Energy](https://www.victronenergy.com/upload/documents/Datasheet-Orion-XS-DC-DC-battery-charger-EN-.pdf))
  - [Full manual](./manuals/Orion_XS_DC-DC_battery_charger-manual.pdf) (Source: [Victron Energy](https://www.victronenergy.com/upload/documents/Orion_XS_12-12-50A_DC-DC_battery_charger/124067-Orion_XS_DC-DC_battery_charger-pdf-en.pdf))

### Monitoring
- **Victron Energy SmartShunt IP65 Battery Monitor (Bluetooth) - 6.5V-70V, 300 amp (House Battery)**: Monitors house battery state and power consumption
  - Tracks state of charge
  - Monitors power consumption patterns
  - Provides historical data
  - Bluetooth connectivity for monitoring via smartphone app
  - Cost (April 2025): $72
  - [Specifications datasheet](./specs/SmartShunt-IP65-EN.pdf) (Source: [Victron Energy](https://www.victronenergy.com/upload/documents/Datasheet-SmartShunt-IP65-EN-.pdf))

- **Victron Energy SmartShunt IP65 Battery Monitor (Bluetooth) - 6.5V-70V, 300 amp (Starter Battery)**: Monitors starter battery state and charging
  - Cost (April 2025): $72

### Loads
- **Windlass**: Anchor system
- **Engine Starter**: Starts the engine (part of the alternator unit)
- **Various DC Loads**: Navigation equipment, lighting, pumps, etc.
- **AC Loads**: Devices powered through the inverter when away from shore power

## Power Flow

### When Engine is Off
- House battery powers all onboard systems through the positive bus bar
- Inverter/charger provides 120V AC power from the house battery
- SmartShunts monitor power consumption and battery state

### When Engine is Running
- Alternator charges the starter battery directly
- DC-DC charger safely charges the house battery from the alternator with current limiting protection
- Both batteries provide power to their respective systems

### When Connected to Shore Power
- Inverter/charger charges the house battery
- AC power is provided directly from shore power
- DC systems continue to run from the house battery

## Wiring
- **Positive Connections**:
  - 2/0 AWG: House battery to fuse
  - Link Bar: Fuse to disconnect switch to positive bus bar
  - AWG 1: Positive bus bar to inverter
  
- **Negative/Ground Connections**:
  - All components connect to the negative bus bar for a common ground

## Benefits of the Upgrade

### Increased Capacity
- 230Ah lithium battery with 90% usable capacity provides ~200Ah of usable power
- Previous 200Ah AGM with 50% usable capacity provided only ~100Ah
- Effectively doubled usable power capacity

### Extended Battery Life
- LiFePO4 batteries typically last 2000+ cycles at 80% depth of discharge
- AGM batteries typically last 300-500 cycles at 50% depth of discharge
- Significantly reduced replacement frequency and lifetime cost

### Enhanced Monitoring
- Real-time monitoring of battery state and health
- Historical data tracking for power consumption analysis
- Early warning of potential issues

### AC Power Availability
- 1200W inverter provides AC power when away from shore power
- Enables use of AC devices without running a generator
- Improves comfort and functionality when cruising

### Weight Reduction
- Lithium battery weighs approximately half as much as the equivalent AGM battery
- Reduced weight improves vessel performance and fuel efficiency

## Conclusion
The 2025 electrical system upgrade significantly improved Grace's power capabilities through the adoption of lithium battery technology, enhanced monitoring, and the addition of inverter functionality. These improvements provide longer battery life, increased usable capacity, better monitoring, and AC power availability when away from shore power.
