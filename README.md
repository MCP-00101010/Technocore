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

- Dyson Sphere
  - `has_dyson_sphere`
  - Spawns vanilla `dyson_sphere_5`
  - If Gigastructural Engineering is present, uses the appropriate Giga Dyson variant for the star class instead

### Gigastructural Engineering

- Matrioshka Brain
  - `has_matrioshka_brain`
  - Supports Giga star-class variants
- Asteroid Artillery
  - `asteroid_has_artillery`
  - Spawns `asteroid_artillery_1`
- Nidavellir Hyperforge
  - `has_nidavellir`
  - Spawns `nidavellir_forge_4`
- Neutronium Gigaforge
  - `has_gigaforge`
  - Spawns `neutronium_gigaforge_3`
- Macroengineering Testing Station
  - `has_test_site`
  - Spawns `macro_test_site_3`
- Orbital Artificial Ecosystem
  - `has_eco_arc`
  - Spawns `orbital_artificial_eco_3`
- Crystal Megabore
  - `has_crystal_megabore`
  - Spawns `crystal_megabore_1`
- Hyperstructural Assembly Yard
  - `has_hyperstructural_assembly_yard`
  - Spawns `hyperstructural_ass_4`
  - Uses a Technocore custom trigger flag for initializer-driven placement
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
- Star Lifter
  - `has_star_lifter`
  - Spawns `star_lifter_5`
  - Supports Giga star-class variants when Giga lifter scaling is active
  - Uses a Technocore custom trigger flag for initializer-driven placement

### Hyperquasaric Megaconstruction

- Hyperquasaric Teraforge
  - `has_hyperquasaric_teraforge`
  - Spawns `hyperquasaric_teraforge_4`
  - Uses a Technocore custom trigger flag for initializer-driven placement
- Hyperquasaric Megashipyard
  - `has_hyperquasaric_megashipyard`
  - Spawns `hyperquasaric_megashipyard_4`
  - Uses a Technocore custom trigger flag for initializer-driven placement

### Stellar Manipulation Rewrite/Revival

- Event support file exists
- No megastructures integrated yet

### Sparble's Stellar Hyperconstructs

- Event support file exists
- No megastructures integrated yet

## Notes

- Some structures use the source mod's own persistent flags.
- Some structures use Technocore-specific trigger flags where the source mod does not expose a clean initializer-friendly flag.
- Several supported structures scale by star class, so the spawned megastructure can change depending on the target star and active compatibility settings.
