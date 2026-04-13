# Technocore Agent Notes

## Project Purpose

Technocore is a Stellaris origin mod built around a custom Ring World start. It also recreates supported megastructures in the starting system at game start by scanning planet flags and spawning the correct finished megastructure.

## Current Playthrough Identity

- The empire name is `Eradication Protocol`.
- The primary species name is `Cortex Node`.
- The build is a Determined Exterminator machine intelligence.
- Use this identity when writing new names, flavor text, startup text, or localisation for this playthrough unless the user asks for a different tone or faction concept.
- Keep new flavour consistent with a ruthless machine intelligence worldview and the Technocore origin theme.

## Key Behavior

- The origin is `origin_technocore`.
- On game start, the mod scans the capital system for supported megastructure flags.
- Megastructure spawn logic is split by source mod instead of keeping everything in one monolithic event.
- Ownership matters:
  - Put logic in the handler for the mod that owns the source flag.
  - If another mod overrides the final spawned megastructure, keep the compat logic in the owning handler.

## Important Files

- `common/governments/civics/technocore_start.txt`
  - Defines the Technocore origin.
- `common/solar_system_initializers/technocore_start.txt`
  - Defines the starting system and any starting flags placed on bodies.
- `common/on_actions/technocore_on_actions.txt`
  - Hooks the startup dispatcher into game start.
- `events/technocore_events.txt`
  - Main dispatcher. Scans the home system and calls per-mod handlers.
- `events/technocore_vanilla_events.txt`
  - Vanilla-owned megastructure flag handling.
- `events/technocore_giga_events.txt`
  - Gigastructural Engineering-owned megastructure flag handling.
- `events/technocore_hyperquasaric_events.txt`
  - Hyperquasaric Megaconstruction-owned megastructure flag handling.
- `events/technocore_stellar_manipulation_events.txt`
  - Stellar Manipulation Rewrite/Revival-owned megastructure flag handling.
- `events/technocore_sparble_events.txt`
  - Sparble's Stellar Hyperconstructs-owned megastructure flag handling.
- `README.md`
  - User-facing documentation for the project and current support matrix.

## Current Documentation Rule

Whenever support is added, removed, or changed for any mod or megastructure:

- update `README.md`
- keep the support list accurate
- keep each supported mod split into `Star megastructures` and `Planet megastructures` sections
- put structures built on stars into the star section for their owning mod
- put structures built on planets into the planet section for their owning mod
- mention whether a structure uses a source mod flag or a Technocore custom trigger flag
- mention star-class scaling when relevant

## Current Support Snapshot

- Vanilla
  - Dyson Sphere
  - Dyson Swarm
  - Matter Decompressor
  - Science Nexus
  - Sentry Array
  - Mega Art Installation
  - Strategic Coordination Center
  - Interstellar Assembly
  - Arc Furnace
  - Grand Archive
- Gigastructural Engineering
  - Matrioshka Brain
  - Nidavellir Hyperforge
  - Neutronium Gigaforge
  - Hyperstructural Assembly Yard
  - Star Lifter
- Hyperquasaric Megaconstruction
  - Hyperquasaric Teraforge
  - Hyperquasaric Megashipyard
- Stellar Manipulation Rewrite/Revival
  - Handler scaffold exists, no integrated structures yet
- Sparble's Stellar Hyperconstructs
  - Handler scaffold exists, no integrated structures yet

## Working Rule For Future Changes

- Prefer extending the existing dispatcher-plus-handler structure.
- For new support, inspect the source mod files first and confirm:
  - the source flag
  - the final megastructure id
  - whether the structure is built on a star or a planet
  - whether star-class scaling applies
  - whether the source mod already provides a persistent flag
- If a source mod does not provide a clean initializer-friendly flag, use a Technocore custom trigger flag and document it in `README.md`.
