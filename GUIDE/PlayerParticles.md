# PlayerParticles Plugin

> [!NOTE]
> If you speak English please visit [PlayerParticles_EN](./PlayerParticles_En.md)

## **Descripción General**

`PlayerParticles` es un **plugin avanzado para TShock** que permite la generación de partículas específicas basadas en diversos eventos y acciones dentro del juego Terraria. Este plugin está diseñado para proporcionar efectos visuales dinámicos y personalizables que mejoran la experiencia del jugador. Cada tipo de evento (como unirse al servidor, morir, recibir daño, curarse, usar ítems o proyectiles) tiene configuraciones específicas que puedes ajustar a tu gusto.

## **Características Principales**

1. **Partículas por Eventos Globales:**
   - Partículas generadas al unirse al servidor.
   - Partículas generadas al morir (incluye efectos especiales como espirales).
   - Partículas generadas al recibir daño o curarse.

2. **Partículas Basadas en Ítems:**
   - Genera partículas personalizadas al usar ciertos ítems.
   - Soporte para partículas "orchestral" (partículas más avanzadas con posiciones aleatorias).

3. **Partículas Basadas en Proyectiles:**
   - Generación de partículas relacionadas con proyectiles específicos.
   - Soporte para partículas en trayectorias de proyectiles.
   - Configuración de partículas aleatorias cerca de proyectiles.

4. **Altamente Configurable:**
   - Archivo de configuración JSON que permite personalizar cada aspecto del comportamiento del plugin.
   - Configuración granular para cada tipo de evento y partícula.

---

## **Guía de Configuración**

El archivo de configuración (`PlayerParticles.json`) permite ajustar el comportamiento del plugin. A continuación, se detalla un ejemplo del archivo de configuración y una explicación extensiva de cada parámetro.

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

### **Sección General**
Controla las configuraciones principales del plugin.

- `EnableJoinParticles`: Activa/desactiva partículas al unirse al servidor.
- `EnableDeathParticles`: Activa/desactiva partículas al morir.
- `EnableDamageParticles`: Activa/desactiva partículas al recibir daño.
- `EnableHealingParticles`: Activa/desactiva partículas al curarse.
- `EnableItemParticles`: Activa/desactiva partículas relacionadas con ítems.
- `EnableProjectileParticles`: Activa/desactiva partículas relacionadas con proyectiles.
- `EnableProjectileTrajectoryParticles`: Activa/desactiva partículas en las trayectorias de proyectiles.

---

### **Sección EventParticles**
Configura partículas relacionadas con eventos.

- **`Join`**:
  - `TimeTicks`: Duración de las partículas generadas al unirse.
  - `ParticleIds`: IDs de las partículas generadas.

- **`Death`**:
  - `TimeTicks`: Duración de las partículas generadas al morir.
  - `ParticleIds`: IDs de las partículas generadas.
  - `SpiralEffect`: Activa/desactiva un efecto de espiral al morir.
  - `SpiralParticleId`: ID de las partículas del efecto espiral.
  - `SpiralParticleTimeTicks`: Duración de las partículas del efecto espiral.
  - `CenterParticleId`: ID de la partícula generada en el centro del jugador.
  - `CenterParticleTimeTicks`: Duración de la partícula central.

- **`DamageHealing`**:
  - `DamageParticleTimeTicks`: Duración de las partículas generadas al recibir daño.
  - `DamageParticleIds`: IDs de las partículas generadas al recibir daño.
  - `HealingParticleTimeTicks`: Duración de las partículas generadas al curarse.
  - `HealingParticleIds`: IDs de las partículas generadas al curarse.

---

### **Sección ItemParticles**
Configura partículas relacionadas con ítems.

- `ItemParticleMap`: Asocia ítems específicos con configuraciones de partículas.
  - Ejemplo: El ítem con ID `24` genera partículas con `ParticleOrchestralIds` [1, 2].
  - `RandomPosition`: Si es `true`, las partículas se generan en posiciones aleatorias.

- `DefaultParticleTimeTicks`: Duración por defecto de las partículas generadas por ítems.

---

### **Sección ProjectileParticles**
Configura partículas relacionadas con proyectiles.

- `ProjectileParticleMap`: Asocia proyectiles específicos con configuraciones de partículas.
  - Ejemplo: El proyectil con ID `1` genera partículas con `ParticleIds` [44].
  - `RandomPosition`: Si es `true`, las partículas se generan en posiciones aleatorias.

- `DefaultParticleCount`: Número por defecto de partículas generadas por proyectiles.

- **`TrajectoryParticles`**:
  - `Enabled`: Activa/desactiva partículas en trayectorias de proyectiles.
  - `ParticleIntervalTicks`: Intervalo entre partículas en ticks.
  - `ParticleIds`: IDs de las partículas generadas.
  - `RandomizePosition`: Si es `true`, las partículas se generan en posiciones aleatorias.
  - `MaxParticles`: Número máximo de partículas activas.
  - `ParticleLifetime`: Duración de las partículas en ticks.

---

### **Sección OrchestralParticles**
Configura partículas avanzadas relacionadas con ítems.

- `Items`: Asocia ítems específicos con configuraciones avanzadas de partículas.
  - Ejemplo: El ítem con ID `24` genera partículas con `ParticleIds` [1001, 1002].
  - `RandomPosition`: Si es `true`, las partículas se generan en posiciones aleatorias.
  - `ParticleCount`: Número de partículas generadas.

---

## **Comandos Disponibles**

1. `/reloadparticles` o `/rp`: Recarga el archivo de configuración.
2. `/testparticle <effectName>` o `/tsp`: Prueba un efecto de partículas específico.

---

## **Créditos**

- **Autor:** FrankV22
- **Versión:** 2.0.0

Si tienes dudas o sugerencias, no dudes en abrir un issue en el repositorio. ¡Disfruta del plugin!
