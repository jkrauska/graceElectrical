# System Patterns: Grace Electrical System

## System Architecture
The Grace Electrical System follows a dual-battery marine architecture with separate house and starter batteries. This architecture provides redundancy and specialized power delivery for different use cases.

### Key Architectural Components
1. **Power Sources**: 
   - House Battery (Primary power for onboard systems)
   - Starter Battery (Dedicated to engine starting)
   - Alternator (Charging when engine is running)
   - Shore Power (When docked)

2. **Protection Systems**:
   - Fuses and circuit breakers for overcurrent protection
   - Disconnect switches for emergency cutoff
   - Battery isolation for system separation

3. **Distribution Systems**:
   - Bus bars for power distribution
   - Circuit panels for load management
   - Grounding system for safety

4. **Conversion Systems**:
   - DC-DC charger for safe battery charging
   - Inverter for DC to AC conversion

5. **Monitoring Systems**:
   - Battery monitors for state of charge and health tracking
   - System monitors for power consumption analysis

## Key Technical Decisions

### 1. Battery Technology Selection
- **Decision**: Upgrade from AGM to LiFePO4 (Lithium Iron Phosphate) batteries
- **Rationale**: 
  - Longer lifespan (2000+ cycles vs 300-500 for AGM)
  - Higher usable capacity (80-90% vs 50% for AGM)
  - Lighter weight for equivalent capacity
  - Better charge acceptance rate
  - Flat discharge curve maintaining voltage under load

### 2. Dual Battery Configuration
- **Decision**: Maintain separate house and starter batteries
- **Rationale**:
  - Ensures starting capability even if house battery is depleted
  - Allows for specialized batteries for different functions
  - Provides system redundancy

### 3. DC-DC Charging
- **Decision**: Use a DC-DC charger between alternator and lithium battery
- **Rationale**:
  - Protects lithium batteries from alternator voltage spikes
  - Provides proper charging profile for lithium chemistry
  - Prevents overcharging of lithium batteries

### 4. Monitoring Integration
- **Decision**: Add comprehensive battery monitoring
- **Rationale**:
  - Provides accurate state of charge information
  - Enables tracking of battery health over time
  - Allows for power consumption analysis and optimization

### 5. Inverter Addition
- **Decision**: Add an inverter for AC power
- **Rationale**:
  - Enables use of AC devices when away from shore power
  - Leverages the increased capacity of lithium batteries
  - Improves comfort and functionality when cruising

## Design Patterns in Use

### 1. Redundancy Pattern
- Multiple power sources (house battery, starter battery, alternator, shore power)
- Backup systems for critical functions

### 2. Isolation Pattern
- Separation of starter and house systems
- Protection devices between system components

### 3. Centralized Distribution Pattern
- Bus bars as central connection points
- Organized wiring paths

### 4. Monitoring and Feedback Pattern
- Battery monitors providing system state information
- Data collection for performance analysis

## Component Relationships
```
[Shore Power] -----> [Inverter/Charger] <-----> [House Battery] <-----> [DC Loads]
                            ^                         ^
                            |                         |
[Engine] -----> [Alternator] -----> [Starter Battery] |
                                          |           |
                                          v           v
                                    [Starter Motor]   [DC-DC Charger]
```

## Critical Implementation Paths

### Power Generation Path
1. Shore Power → Inverter/Charger → House Battery
2. Alternator → Starter Battery → DC-DC Charger → House Battery

### Power Consumption Path
1. House Battery → Bus Bar → Distribution Panel → Individual Loads
2. House Battery → Inverter → AC Loads
3. Starter Battery → Engine Starter

### Monitoring Path
1. House Battery → SmartShunt → Monitoring System
2. Starter Battery → SmartShunt → Monitoring System
