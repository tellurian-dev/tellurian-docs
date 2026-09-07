# Tellurian Technical Architecture & Mod Roadmap

This document maps the systems defined in the [Master Design Specification (MDS.md)](MDS.md) to modular codebases and custom mods.

Due to the sheer scale of Tellurian, mechanics are decomposed into focused, decoupled mods to ensure community maintainability, high performance, and parallel development streams.

---

## 🧩 Architectural Breakdown

```text
┌─────────────────────────────────────────────────────────────┐
│                       TELLURIAN PACK                        │
│          (Config, KubeJS scripts, Quests, Packwiz)          │
└──────────────┬───────────────────────────────┬──────────────┘
               │                               │
       ┌───────▼──────────────┐        ┌───────▼──────────────┐
       │   tellurian-civics   │        │  tellurian-topology  │
       │  (Settlement grid,   │        │ (Toroidal wrapping,  │
       │   14 professions,    │        │  LOD, vertical tiers,│
       │   material zones)    │        │  finite geology)     │
       └───────┬──────────────┘        └───────┬──────────────┘
               │                               │
               └───────────────┬───────────────┘
                               │
                    ┌──────────▼──────────┐
                    │    tellurian-core   │
                    │   (Shared math,     │
                    │    network & APIs)  │
                    └─────────────────────┘
```

### 1. `tellurian-core` (Foundational Library)
* Coordinate math (toroidal wrapping coordinate helpers, spherical distance algorithms).
* Shared data structures and networking packets.
* Integration hooks with **Create** and **Create: Aeronautics**.

### 2. `tellurian-topology` (Cosmology, Worldgen & Rendering)
* **Toroidal Seam Manager:** Seamless coordinate teleportation/wrapping along the East-West boundary for players, entities, and multi-block trains.
* **Curvature Horizon Shader & Distant LOD Engine:** World projection and continuous terrain caching.
* **Vertical Cosmology:** Bedrock mantle breaches under volcanic biomes; high stratosphere transition ($Y \ge 500$) into the zero-G asteroid belt.
* **Realistic Geology & Climate:** Banded Iron Formations, Kimberlite pipes, finite voxel depletion, and latitudinal $Z$-axis seasons.

### 3. `tellurian-civics` (Settlement Simulation, Society & Logistics)
* **Historical Generation Simulator:** Generates starter mines, quarries, and desire paths prior to player spawn.
* **2D Deterministic Plot Grid:** Zoning system for plots ($16 \times 16$ or $12 \times 12$) and wide 7–9 block surveyed road corridors.
* **14 Lean Professions & Life Cycle AI:** Workstations, sleep cycles, and daily wage/market ration loops.
* **The Material Zone (Green Ghost Box):** Universal bounding box inventory ingestion for builders, market depots, and freight terminals.
* **Physical Freight & Order System:** On-demand artisan crafting, hauler dispatch, and inter-city shipping manifests.
* **Law & Faction System:** Witness-based crime stat, Wanted status, and Pillager Outlaw alignment.

---

## 🗺️ High-Level Development Phases

### Phase 1: Foundation & Community Infrastructure (Current)
- [x] Establish `tellurian-dev` GitHub organization.
- [x] Configure community health files (Contributing guidelines, Code of Conduct, Issue/PR templates).
- [x] Publish Master Design Specification (`MDS.md`) and Technical Roadmap.
- [x] Scaffold base modpack repository structure.

### Phase 2: Core Simulation & Topology Prototype
- [ ] World boundary coordinate wrapping POC (teleportation/entity handoff across $X$ boundaries).
- [ ] Finite ore vein world generation schemas.
- [ ] Bedrock volcanic breach generation for Underworld access.

### Phase 3: Settlements & Logistics Engine
- [ ] 2D Plot Grid surveyor and cut-and-fill road corridor logic.
- [ ] Material Zone block entity bounding box registration.
- [ ] 14 NPC profession routines and daily market cycle.

### Phase 4: Industrial Interop & Flight
- [ ] Create rotational hydro-kinetic integration with flowing downhill rivers.
- [ ] Create: Aeronautics zero-G tumbling asteroid space tier and Void Wyrm boss arena.
- [ ] Maritime shipping lane registration and NPC trade fleets.

### Phase 5: Pack Integration, Balance & Release
- [ ] Complete KubeJS balance and economic tuning (eliminating infinite renewable loops).
- [ ] Packwiz manifest lock and automated CI build releases.
- [ ] Community alpha testing campaign.
