# Technical Context: Grace Electrical System

## Technologies Used

### Battery Technologies
1. **AGM (Absorbed Glass Mat) - Previous System**
   - Type: 4D AGM Deep Cycle Batteries
   - Chemistry: Lead-acid with glass mat separator
   - Voltage: 12V nominal
   - Typical lifespan: 300-500 cycles at 50% depth of discharge

2. **LiFePO4 (Lithium Iron Phosphate) - Upgraded System**
   - Type: LiTime 12V 230Ah Deep Cycle Battery
   - Chemistry: Lithium iron phosphate
   - Voltage: 12.8V nominal
   - Typical lifespan: 2000+ cycles at 80% depth of discharge

### Charging Systems
1. **Shore Power Charging**
   - Previous: Xantrax 20A Charger
   - Upgraded: Victron Energy MultiPlus 12/1200/50-16 Inverter/Charger

2. **Engine Charging**
   - Alternator: Stock Hitachi 129772-77200 55A
   - DC-DC Charging: Victron Orion XS Smart 12/12 50A (700W)

### Power Distribution
1. **Battery Switching**
   - Previous: 1/2/Both Switch for battery selection
   - Upgraded: Main Disconnect Switch with dedicated circuits

2. **Power Management**
   - Bus Bars: Positive and Negative for centralized distribution
   - Protection: Class T Fuse 200A for overcurrent protection
   - Distribution: DC Panel for circuit management

### Monitoring Systems
1. **Battery Monitoring**
   - DC SmartShunt for House Battery
   - DC SmartShunt for Starter Battery

### Power Conversion
1. **DC to AC Conversion**
   - Victron Energy MultiPlus 12/1200/50-16 120V Inverter/Charger
   - Output: 1200W at 120V AC

## Development Setup
This project is primarily documentation-based, using:
- Markdown for text documentation
- Mermaid for diagramming
- Git for version control

## Technical Constraints

### Physical Constraints
1. **Space Limitations**
   - Battery compartment size restrictions
   - Wiring path limitations in marine environment
   - Heat dissipation considerations

2. **Environmental Factors**
   - Marine environment (salt, humidity, vibration)
   - Temperature variations
   - Moisture protection requirements

### Electrical Constraints
1. **Voltage Requirements**
   - 12V DC system (nominal)
   - 120V AC output from inverter

2. **Current Limitations**
   - Alternator output: 55A maximum
   - DC-DC charger: 50A maximum
   - Inverter capacity: 1200W maximum

3. **Safety Requirements**
   - Overcurrent protection
   - Proper grounding
   - Isolation of circuits
   - Marine-grade components and wiring

## Dependencies

### Component Dependencies
1. **Battery Dependencies**
   - Battery capacity affects runtime of all systems
   - Battery chemistry determines charging requirements

2. **Charging Dependencies**
   - Alternator output affects charging rate
   - DC-DC charger protects lithium battery from alternator

3. **Load Dependencies**
   - Total load must not exceed battery capacity
   - AC loads limited by inverter capacity

### Documentation Dependencies
1. **Diagram Dependencies**
   - Mermaid syntax for creating system diagrams
   - Color coding for component categorization

2. **Content Dependencies**
   - Technical specifications from component manufacturers
   - Marine electrical standards and best practices

## Tool Usage Patterns

### Documentation Tools
1. **Markdown**
   - Used for all textual documentation
   - Supports embedded diagrams and formatting

2. **Mermaid**
   - Used for creating system diagrams
   - Embedded within markdown files
   - Supports color coding and styling

3. **Version Control**
   - Git for tracking changes
   - Commit messages document evolution of the project
