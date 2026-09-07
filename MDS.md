# TELLURIAN: MASTER DESIGN SPECIFICATION
*A Living Planetary Sandbox*

---

## 1. WORLD TOPOLOGY & RENDERING ENGINE

### A. The Finite Toroidal Planet
* **The Global Loop:** The world is mathematically finite and wraps continuously along the East-West axis (e.g., $X = +4000 \rightarrow X = -4000$). Crossing this boundary is completely seamless—players, vehicles, and long train assemblies transition with zero loading screens, pauses, or border barriers.
* **Seamless Visual Horizon:** Standing near the eastern boundary and looking east allows the player to physically see the landscape, structures, and terrain of the far western boundary rendered continuously into the distance.
* **Spherical Curvature Illusion:** The world geometry is projected through a dynamic curvature shader. At ground level, terrain drops off naturally with distance; as a player ascends into the higher atmosphere or low orbit, the horizon progressively curves downward, transforming the flat, looping map into the visual appearance of a spherical planet floating in space.
* **Global LOD Rendering:** The entire surface of the planet is pre-generated. A Level of Detail (LOD) distant terrain rendering engine maintains a continuous visual cache of all continents, mountain chains, oceans, and orbital structures, ensuring the world never abruptly cuts off into empty fog.
* **Toroidal Cartography:** In-game maps and navigation systems are adapted to the looping coordinate system. Traveling past the eastern edge seamlessly loops the player icon to the western edge, and navigation needles calculate the shortest path around the circumference of the globe rather than pointing backward across the entire planet.
* **Scalability:** The planet’s boundary dimensions are fully configurable during world creation:
  * *Singleplayer Preset:* Compact globe (e.g., $3,000 \times 3,000$ blocks) for tight logistics and rapid global circumnavigation.
  * *Multiplayer Preset:* Expansive globe (e.g., $12,000 \times 12,000+$ blocks) providing room for multiple competing empires, massive rail lines, and wide oceans.

---

## 2. VERTICAL COSMOLOGY (THE THREE TIERS)
All traditional dimensions are collapsed into a single, seamless vertical continuum with no loading-screen portals:

```text
       ▲  Y = 500+  │ THE SHATTERED HEAVENS (Orbital Asteroid Belt)
       │            │ Zero-G vacuum, tumbled physics asteroids, Void Wyrm boss.
───────┼────────────┼──────────────────────────────────────────────────────────
       │  Y = -64   │ THE MORTAL REALM (The Planetary Surface)
       │  to 320    │ Grand mountain ranges, flowing rivers, towns, railways.
───────┼────────────┼──────────────────────────────────────────────────────────
       │  Y = -64   │ SOLID BEDROCK CRUST (Impenetrable)
       ▼  to -250   │ Breached ONLY beneath surface volcanic/tectonic biomes.
                    │
                    │ THE UNDERWORLD (The Deep Magma Mantle)
                    │ High-heat subterranean crust, sulfur, exotic tech materials.
```

### A. The Underworld (The Deep Magma Mantle) — $Y \le -64$ down to $-250$
* **Subterranean Placement:** Exists entirely underground beneath the continental crust. The surface of the planet remains unbroken by open-air world scars.
* **The Bedrock Barrier:** Bedrock forms a solid, impenetrable floor across 95% of the planet. Digging downward in temperate forests, plains, or oceans stops permanently at bedrock.
* **Volcanic Breaches:** Bedrock is fractured **only deep beneath surface volcanic, geothermal, and tectonic biomes**. The surface geology (basalt columns, sulfur vents, ash, blackstone outcroppings) acts as a visual guide indicating where a deep shaft can breach the mantle.
* **Countless Paths of Descent:** Reaching the Underworld is a major subterranean undertaking. Players and expeditions can penetrate the mantle through numerous methods:
  * Sinking vertical industrial mine shafts using **Create** mechanical rope pulley elevators.
  * Navigating natural underground magma tubes, thermal caverns, and deep fault trenches that wind down through deepslate.
  * Blasting deep shaft corridors with explosives and reinforced scaffolding.
* **Subterranean Threshold:** At the very bottom of the volcanic deepslate ($Y \approx -64$), excavations break through into subterranean magma caverns where seamless spatial thresholds open directly into the molten Underworld ceiling.
* **Resource Exclusivity:** Nether Quartz, Blaze Burners, Basalt, Magma, and Netherite exist exclusively in this deep layer. Because surface villagers fear the Underworld and refuse to descend, players hold a total monopoly on importing these materials.

