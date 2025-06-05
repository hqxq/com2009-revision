# Braitenberg Vehicles - Wiring and Behavior Reference

## Vehicle Wiring Configurations

| Vehicle | Name | Sensor Type | Connection Type | Connection Polarity | Weight/Strength | Resulting Behavior |
|---------|------|-------------|-----------------|-------------------|-----------------|-------------------|
| **1** | **Alive** | Light sensors | N/A (single sensor) | N/A | Fixed | Moves forward at constant speed |
| **2a** | **Coward** | Light sensors | Ipsilateral (uncrossed) | Positive (excitatory) | Variable | **Avoids light** - moves away from light sources |
| **2b** | **Aggressor** | Light sensors | Contralateral (crossed) | Positive (excitatory) | Variable | **Seeks light** - moves toward light sources |
| **3a** | **Lover** | Light sensors | Ipsilateral (uncrossed) | Negative (inhibitory) | Variable | **Approaches and stops** - slows down near light |
| **3b** | **Explorer** | Light sensors | Contralateral (crossed) | Negative (inhibitory) | Variable | **Explores** - complex wandering behavior |


## Detailed Behavior Analysis

### Vehicle 2a: "Coward" (Light Avoider)
```
Configuration: Ipsilateral Positive
Left Light Sensor  ────┐     ┌──── Left Motor
                       │  +  │
Right Light Sensor ────┘     └──── Right Motor
```
**Behavior:** When light hits left sensor → left motor speeds up → robot turns away from light
- Brighter light = faster turn away
- Always moves away from light sources
- "Cowardly" behavior - flees from stimulation

### Vehicle 2b: "Aggressor" (Light Seeker)
```
Configuration: Contralateral Positive  
Left Light Sensor  ────┐     ┌──── Right Motor
                       │  +  │
Right Light Sensor ────┘     └──── Left Motor
```
**Behavior:** When light hits left sensor → right motor speeds up → robot turns toward light
- Brighter light = faster approach
- Aggressively seeks light sources
- Will crash into light if unchecked

### Vehicle 3a: "Lover" (Approach and Stop)
```
Configuration: Ipsilateral Negative
Left Light Sensor  ────┐     ┌──── Left Motor
                       │  -  │
Right Light Sensor ────┘     └──── Right Motor
```
**Behavior:** When light hits left sensor → left motor slows down → robot turns toward light
- As it gets closer, both sensors activate more → both motors slow down
- **Approaches and stops near light** - "loving" behavior
- Gentle, controlled approach

### Vehicle 3b: "Explorer" (Complex Wandering)
```
Configuration: Contralateral Negative
Left Light Sensor  ────┐     ┌──── Right Motor
                       │  -  │
Right Light Sensor ────┘     └──── Left Motor
```
**Behavior:** When light hits left sensor → right motor slows down → robot turns away from light
- Creates complex wandering patterns around light sources
- Neither purely approaches nor avoids
- "Explores" the environment in interesting trajectories



## Key Concepts

### Connection Types
- **Ipsilateral (Uncrossed)**: Left sensor → Left motor, Right sensor → Right motor
- **Contralateral (Crossed)**: Left sensor → Right motor, Right sensor → Left motor

### Connection Polarities
- **Positive (Excitatory)**: More sensor input → More motor output
- **Negative (Inhibitory)**: More sensor input → Less motor output (or reverse)

### Behavioral Emergence
- Simple wiring rules create complex, seemingly purposeful behaviors
- No central control or intelligence required
- Behavior emerges from sensor-motor coupling and environmental interaction
- Small changes in wiring create dramatically different behaviors
