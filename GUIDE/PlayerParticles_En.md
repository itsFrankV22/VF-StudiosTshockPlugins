# PlayerParticles Plugin

## **General Description**

`PlayerParticles` is an **advanced plugin for TShock** that allows the generation of specific particles based on various events and actions within the Terraria game. This plugin is designed to provide dynamic and customizable visual effects that enhance the player's experience. Each type of event (such as joining the server, dying, taking damage, healing, using items, or projectiles) has specific configurations that you can tailor to your liking.

## **Key Features**

1. **Global Event Particles:**
   - Particles generated when joining the server.
   - Particles generated upon death (includes special effects like spirals).
   - Particles generated when taking damage or healing.

2. **Item-Based Particles:**
   - Generate custom particles when using specific items.
   - Support for "orchestral" particles (more advanced particles with random positions).

3. **Projectile-Based Particles:**
   - Generate particles related to specific projectiles.
   - Support for particles along projectile trajectories.
   - Configuration for random particles near projectiles.

4. **Highly Configurable:**
   - JSON configuration file that allows you to customize every aspect of the plugin's behavior.
   - Granular settings for every type of event and particle.

---

## **Configuration Guide**

The configuration file (`PlayerParticles.json`) allows you to adjust the plugin's behavior. Below is an example of the configuration file with an extensive explanation of each parameter.

```json
{
  "Version": "1.0.0",
  "General": {
    "EnableJoinParticles": true,
    "EnableDeathParticles": true,
    "EnableDamageParticles": false,
    "EnableHealingParticles": false,
    "EnableItemParticles": true,
    "EnableProjectileParticles": true,
    "EnableProjectileTrajectoryParticles": true
  },
  "EventParticles": {
    "Join": {
      "TimeTicks": 60,
      "ParticleIds": [
        1,
        2
      ]
    },
    "Death": {
      "TimeTicks": 60,
      "ParticleIds": [
        1,
        2
      ],
      "SpiralEffect": true,
      "SpiralParticleId": 5,
      "SpiralParticleTimeTicks": 120,
      "CenterParticleId": 6,
      "CenterParticleTimeTicks": 100
    },
    "DamageHealing": {
      "DamageParticleTimeTicks": 60,
      "DamageParticleIds": [
        1,
        2
      ],
      "HealingParticleTimeTicks": 60,
      "HealingParticleIds": [
        3,
        4
      ]
    }
  },
  "ItemParticles": {
    "ItemParticleMap": {
      "24": {
        "ParticleOrchestralIds": [
          1,
          2
        ],
        "RandomPosition": false
      },
      "25": {
        "ParticleOrchestralIds": [
          3,
          4
        ],
        "RandomPosition": true
      }
    },
    "DefaultParticleTimeTicks": 60
  },
  "ProjectileParticles": {
    "ProjectileParticleMap": {
      "1": {
        "ParticleIds": [
          44
        ],
        "RandomPosition": false
      },
      "101": {
        "ParticleIds": [
          7,
          8
        ],
        "RandomPosition": false
      }
    },
    "DefaultParticleCount": 5,
    "TrajectoryParticles": {
      "Enabled": true,
      "ParticleIntervalTicks": 10,
      "ParticleIds": [
        9,
        10
      ],
      "RandomizePosition": false,
      "MaxParticles": 50,
      "ParticleLifetime": 30
    }
  },
  "OrchestralParticles": {
    "Items": {
      "24": {
        "ParticleIds": [
          1001,
          1002
        ],
        "RandomPosition": true,
        "ParticleCount": 3
      },
      "101": {
        "ParticleIds": [
          1003
        ],
        "RandomPosition": false,
        "ParticleCount": 1
      }
    }
  }
}
```

### **General Section**
Controls the main settings of the plugin.

- `EnableJoinParticles`: Enables/disables particles when joining the server.
- `EnableDeathParticles`: Enables/disables particles upon death.
- `EnableDamageParticles`: Enables/disables particles when taking damage.
- `EnableHealingParticles`: Enables/disables particles when healing.
- `EnableItemParticles`: Enables/disables particles related to items.
- `EnableProjectileParticles`: Enables/disables particles related to projectiles.
- `EnableProjectileTrajectoryParticles`: Enables/disables particles along projectile trajectories.

---

### **EventParticles Section**
Configures particles related to events.

- **`Join`**:
  - `TimeTicks`: Duration of particles generated when joining.
  - `ParticleIds`: IDs of the particles to generate.

- **`Death`**:
  - `TimeTicks`: Duration of particles generated upon death.
  - `ParticleIds`: IDs of the particles to generate.
  - `SpiralEffect`: Enables/disables a spiral effect upon death.
  - `SpiralParticleId`: ID of the particles in the spiral effect.
  - `SpiralParticleTimeTicks`: Duration of particles in the spiral effect.
  - `CenterParticleId`: ID of the particle generated at the player’s center.
  - `CenterParticleTimeTicks`: Duration of the center particle.

- **`DamageHealing`**:
  - `DamageParticleTimeTicks`: Duration of particles generated when taking damage.
  - `DamageParticleIds`: IDs of the particles generated when taking damage.
  - `HealingParticleTimeTicks`: Duration of particles generated when healing.
  - `HealingParticleIds`: IDs of the particles generated when healing.

---

### **ItemParticles Section**
Configures particles related to items.

- `ItemParticleMap`: Associates specific items with particle configurations.
  - Example: The item with ID `24` generates particles with `ParticleOrchestralIds` [1, 2].
  - `RandomPosition`: If `true`, particles are generated at random positions.

- `DefaultParticleTimeTicks`: Default duration of particles generated by items.

---

### **ProjectileParticles Section**
Configures particles related to projectiles.

- `ProjectileParticleMap`: Associates specific projectiles with particle configurations.
  - Example: The projectile with ID `1` generates particles with `ParticleIds` [44].
  - `RandomPosition`: If `true`, particles are generated at random positions.

- `DefaultParticleCount`: Default number of particles generated by projectiles.

- **`TrajectoryParticles`**:
  - `Enabled`: Enables/disables particles along projectile trajectories.
  - `ParticleIntervalTicks`: Interval between particle generations in ticks.
  - `ParticleIds`: IDs of the particles to generate.
  - `RandomizePosition`: If `true`, particles are generated at random positions.
  - `MaxParticles`: Maximum number of active particles.
  - `ParticleLifetime`: Duration of particles in ticks.

---

### **OrchestralParticles Section**
Configures advanced particles related to items.

- `Items`: Associates specific items with advanced particle configurations.
  - Example: The item with ID `24` generates particles with `ParticleIds` [1001, 1002].
  - `RandomPosition`: If `true`, particles are generated at random positions.
  - `ParticleCount`: Number of particles to generate.

---

## **Available Commands**

1. `/reloadparticles` or `/rp`: Reloads the configuration file.
2. `/testparticle <effectName>` or `/tsp`: Tests a specific particle effect.

---

## **Credits**

- **Author:** FrankV22
- **Version:** 2.0.0

If you have questions or suggestions, feel free to open an issue in the repository. Enjoy the plugin!