### B. The Mortal Realm (The Planetary Surface) — $Y = -64$ to $Y = 320$
* The primary terrestrial biosphere featuring full custom terrain generation, river networks, settlements, and civil infrastructure.

### C. The Shattered Heavens (The Orbital Asteroid Belt) — $Y \ge 500$
* **Atmospheric Boundary:** Ascending into the high stratosphere transitions seamlessly into low planetary orbit. Accessible **only** via aerospace craft engineered through **Create: Aeronautics** equipped for extreme altitude and vacuum.
* **Zero-G Physics Asteroids:** The high orbital realm is an asteroid belt encircling the planet. Asteroids exist as **freely rotated, non-grid-aligned physics bodies** tumbling at arbitrary angles (pitch, yaw, roll) in true zero gravity.
* **Gated Elytra:** Elytra cannot be obtained early; they are rare aerodynamic relics found strictly within derelict orbital shipwrecks drifting in the asteroid belt.
* **The Overhauled Boss (The Void Wyrm):**
  * Replaces the traditional dragon boss.
  * An opt-in, summonable cosmic leviathan nestled within a massive, hollowed-out asteroid arena.
  * Fought in 3D zero-G naval combat using player-crewed combat airships and gunboats built with **Create** and **Create: Aeronautics**, equipped with deck-mounted cannons, broadside artillery, and flak defenses.

---

## 3. FULL CUSTOM WORLD GENERATION, GEOLOGY & CLIMATE

### A. Ground-Up Custom World Generation
The world completely abandons vanilla terrain noise in favor of a massive, realistic geographical system:
* **Tectonic Landmasses:** Large-scale continental plates, sweeping ocean basins, broad coastal lowlands, and rugged highland plateaus.
* **Grand Mountain Ranges:** Towering peaks with realistic cliff faces, natural switchback passes, and glacial valleys.
* **True Downhill Flowing Rivers:** Rivers do not generate as flat, static biome canals. They carve downward through terrain from mountain headwaters to sea level, featuring natural elevation drops and directional water currents.
* **Hydro-Kinetic Power:** Natural river currents continuously spin **Create** water wheels installed along riverbanks, providing clean rotational power for local industry.

### B. Latitudinal Climate Zones ($Z$-Axis Driven)
Climate is determined strictly by latitude relative to the equator:
* **The Equator ($Z = 0$):** Tropical rainforests, savannas, and arid deserts. **No winter.** Seasons alternate between **The Monsoon (Wet Season)** and **The Drought (Dry Season)**.
* **Temperate Mid-Latitudes ($Z = \pm 2000$):** A full four-season cycle (Spring, Summer, Autumn, Winter). In winter, outdoor topsoil freezes, halting outdoor crop growth, and rivers freeze over.
* **The Polar Caps ($Z = \pm 4000$):** Permanent arctic tundra and glacial ice sheets with permafrost and long, freezing polar nights.

### C. Realistic Geological Ore Deposits (Finite Voxel Extraction)
Ores generate in massive, geologically authentic formations rather than uniform cave noise:
* **Banded Iron Formations (BIF):** Concentrated, massive iron deposits in ancient metamorphic plateaus containing thousands of ore blocks.
* **Kimberlite Pipes:** Deep, vertical volcanic columns containing rich diamond deposits.
* **Hydrothermal Veins:** Rich deposits of copper, tin, and gold running through volcanic rifts and thermal faults.
* **Placer Gravels:** Trace gold and tin flakes deposited in river gravel beds.
* **Finite Depletion:** Ores are physical blocks. When mined by hand or **Create** mechanical drills, the blocks are permanently gone. Local deposits dry up over time, requiring logistics expansion.

### D. The Steampunk Baseline: Copper & Brass
* **Abundant Surface Copper:** Copper is tuned to generate abundantly in surface outcroppings, exposed cliffs, and riverbanks.
* **Aesthetic Integration:** Because copper is cheap and accessible, settlements and players naturally use it for roofing, piping, lanterns, and structural trim, creating an oxidized verdigris aesthetic without breaking the economy.
* **Economic Gating:** Copper is structural and industrial; currency remains strictly **Emeralds**. High-tier automation requires alloying copper with **Zinc** (which is kept deeper and rarer) to produce **Brass** for **Create** mechanical systems.

