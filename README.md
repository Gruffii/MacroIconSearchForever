# Macro Icon Search for WoW: Forever

A fast, lightweight macro-icon search and filter addon for **WoW: Forever**.

Instead of scrolling through thousands of macro icons, Macro Icon Search adds a search field and quick filters directly to the normal macro icon picker.

> **Current stable version:** 2.10.3  
> **Embedded Forever icon set:** 27,714 icons

[Deutsche Beschreibung](README.de.md)

## Before / After

### Before
Default WoW: Forever macro icon picker.

![Before - default WoW Forever macro icon picker](before.png.png)

### After
Macro Icon Search adds a search bar, color filters, class filters, profession filters, and fast browsing directly inside the macro icon picker.

![After - Macro Icon Search with search and filters](after.png.png)

## Features

- **Fast text search** for icon filenames, e.g. `fire`, `sword`, `shadow`, `bear`
- **Real pixel-color filters** based on offline icon-image analysis
- **13 color filters:** Red, Orange, Yellow, Gold, Green, Cyan, Blue, Purple, Pink, Brown, Black, Gray, White
- **Color strength levels:** broad, strong (`!`), dominant (`!!`)
- **Class filters:** Warrior, Paladin, Hunter, Rogue, Priest, Shaman, Mage, Warlock, Druid
- **Profession filters:** Alchemy, Blacksmithing, Enchanting, Engineering, Herbalism, Leatherworking, Mining, Skinning, Tailoring, Cooking, Fishing, First Aid, Jewelcrafting
- **Combine filters with AND logic**
- **Right-click reset** for individual quick filters
- **Mouse-wheel page navigation** through filtered results
- Works with the normal **All Icons / Spells / Items** selector
- **English and German UI**
- Optimized to avoid large FPS drops while searching/filtering

## How it works

### Text search

Most normal text searches use a pre-generated **2-/3-character filename index**.

Instead of scanning all 27,714 icons for every search, the addon first narrows the search to a much smaller candidate set and then verifies only those icons.

Examples:

```text
fire
sword
shield
bear
dragon
shadow
```

### Pixel-color search

Color filters are based on analyzed icon pixels rather than only icon names.

Available colors:

```text
red orange yellow gold green cyan blue
purple pink brown black gray white
```

Color strength can also be entered as text:

```text
green     broad match
green!    strong match
green!!   dominant match
```

Clicking a color button repeatedly cycles:

```text
Broad -> Strong -> Dominant -> Off
```

Right-clicking the button resets only that color.

### Combine filters

Quick filters and text search can be combined.

Examples:

```text
Green + Druid + bear
Blue + Mage + frost
Red + Warrior + sword
```

All active conditions must match.

## Mouse-wheel navigation

When filtered results are visible:

- **Mouse wheel down:** next page
- **Mouse wheel up:** previous page
- The `<` and `>` buttons remain available
- The current page and total match count are shown at the bottom of the icon grid

Example:

```text
Page 1 / 84 - 3891 matches
```

## Database coverage

The current embedded WoW: Forever data set contains:

| Data | Count |
|---|---:|
| Total macro icons | 27,714 |
| Spell icons | 2,688 |
| Item icons | 25,026 |
| Resolved icon filenames | 27,409 |
| Unresolved filenames | 305 |
| Icons with pixel-color data | 27,355 |
| Icons without pixel-color data | 359 |

The embedded exact icon set was exported from **Forever build 70205**.

## Special searches

Icons without a resolved filename can be found with:

```text
lost
unknown
unresolved
```

Icons without analyzed pixel-color data can be found with:

```text
nocolor
colorlost
farblos
```

## Installation

1. Download the latest release ZIP.
2. Extract it.
3. Make sure the addon folder is named `MacroIconSearch`.
4. Copy it to:

```text
World of Warcraft/
└── Interface/
    └── AddOns/
        └── MacroIconSearch/
```

5. Start the game or use:

```text
/reload
```

6. Open the normal Macro window and choose an icon. The search field and **Filters** button appear in the icon-selection window.

## Slash commands

| Command | Description |
|---|---|
| `/mis help` | Show available commands |
| `/mis status` | Addon/database status |
| `/mis colors` | Pixel-color database info |
| `/mis names` | Filename-resolution statistics |
| `/mis lost` | Unresolved filename information |
| `/mis exact` | Embedded Forever icon-set information |
| `/mis coverage` | Database coverage |
| `/mis stats green` | Statistics for a color |
| `/mis perf` | Performance information for the last search |

Additional diagnostic commands may be available in the addon.

## Performance design

Macro Icon Search avoids replacing Blizzard's complete icon data provider during an active filter.

The current implementation uses:

- pre-generated direct lists for quick filters
- static intersection for combined filters
- indexed filename search
- a lightweight custom result grid
- reusable result buttons
- paged results
- no external runtime analysis while the game is running

This keeps normal quick-filter usage effectively instant and greatly reduces the amount of work needed for text searches.

## No external software required

Macro Icon Search is a normal Lua addon. It does not require executable files, DLL injection, memory reading, input automation, or an external background program.

The icon-name and pixel-color databases were generated offline and are shipped as static addon data.

## Compatibility

This project is built specifically for **WoW: Forever** and its macro icon picker.

Other World of Warcraft clients may use different UI APIs, icon sets, or interface versions and are not currently the primary target.

## Changelog

See [CHANGELOG.md](CHANGELOG.md).

## Bugs and suggestions

If you find a bug, please open a GitHub Issue and include:

- what you searched or clicked
- what you expected
- what happened instead
- any Lua error message
- output from `/mis perf` when the problem is performance-related

## License

No open-source license has been selected yet. Until a license is added, normal copyright rules apply to the source code.

## Disclaimer

This is a community-made addon and is not affiliated with or endorsed by Blizzard Entertainment. World of Warcraft and related names are trademarks of their respective owners.

## Release naming

All packaged releases use this naming scheme:

```text
MacroIconSearchForever_v.X.XX.x.zip
```

Example:

```text
MacroIconSearchForever_v2.10.3.zip
```
