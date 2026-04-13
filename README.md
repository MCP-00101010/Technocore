# Technocore

Technocore is a Stellaris origin mod centered on a custom Ring World start. It also contains startup event logic that scans the home system on game start and recreates supported megastructures based on planet flags, letting the origin start with advanced structures from vanilla Stellaris and supported megastructure mods.

## How It Works

At game start, the mod:

- checks empires with the `origin_technocore` origin
- scans every body in the capital system
- looks for supported megastructure flags
- spawns the corresponding finished megastructure

The megastructure logic is split by mod so compatibility support is easier to maintain and extend.

## Current Support

### Vanilla Stellaris

Star megastructures:

- Dyson Sphere
  - `has_dyson_sphere`
  - Spawns vanilla `dyson_sphere_5`
  - If Gigastructural Engineering is present, uses the appropriate Giga Dyson variant for the star class instead
- Dyson Swarm
  - `has_dyson_swarm`
  - Spawns `dyson_swarm_3`
  - Uses a Technocore custom trigger flag for initializer-driven placement
  - Vanilla does not provide star-class Dyson Swarm variants
- Matter Decompressor
  - `has_matter_decompressor`
  - Spawns `matter_decompressor_4`
  - Uses a Technocore custom trigger flag for initializer-driven placement

Planet megastructures:

- Science Nexus
  - `has_science_nexus`
  - Spawns `think_tank_4`
  - Uses a Technocore custom trigger flag for initializer-driven placement
- Sentry Array
  - `has_sentry_array`
  - Spawns `spy_orb_4`
  - Uses a Technocore custom trigger flag for initializer-driven placement
- Mega Art Installation
  - `has_mega_art_installation`
  - Spawns `mega_art_installation_4`
  - Uses a Technocore custom trigger flag for initializer-driven placement
- Strategic Coordination Center
  - `has_strategic_coordination_center`
  - Spawns `strategic_coordination_center_3`
  - Uses a Technocore custom trigger flag for initializer-driven placement
- Interstellar Assembly
  - `has_interstellar_assembly`
  - Spawns `interstellar_assembly_4`
  - Uses a Technocore custom trigger flag for initializer-driven placement
- Arc Furnace
  - `has_arc_furnace`
  - Spawns `orbital_arc_furnace_4`
  - Uses vanilla's own persistent source flag
- Grand Archive
  - `has_grand_archive`
  - Spawns `grand_archive_0`
  - Uses a Technocore custom trigger flag for initializer-driven placement

### Gigastructural Engineering

Star megastructures:

- Matrioshka Brain
  - `has_matrioshka_brain`
  - Supports Giga star-class variants
- Nidavellir Hyperforge
  - `has_nidavellir`
  - Spawns `nidavellir_forge_4`
- Neutronium Gigaforge
  - `has_gigaforge`
  - Spawns `neutronium_gigaforge_3`
- Hyperstructural Assembly Yard
  - `has_hyperstructural_assembly_yard`
  - Spawns `hyperstructural_ass_4`
  - Uses a Technocore custom trigger flag for initializer-driven placement
- Star Lifter
  - `has_star_lifter`
  - Spawns `star_lifter_5`
  - Supports Giga star-class variants when Giga lifter scaling is active
  - Uses a Technocore custom trigger flag for initializer-driven placement

Planet megastructures:

- Asteroid Artillery
  - `asteroid_has_artillery`
  - Spawns `asteroid_artillery_1`
- Macroengineering Testing Station
  - `has_test_site`
  - Spawns `macro_test_site_3`
- Orbital Artificial Ecosystem
  - `has_eco_arc`
  - Spawns `orbital_artificial_eco_3`
- Crystal Megabore
  - `has_crystal_megabore`
  - Spawns `crystal_megabore_1`
- Planetary Drive Yard
  - `giga_drive_yard`
  - Spawns `planetary_drive_yard_1`
  - Uses Giga's own persistent source flag
- Equatorial Shipyard
  - `has_equatorial_shipyard`
  - Spawns `eq_shipyard_2`
  - Uses a Technocore custom trigger flag for initializer-driven placement
- Kugelblitz
  - `has_kugelblitz`
  - Spawns `kugelblitz_3`
  - Uses a Technocore custom trigger flag for initializer-driven placement
- Orbital Naval Logistics Office
  - `has_orbital_naval_logistics_office`
  - Spawns `orbital_naval_logistics_office_1`
  - Uses a Technocore custom trigger flag for initializer-driven placement

### Hyperquasaric Megaconstruction

Star megastructures:

- Hyperquasaric Teraforge
  - `has_hyperquasaric_teraforge`
  - Spawns `hyperquasaric_teraforge_4`
  - Uses a Technocore custom trigger flag for initializer-driven placement
- Hyperquasaric Megashipyard
  - `has_hyperquasaric_megashipyard`
  - Spawns `hyperquasaric_megashipyard_4`
  - Uses a Technocore custom trigger flag for initializer-driven placement

Planet megastructures:

- None integrated yet

### Stellar Manipulation Rewrite/Revival

Star megastructures:

- None integrated yet

Planet megastructures:

- None integrated yet

### Sparble's Stellar Hyperconstructs

Star megastructures:

- None integrated yet

Planet megastructures:

- None integrated yet

## Notes

- Some structures use the source mod's own persistent flags.
- Some structures use Technocore-specific trigger flags where the source mod does not expose a clean initializer-friendly flag.
- Several supported structures scale by star class, so the spawned megastructure can change depending on the target star and active compatibility settings.
