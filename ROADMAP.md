# Tellurian Technical Architecture & Roadmap

This document maps the systems defined in the [Master Design Specification (MDS.md)](MDS.md) to technical milestones and development phases for Minecraft **1.21.1 NeoForge**.

---

## 🗺️ High-Level Development Phases

### Phase 1: Foundation & Community Infrastructure (Current)
- [x] Establish `tellurian-dev` GitHub organization.
- [x] Configure community health files (Contributing guidelines, Code of Conduct, Issue/PR templates).
- [x] Publish Master Design Specification (`MDS.md`) and Technical Roadmap.
- [x] Scaffold base modpack repository structure for NeoForge 1.21.1.

### Phase 2: Core Simulation & Topology
- [ ] Toroidal boundary coordinate wrapping (seamless transition/entity handoff across $X$ boundaries).
- [ ] Finite ore vein world generation schemas (Banded Iron Formations, Kimberlite pipes).
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
- [ ] Packwiz / modpack manifest lock and automated CI build releases.
- [ ] Community alpha testing campaign.