### E. Anti-Softlock Safety Nets (The Closed-Planet Economy)
To ensure a depleted planet never softlocks new players or halts the space program:
* **The "Trickle Floor" (Gravel Washing & Panning):** Common cobblestone can always be crushed into gravel and washed with **Create** encased fans to extract trace iron and copper nuggets. River gravel can always be panned. It is too slow to run a factory, but guarantees a new player can always bootstrap basic tools.
* **Civilized Wage Labor:** A new player on an old, depleted server does not need to mine. They can harvest renewable timber or wheat, sell it to a town market for emeralds, and purchase finished iron tools directly from an artisan.
* **Scrap & Salvage:** Damaged tools, armor, old railway tracks, and pillager weapons can be smelted down or crushed to recycle their raw metals.
* **Mantle Geothermal Renewal:** Deep volcanic vents in the Underworld periodically deposit geothermal slag, sulfur, and mineral crusts from the planet's core, ensuring late-game empires can always harvest the fuels and metals needed to construct aerospace vessels.

### F. Agriculture, Greenhouses & Fauna
* **Climate-Locked Crops:** Crops possess strict temperature tolerances. Delicate crops wither in freezing weather.
* **Heated Greenhouses:** During winter or in polar zones, players can build enclosed glass greenhouses warmed by **Create** steam pipes and radiators connected to a boiler, allowing year-round agricultural production.
* **Grounded Fauna:** Animals spawn strictly within their native geographic zones (camels in equatorial deserts; cattle, sheep, pigs, and horses in temperate plains; yaks and polar bears in polar regions). They follow clean, reliable vanilla breeding and harvest mechanics.

---

## 4. AUTONOMOUS SETTLEMENTS & CIVIL ENGINEERING

### A. Historical Worldgen Simulation (Material Provenance)
Before the player spawns, world generation executes a historical simulation step:
1. Geology, biomes, and ore veins generate.
2. Pioneer settlement seeds appear across the globe.
3. The simulation calculates years of early history: settlements harvest local forests and quarry nearby stone and iron (physically excavating real starter mines and quarries into surrounding hills).
4. Connected trade corridors form between settlements to exchange deficits.
5. **Day 1 Result:** The world contains grounded, modestly sized settlements connected by pre-established roads, bridges, and trade routes, with physical quarries showing exactly where their materials were harvested.

