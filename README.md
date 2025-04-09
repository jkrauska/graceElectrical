# Marine Electrical System - 12V Battery Installation

This diagram illustrates a comprehensive marine electrical system with dual batteries (house and starter), showing all components, connections, and specifications.

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
  house_battery["LiTime 12V 230Ah LiFePO4<br>Deep Cycle Battery"]
  main_fuse["Class T Fuse 200A<br>Overcurrent Protection"]
  disconnect_switch["Main Disconnect Switch<br>Emergency Cutoff"]
  positive_bus["Positive Bus Bar<br>Power Distribution"]
  inverter_charger["Victron Energy MultiPlus<br>12/1200/50-16 120V<br>Inverter/Charger"]
  windlass["Windlass<br>Anchor System"]
  dc_panel["DC Panel<br>Circuit Distribution"]
  dc_dc_charger["Victron Orion XS Smart<br>12/12 50A (700W)<br>DC-DC Charger"]
  house_shunt["DC SmartShunt<br>House Battery Monitor"]
  negative_bus["Negative Bus Bar<br>Ground Return"]
  starter_battery["Starter Battery<br>12V AGM 1000 CCA"]
  alternator["Engine Starter/<br>Alternator<br>Stock Hitachi 129772-77200 55A"]
  starter_shunt["DC SmartShunt<br>Starter Battery Monitor"]
  
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
  main_fuse -->|2/0 AWG| disconnect_switch
  disconnect_switch -->|2/0 AWG| positive_bus
  positive_bus -->|AWG 1| inverter_charger
  positive_bus -->|AWG ?| windlass
  positive_bus -->|AWG ?| dc_panel
  
  %% Starter battery and alternator connections
  alternator -->|AWG ?| starter_battery
  starter_battery -->|AWG ?| dc_dc_charger
  dc_dc_charger -->|AWG ?| house_battery
  
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
  note_house_battery["Battery provides 12V<br>230Ah main power"]
  note_inverter["Inverter converts 12V DC<br>to 120V AC power<br>1200W capacity"]
  note_dc_dc["DC-DC charger safely charges<br>LiFePO4 house battery from<br>alternator with current limiting"]
  note_house_shunt["SmartShunt monitors<br>house battery state<br>and power consumption"]
  note_starter_battery["AGM starter battery<br>1000 Cold Cranking Amps<br>for engine ignition"]
  note_alternator["55A alternator starts engine<br>and charges batteries<br>when running"]
  note_starter_shunt["SmartShunt monitors<br>starter battery state<br>and charging"]
  
  style note_house_battery fill:#fffde7,stroke:#d6d6d6
  style note_inverter fill:#fffde7,stroke:#d6d6d6
  style note_dc_dc fill:#fffde7,stroke:#d6d6d6
  style note_house_shunt fill:#fffde7,stroke:#d6d6d6
  style note_starter_battery fill:#fffde7,stroke:#d6d6d6
  style note_alternator fill:#fffde7,stroke:#d6d6d6
  style note_starter_shunt fill:#fffde7,stroke:#d6d6d6
  
  house_battery --- note_house_battery
  inverter_charger --- note_inverter
  dc_dc_charger --- note_dc_dc
  house_shunt --- note_house_shunt
  starter_battery --- note_starter_battery
  alternator --- note_alternator
  starter_shunt --- note_starter_shunt

  %% Title with background to ensure visibility in dark mode
  title["Marine Electrical System<br>12V Battery Installation"]
  style title fill:#f0f0f0,stroke:#333,color:#000000,font-size:18px,font-weight:bold
  title --- house_battery

  %% Styling for positive and negative connections
  linkStyle 0,1,2,3,4,5,6,7,8 stroke:#ff0000,stroke-width:2px
  linkStyle 9,10,11,12,13,14,15,16,17 stroke:#0066cc,stroke-width:2.5px,stroke-dasharray:3
  linkStyle 18,19,20,21,22,23,24 stroke:#d6d6d6,stroke-width:1px

  %% Color coding legend (moved to bottom and made smaller)
  subgraph Legend["Color Legend"]
    direction LR
    legend_power["Power Source"] --- legend_protection["Protection"] --- legend_conversion["Conversion"] --- legend_load["Load"] --- legend_distribution["Distribution"] --- legend_monitor["Monitor/Ground"]
    
    style legend_power fill:#d4f1f9,stroke:#333,font-size:11px
    style legend_protection fill:#ffe6cc,stroke:#333,font-size:11px
    style legend_conversion fill:#d5e8d4,stroke:#333,font-size:11px
    style legend_load fill:#e1d5e7,stroke:#333,font-size:11px
    style legend_distribution fill:#f8cecc,stroke:#333,font-size:11px
    style legend_monitor fill:#f5f5f5,stroke:#333,font-size:11px
    style Legend font-size:12px,font-weight:bold
  end
```

## System Components

### Power Sources
- **LiTime 12V 230Ah LiFePO4 Deep Cycle Battery**: Main house battery providing power to all onboard systems
- **12V AGM 1000 CCA Starter Battery**: High cranking power battery dedicated to engine starting
- **Stock Hitachi 129772-77200 55A Alternator**: Provides power to charge both batteries when the engine is running

### Protection Devices
- **Class T Fuse 200A**: Overcurrent protection for the main battery
- **Main Disconnect Switch**: Emergency cutoff for the electrical system

### Power Distribution
- **Positive Bus Bar**: Central distribution point for positive connections
- **DC Panel**: Circuit distribution for various DC loads
- **Negative Bus Bar**: Common ground return for all components

### Power Conversion
- **Victron Energy MultiPlus 12/1200/50-16 120V**: Inverter/charger converting 12V DC to 120V AC (1200W)
- **Victron Orion XS Smart 12/12 50A (700W)**: DC-DC charger that safely charges the LiFePO4 house battery from the alternator with current limiting protection

### Monitoring
- **DC SmartShunt (House Battery)**: Monitors house battery state and power consumption
- **DC SmartShunt (Starter Battery)**: Monitors starter battery state and charging

### Loads
- **Windlass**: Anchor system
- **Engine Starter**: Starts the engine (part of the alternator unit)

## Power Flow

### When Engine is Off
- House battery powers all onboard systems through the positive bus bar
- Inverter/charger provides 120V AC power from the house battery

### When Engine is Running
- Alternator charges the starter battery directly
- DC-DC charger safely charges the house battery from the alternator with current limiting protection
- Both batteries provide power to their respective systems

## Wiring
- **Positive Connections** (Red Lines):
  - 2/0 AWG: House battery to fuse to disconnect to positive bus bar
  - AWG 1: Positive bus bar to inverter
  
- **Negative/Ground Connections** (Blue Dotted Lines):
  - All components connect to the negative bus bar for a common ground

## Notes
This diagram was created using Mermaid, a JavaScript-based diagramming tool that renders Markdown-inspired text definitions to create diagrams dynamically. The diagram uses color-coding to identify component types and connection types.
