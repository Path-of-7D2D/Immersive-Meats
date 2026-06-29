# Immersive Meats

Immersive Meats is a 7 Days To Die V3.0 XML modlet that replaces generic raw meat harvesting with animal-specific meats, adds a butchered cut step, and updates the vanilla campfire meat recipes to use those cuts.

The goal is to keep vanilla cooking familiar while making animal harvesting feel less abstract than turning every animal into the same `foodRawMeat` stack.

## Features

- Replaces normal animal raw meat harvest drops with animal-specific raw meats.
- Adds butchered cut items used as the direct cooking ingredient.
- Updates Charred Meat, Grilled Meat, and Boiled Meat recipes to accept any butchered cut.
- Keeps zombie animals on their vanilla rotting flesh path.
- Carries vanilla raw meat gameplay stats onto the new raw meats and cuts, including smell, smell-on-use, health impact, food value, stamina penalty, and dysentery risk.
- Includes custom item icons in both `ItemIcons` and `UIAtlases/ItemIconAtlas` for V3 recipe list display.

## Animal Meat Types

| Animal | Harvested Meat |
| --- | --- |
| Chicken, hostile chicken | Raw Poultry |
| Rabbit | Raw Small Game |
| Snake | Raw Reptile Meat |
| Stag, doe | Raw Venison |
| Boar | Raw Pork |
| Coyote, wolf, mountain lion | Raw Predator Meat |
| Bear, small bear | Raw Bear Meat |

## Butchering

Raw meats are converted into cleaned cooking cuts before they can be cooked.

| Raw Meat | Butchered Cut | Raw Meat Cost |
| --- | --- | --- |
| Raw Poultry | Poultry Cut | 5 |
| Raw Small Game | Small Game Cut | 5 |
| Raw Reptile Meat | Reptile Cut | 5 |
| Raw Venison | Venison Cut | 4 |
| Raw Pork | Pork Cut | 4 |
| Raw Predator Meat | Predator Cut | 4 |
| Raw Bear Meat | Bear Cut | 4 |

## Cooking

Each butchered cut can be cooked into the vanilla meat foods:

- Charred Meat at a campfire.
- Grilled Meat at a campfire with a cooking grill.
- Boiled Meat at a campfire with a cooking pot and boiled water.

## Requirements

- 7 Days To Die V3.0.
- No DLL required.

Easy Anti-Cheat can stay enabled because this is an XML-only modlet.

## Installation

1. Download the latest `ImmersiveMeats-*.zip` from the [GitHub Releases](https://github.com/Path-of-7D2D/Immersive-Meats/releases) page.
2. Extract the release zip.
3. Copy the `1A-ImmersiveMeats` folder into your `Mods` folder:

```text
7 Days To Die/Mods/1A-ImmersiveMeats/
```

The folder is installed correctly when this file exists:

```text
7 Days To Die/Mods/1A-ImmersiveMeats/ModInfo.xml
```

## Multiplayer

Install the mod on the server and every connecting client so harvested item definitions, icons, localization, and recipe lists stay consistent.

## Compatibility

This mod patches animal harvest drops in `entityclasses.xml`, appends item definitions in `items.xml`, and replaces the vanilla Charred Meat, Grilled Meat, and Boiled Meat recipes in `recipes.xml`.

It may conflict with another mod that changes the same animal harvest drops or removes/replaces the same vanilla meat recipes.

## Testing

1. Install `1A-ImmersiveMeats` into the game's `Mods` folder.
2. Start a test world.
3. Spawn or find each animal type.
4. Harvest the corpse with a butcher-capable tool.
5. Confirm the expected raw meat is received.
6. Craft the matching butchered cut.
7. Cook Charred Meat, Grilled Meat, and Boiled Meat at a campfire.

## Releasing

The release workflow is manual. Run the `Release` GitHub Action with a `version_tag` such as `v0.1.0` or `0.1.0`.

The workflow validates the deployable `1A-ImmersiveMeats` folder, creates an `ImmersiveMeats-<version>.zip`, generates release notes with `Path-of-7D2D/Changelog-Generator`, and publishes the GitHub release.