### B. Deterministic 2D Plot Grid & Zoning
* Settlements expand strictly along a **2D Grid of Plots** ($16 \times 16$ or $12 \times 12$ block cells) separated by wide road corridors, completely eliminating clipping or floating structures.
* **Plot Types:**
  * *Standard Plots:* Interior cells used for housing, workshops, bakeries, and municipal halls ($1 \times 1$, $1 \times 2$, or $2 \times 2$ footprints).
  * *Environmental Anchor Plots:* Specialized plots that break strict alignment to snap directly to geographic terrain (e.g., a Fisherman's Pier snaps to deep water; a Watermill snaps flush to a riverbank with its wheel over the current).
* **Harmonious Palette Algorithm:** Building templates dynamically substitute materials based on local resource abundance and color-harmony rules (e.g., birch and river cobble in valleys; sandstone and terracotta in deserts; spruce and deepslate in taigas).

### C. Wide Surveyed Road Corridors (7–9 Block Right-of-Way)
* **Future-Proof Allocation:** When a road is surveyed, a **7-to-9 block wide corridor** is cleared of trees and obstacles.
* **Corridor Evolution:**
  * *Stage 1 (The Trail):* A narrow 1-block dirt desire path meanders down the middle of the wide clearing.
  * *Stage 2 (The Cart Road):* Upgraded to a 3-block wide gravel road with room for wagons to pass.
  * *Stage 3 (The Paved Highway):* Upgraded to a 5-to-6 block wide cobblestone street with curbs, stone slabs on inclines, and roadside lanterns.
  * *Stage 4 (The Metropolitan Avenue):* High-tier cities install dual-lane paved streets with raised sidewalks, gas lamps, and a central **Create** tramway or rail line running down the median.
* **Cut-and-Fill Limits ($\pm 1$ to $2$ Blocks):** Roads may only shave down bumps by 1–2 blocks or fill dips by 1–2 blocks, using slabs for gentle gradients. Exceeding these limits triggers modular civil engineering:
  * *Trestle Bridges:* Over deep gorges, ravines, and rivers.
  * *Switchback Passes:* Zig-zagging up steep mountain slopes.
  * *Blasted Tunnels:* Straight stone-arched tunnels punched through mountain bases, unlocked in later industrial tiers via explosives and **Create** mechanical drills.
* **Desire Paths & Speed Modifiers:** Frequent foot traffic along the surveyed corridor wears grass into dirt paths. Paved roads confer physical movement speed bonuses to players, horses, and wagons.

### D. Sprawling Agricultural Greenbelts
Agriculture is not confined inside city walls. Sprawling crop fields and animal pastures generate outside the urban core, expanding outward across the surrounding countryside as the town’s population increases.

### E. Modular Grid-Edge Walls
* **Unified Road/Wall Logic:** Walls run along the exact same grid edges as roads:
  * *Wall Segments:* Stone masonry stacked 4–5 blocks high along a grid boundary. Every wall segment generates with an **integrated 1-to-2 block wide flat walkway on top**, protected by outer crenellations for guards to patrol.
  * *Intersection with a Road:* Automatically generates an arched **Fortified Gatehouse** with iron-banded doors or a portcullis, complete with interior stairs connecting to the wall-top walkway.
  * *Parallel to a Road:* Forms an intramural rampart street running along the inner wall.
* **Demolition & Relocation:** When a city expands, old walls are de-zoned, demolished for stone, and rebuilt along the new outer grid edge.

### F. Urban Renewal & Local Material Recycling
* **Adaptive Prioritization:** The town administration dynamically updates a project queue based on civic deficits (e.g., housing shortages trigger cottage construction; high crime triggers guard barracks).
* **Demolition & Upgrading:** Low-density starter shacks or farms in prime central plots can be demolished and replaced with high-density stone buildings or rail terminals.
* **Direct Short-Circuit Scavenging:** When an old building or wall is dismantled, reclaimed materials are placed in a temporary local scrap pallet. Adjacent construction projects pull stone and timber **directly from that demolition pallet first**, eliminating unnecessary round trips to the central warehouse.

### G. Autonomous Vehicle Manufacturing
Settlements build their own transit vehicles at specialized assembly plots:
* **Assembly Sites:** Cartwright Sheds (carts/wagons), Rail Roundhouses (trains), and Coastal Drydocks/Shipyards (ships).
* **Vessel Types:**
  * *Fishing Smacks:* Sail into ocean chunks, gather fish with nets, and return to port to unload.
  * *Cargo Freighters:* Flat-bottomed steam barges or sailing schooners hauling bulk goods along coastal lanes.
  * *Naval Warships:* Iron-prowed cutters equipped with **Create: Big Cannons** that patrol coastal waters to intercept pillager pirates.

### H. Macro-to-Micro Simulation Handoff (The Observer Model)
* **Off-Screen Logic (Pure Math):** Cities, construction projects, and trade routes do not tick in full 3D when unloaded. They update on a low-frequency data heartbeat (e.g., every 10–30 seconds) via simple arithmetic in the town ledger.
* **The "Pre-Render Catch-Up" Sequence:** When a player crosses the simulation boundary toward a project:
  1. *Timestamp Check:* Calculates elapsed work (e.g., 40 blocks paved, 3 trees felled).
  2. *Voxel Committal:* Directly swaps the raw blocks in the chunk data *before* sending render packets to the player's client.
  3. *Worker Positioning:* Spawns the physical villager entities directly at the current active work front (e.g., the Builder appears holding tools at block #41, not back at the warehouse).
* **LOD World Updates:** Unloaded construction milestones (like a completed road stretch) write directly to the saved chunk data on disk and flag low-poly LOD terrain to update, allowing players to watch infrastructure expand across distant valleys through a spyglass.

---

## 5. WORKFORCE, CITIZEN LIFECYCLE & SOCIETY

### A. The 14 Lean Professions
Every citizen holds a distinct, non-overlapping profession tied to a physical workstation block:

| Category | Profession | Workstation Block | Primary Function |
| :--- | :--- | :--- | :--- |
| **Extraction** | **Woodsman** | Sawbuck | Fells trees, clears road corridors, and replants saplings. |
| | **Miner** | Mining Anvil / Winch | Extracts finite stone and ore veins in quarries and shafts. |
| | **Farmer** | Scythe Rack | Tills, plants seasonal crops, and harvests grain into silos. |
| | **Fisherman** | Bait Barrel | Harvests fish and marine resources from piers and boats. |
| **Refining** | **Blacksmith** | Forge Bellows | Smelts ores, forges sheets, tools, and **Create** cogs. |
| | **Mason** | Chisel Table | Processes raw stone into bricks, slabs, and pavers. |
| | **Carpenter** | Joiner's Bench | Cuts logs into planks, furniture, scaffolding, and frames. |
| | **Baker** | Masonry Oven | Grinds grain into flour (via millstone) and bakes bread rations. |
| **Logistics** | **Hauler** | Freight Registry Desk | Moves cargo between zones (on foot or driving horse carts). |
| | **Builder** | Masonry Trowel Box | Assembles buildings, paves roads, and constructs walls layer-by-layer. |
| | **Engineer** | Machinist Toolboard | Operates steam trains, boilers, tunnel bores, and heavy machinery. |
| **Civic** | **Town Watch** | Guard Bell Post | Universal defense: patrols streets, guards gates, and fires cannons. |
| | **Mayor** | Town Hall Ledger | Programmatic brain: manages municipal accounts, zoning, and queues. |
| | **Merchant** | Merchant Counter | Operates market stalls and player storefronts, managing retail sales. |

### B. Dedicated Housing & The Daily Life Cycle
Villagers do not sleep in their workshops; they maintain a dedicated daily routine:
1. **06:00 (Wake Up):** Citizens leave their residential homes and walk down paved streets to their assigned workstation.
2. **07:00–17:00 (Work Shift):** Workers perform their job tasks. At shift completion, the Town Treasury deposits a daily wage in Emeralds into their inventory.
3. **17:00–20:00 (Market Hour):** Citizens walk to the central Marketplace to purchase food rations (bread, beef, fish) using their earned wages.
4. **20:00 (Rest):** Citizens return to their residential homes, eat their meal, and sleep in their beds to recover stamina.

### C. Housing Tiers
* **Tier 0:** Crude tents and shanties at the pioneer campfire stage (1–2 settlers).
* **Tier 1 (Cottages — $1 \times 1$ Plot):** Timber-and-thatch single-family homes (2–3 beds).
* **Tier 2 (Townhouses — $1 \times 1$ or $1 \times 2$ Plot):** Multi-story stone row houses with bedroom lofts (4–6 beds).
* **Tier 3 (Tenements — $1 \times 2$ or $2 \times 2$ Plot):** Multi-story brick residential complexes housing 8–12 citizens.

### D. The Closed-Loop Wage & Food Economy
Money circulates through the town in an unbroken loop:
* The Town Treasury pays wages $\rightarrow$ Workers spend emeralds at the Marketplace to buy food $\rightarrow$ Merchant food revenue and municipal taxes flow back into the Town Treasury.
* **Farm Specialization:**
  * *Arable Farms (Crops):* High-volume, affordable carbohydrates (wheat, potatoes) feeding the Bakery supply chain.
  * *Pastoral Farms (Livestock):* High-value proteins (beef, pork, mutton) and industrial materials (leather for **Create** belts, wool for airships).
  * Converting farm types is not instantaneous; it requires a physical re-zoning project where builders tear down fences, clear land, and re-till furrows.

### E. Population Growth & The Sluggish Penalty
* **Two-Track Growth:**
  * *Wandering Settlers (Extrinsic):* Drifters periodically travel down the roads. If the town has an unoccupied bed and food in the market, they settle and join the workforce. If the town is full or starving, they refuse and keep moving.
  * *Natural Births (Intrinsic):* Housed families living in homes with spare beds will breed naturally if regularly fed.
* **The Sluggish Penalty (No Complex Crime):** If a villager has no bed to sleep in, or lacks emeralds to buy food, they receive the **Fatigued/Sluggish debuff**:
  * Movement speed drops significantly.
  * Work speed drops (mining, hammering, and farming take twice as long).
  * Resolving the issue simply requires zoning more housing or stocking the market with food.

### F. The Marketplace Building
The commercial heart of the town grid where food, tools, and materials are exchanged:
* **Tier 1 (Market Green):** Open gravel square with 2–3 wooden stalls selling basic bread and vegetables.
* **Tier 2 (Paved Bazaar):** Cobblestone plaza with 4–6 covered stalls adding butchers, fishmongers, and toolmakers.
* **Tier 3 (Grand Exchange):** Colonnaded brick market galleria with 8–12 dedicated merchant counters, gas lighting, and direct mechanical chute connections to storage vaults.
* **Player Usage:** Freeform players can place a **Merchant Counter** block inside any custom-built shop, tavern, or stall to hire a villager Merchant and run a private retail business.

---

## 6. LOGISTICS, THE UNIVERSAL MATERIAL ZONE & MANUFACTURING

### A. The Universal Mechanic: The Material Zone (The Green Ghost Box)
All trade, construction, warehousing, fluid handling, and shipping are powered by one universal mechanic:
* **The Bounding Volume:** Placing a zone marker renders a translucent green holographic box over a piece of land.
* **Universal Ingestion:** Any block entity with an inventory inside that volume (a carried chest, vanilla barrel, **Create** item vault, fluid tank, hopper, or cargo train wagon) is automatically registered.
* **Uniform Functionality:**
  * *At Construction Sites:* The green zone displays required materials. Builders draw items directly from containers inside to build the structure.
  * *At Market Depots:* Items deposited inside are added to town stock for sale.
  * *At Rail/Harbor Terminals:* Freight contracts complete when the required cargo enters the zone.
  * *For Fluids:* Fluid tanks or barrels placed inside the zone register their liquid volume identically to solid goods.

### B. Physical Chest Carrying & Encumbrance
* Players can sneak + right-click a chest, barrel, or crate to pick it up with all contents preserved.
* **Encumbrance Trade-Off:** Carried chests induce a significant **Slowness debuff**, disable sprinting, and fill both hands (preventing tool/weapon use).
* Serves as the tactile early-game logistics method before carts, wagons, and trains are unlocked.

### C. Steampunk Transport Progression
Transport strictly honors a Steampunk / Victorian Industrial aesthetic:
* **Tier 1:** Physical chest carrying on foot $\rightarrow$ horse-drawn carts and delivery wagons.
* **Tier 2:** Steam-powered road tractors and heavy cargo trucks.
* **Tier 3:** **Create** steam locomotives running on steel railway networks.
* **Tier 4:** **Create: Aeronautics** rigid-frame zeppelins, cargo dirigibles, and scout biplanes.
* **Tier 5 (Endgame, Player-Exclusive):** Pressurized orbital spacecraft designed for vacuum flight in the asteroid belt.

### D. On-Demand / Made-to-Order Manufacturing
Specialized goods (tools, weapons, armor, machinery parts) are not mass-produced into dead store inventory:
* **Just-in-Time Crafting:** When a player or NPC orders a tool at a workshop:
  1. The artisan checks if raw materials (e.g., 3 iron ingots, 2 sticks) exist in the shop's Material Zone.
  2. The artisan pulls the ingredients, heats the metal at the forge, plays a brief hammering animation at the anvil with sound effects, and quenches the tool in a cauldron.
  3. The finished item is placed on the counter.
* **"Bring Your Own Materials" (BYOM):** A player can supply their own raw ingots and sticks into the shop's zone, paying the artisan only a small **Labor Fee in Emeralds** to forge the tool.
* **Bulk Factory Commissions:** Large orders (e.g., 200 steel rail tracks) are submitted to a foundry, which activates its **Create** mechanical presses to roll and stamp the batch over several minutes.

### E. Autonomous Parcel & Freight Routing Pipeline
When goods are ordered remotely, the world's infrastructure physically transports the item door-to-door:
1. **Production:** The artisan places the finished item on the workshop's output pallet.
2. **Local Haul:** A town Hauler picks up the parcel and carries it to the central rail terminal or cart depot.
3. **Inter-City Transit:** A freight train, road wagon, or cargo ship moves the cargo along the surveyed corridor.
4. **Receipt:** The vehicle arrives at the destination depot and unloads the parcel into the freight bay.
5. **Final Delivery:** A local Hauler picks up the parcel, walks down the street, and deposits it directly into the customer's registered green Material Zone.
6. **Physical Vulnerability:** Because parcels travel aboard real vehicles across real terrain, shipments can be ambushed by Pillager raiders, requiring escort protection.

---

### F. Player-Owned Storefronts & Cross-Entity Commerce
* **The Merchant Desk:** Players can set up a storefront, place a **Merchant Counter**, and hire a villager Merchant on an emerald wage.
* **Configurable Buy/Sell Orders:** The player configures item prices and quantities via a ledger interface.
* **Who Shops There:**
  * *Other Players:* Browse and purchase items directly.
  * *NPC Cities:* If an NPC town has an iron deficit and the player's shop sells iron at a fair price, the NPC Mayor will dispatch a Hauler with a wagon of emeralds to buy the iron.
  * *Automated Supply Intake:* Setting a "Buy Order" for raw timber will prompt local NPC lumberjacks to bring surplus logs to the player's shop to sell for emeralds.

---

## 7. COMMERCE, CURRENCY & GLOBAL COMMUNICATION

### A. Currency: The Pure Emerald Standard
* Currency consists exclusively of vanilla **Emeralds** and **Emerald Blocks** (for compact, high-value transactions).
* No infinite renewable trade loops (no infinite stick, melon, or wool trades). Trades are strictly capped by municipal storage and consumption.

### B. Geographic Comparative Advantage (Arbitrage)
Town inventories reflect their surrounding natural environment:
* *Forest Towns:* Timber surplus $\rightarrow$ cheap wood; severe deficit of fish and salt.
* *Coastal Harbors:* Seafood surplus $\rightarrow$ cheap fish; pay high prices for imported lumber to build docks and ships.
* *Plains Towns:* Grain surplus $\rightarrow$ cheap bread; pay high prices for raw iron.
* *Mountain Foundries:* Metal surplus $\rightarrow$ cheap iron and copper; must import food to survive winter.

### C. The Interaction UI Suite
* **The Market Depot UI (Stock Exchange):** Displays real town inventory with dynamic buy/sell columns and bulk purchase options ([Buy 1x], [Buy 64x], [Buy Vault Fill]).
* **The Freight & Contract Board UI:** Displays bulk shipping manifests between cities (e.g., *"Deliver 1,024 Oak Planks to High-Peak Foundry | Payout: 8 Emerald Blocks"*).
* **The Civic & Town Hall UI:** Displays population, health, deficits, available plots for purchase, and the **[Purchase City Charter]** button.

### D. Global Information & Maritime Shipping Lanes
* **The Town Hall Mailbox:** A physical mailbox block outside the Town Hall. As long as a settlement is physically linked to others via road, rail, or sea, players can access daily regional telegrams, price fluctuations, and available shipping contracts.
* **Deep-Water Maritime Corridors:**
  * Coastal ports connect by placing an **Anchor Buoy** (floating beacon) at the harbor mouth.
  * The engine verifies an unobstructed water path across the ocean to another harbor buoy, registering an official maritime shipping lane for cargo vessels and postal traffic.

---

## 8. GOVERNANCE, REAL ESTATE & PLAYSTYLES

### A. Dual Playstyles (That Can Merge)
1. **The Corporate Tycoon:** Operates under an independent corporate charter. Builds private rail lines, mining outposts, and airship fleets; hires workers and guards on weekly emerald payroll.
2. **The Civic Mayor:** Manages urban zoning, tax rates, municipal defenses, and public projects. Can be achieved by founding a new town in the wild or buying out an existing town.

### B. City Planner Mode (Macro-Management)
* Players who do not want to place blocks manually can manage cities through the **Town Planning Board UI**:
  * Click empty plots to zone them (`[Zone: Bakery]`, `[Zone: Masonry]`, `[Priority: High]`).
  * Click grid edges to zone infrastructure (`[Zone: Stone Wall]`, `[Zone: Paved Road]`).
  * Town Builders, Masons, and Haulers automatically execute the schematics using materials from town zones.
* **Freeform Building:** Players who wish to build manually can construct custom structures freely; placing a **Workstation Block** inside any valid, enclosed room registers the building with the municipal system.

### C. Buying Cities Outright
* Any city can be purchased on the open market with Emerald Blocks.
* **Dynamic Property Value:** A battered, raided town with depleted resources costs significantly fewer emeralds; a booming metropolis with full warehouses and active trade routes costs a massive fortune.

### D. Settlement Failure & Abandoned Ruins
* **The Open Claim Rule:** If all citizens in a town perish (via starvation, raids, or disease), the settlement loses its sovereign territory claim.
* **No Squatter Bloat:** Pillagers do not move in as replacement citizens; the town simply becomes an overgrown, dark ruin.
* **Free Takeover:** Any player can walk into an abandoned, unclaimed settlement, place a Charter Stone, and claim the remaining roads, workshops, and walls for free.

---

## 9. MULTIPLAYER, LAW, THREATS & FACTIONS

### A. Soft Law & The Global Crime Stat
* **No Unbreakable Claim Shields:** Players can physically trespass, break blocks, and loot containers.
* **Witness-Based Crime:** Committing crimes inside claimed territory increases a player’s **Global Crime Stat** if seen by guards or citizens.
* **Fines vs. Outlaw Status:**
  * *Minor Crimes:* Fines can be paid off at any Town Hall to clear the record.
  * *Outlaw Threshold:* Severe crimes (murder, train robbery, bombing) mark the player as **Wanted Dead or Alive**. Fines are disabled; guards attack on sight.
  * *Execution:* Being killed inside city territory while an Outlaw revokes urban property, confiscates bank assets, and respawns the player exiled in the wilderness.
* **Player Bounty Hunting:** Tavern bulletin boards generate wanted posters for criminal players with emerald bounties.

### B. The Faction Flip: Lawful Citizen vs. Pillager Outlaw
* **Lawful Path:** Welcome in civilized cities, protected by Town Watch, targeted by Pillagers.
* **Outlaw Path:** Banished and hunted by civilized cities, but gains diplomatic access to **Pillager Outposts, Cities, and Black Markets** to trade stolen goods, buy weapons, and hire mercenaries.

### C. Scaled Pillager Aggression & The Kingpin
* **Dynamic Threat Scaling:** 
  * Pillagers operate crude scrap-metal vehicles (ramming trains, ironclad pirate barges) and stage stagecoach ambushes along roads.
  * Small scout camps ignore heavily fortified player cities (knowing they will be crushed) and target weak road convoys instead.
  * As a city grows wealthier, larger warbands with siege engines and ramming craft naturally organize attacks.
* **Player-Activated Story Arc (The Kingpin):** 
  * Ambient raids happen automatically.
  * Major narrative crises involving the **Kingpin / Iron Syndicate** (the supreme warlord running industrial foundries and dreadnoughts) are strictly **player-activated** via broken pacts, border skirmishes, or war horns.

### D. Base Defense & Offline Protection
* **Grounded Base Security:** No bespoke lock mini-games. Players protect bases normally: thick walls, iron doors, hired guards, hidden chests, and weapons.
* **Configurable Server Modes:**
  * *Protected Mode:* When a player is offline, blocks/containers in their claimed plot are completely un-interactable.
  * *Hardcore Mode:* Everything remains vulnerable 24/7; players rely purely on physical base design and guards.
* **The Universal Decency Rule:** **Pillager attacks never trigger against an offline player's territory.**

### E. Ambient Monsters & Off-Screen Combat Resolution
* **Standard Hostile Mobs Remain:** Zombies, skeletons, spiders, and creepers remain in the world as the baseline night threat, justifying streetlights, torches along roads, and Town Watch patrols.
* **Off-Screen Raid "Auto-Resolve":** When a Pillager attack occurs in an unloaded chunk, the engine runs a statistical comparison (`Attacking Threat Rating vs. Town Defense Rating`):
  * Prevents server lag from spawning hundreds of unobserved AI combatants.
  * *If the player arrives mid-battle:* Seamlessly transitions from the background calculation into physical 3D combat with active entities.
  * *If the player arrives after the battle:* The engine commits battle scars (damaged barricades, looted crates) and queues emergency repairs in the Mayor's project list unless enough time has passed for it all to be fixed already of course.

---

### SUMMARY OF THE CORE FORMULA
* **The Earth:** A finite, looping globe with full custom generation, latitudinal climate, flowing rivers, and finite geological ore veins.
* **The Machinery:** **Create** and **Create: Aeronautics** powering kinetic factories, waterwheels, steam trains, and rigid-frame airships.
* **The Society:** Autonomous cities planned on deterministic grids, powered by 14 lean professions, dedicated housing, and a closed-loop wage/food economy.
* **The Infrastructure:** A universal Material Zone powering all trade, manufacturing, and parcel freight across wide surveyed road corridors and open-water shipping lanes.
* **The Journey:** Sinking deep mine shafts to the Underworld beneath volcanic bedrock, building industrial rail empires, and flying aerospace gunboats into orbit to conquer the Void Wyrm in the asteroid belt.