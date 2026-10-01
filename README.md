# SpazzMods Hub

An in-app storefront window that lists every SpazzMods module, shows which
ones you have and whether they are up to date. Free for any Foundry world,
any game system.

## Install

**The easy way (Windows):** download the [SpazzMods Installer](https://github.com/Spazzletopia-Studios/spazzmods-installer/releases/latest),
run it, and click Install on SpazzMods Hub. No account needed.

**Without the installer:** paste this into Foundry's **Install Module →
Manifest URL** box:
`https://github.com/Spazzletopia-Studios/spazzmods-hub/releases/latest/download/module.json`

## Using it

- Select **SpazzMods** at the bottom of the scene controls and click the store,
  open the **SpazzMods Hub** button in the Settings sidebar tab, use the
  **Open the Hub** button in the module's own settings, or run
  `game.spazzmodsHub.open()` from a macro or the console.
- One window lists every SpazzMods module for this world's game system — free
  and premium. The list on the left has one line per module: a state dot, the
  name and its plan. Search it, or filter it by On, Off, Updates (Upd) and
  Missing (Miss).
- Click a module, or move with the arrow keys, to see its card on the right:
  the pitch, plan, installed and latest versions, its link and its switch.
  The selected module, filter, search text, focus and both scroll positions
  survive catalog redraws.
- Your installed version sits next to the latest release, with an
  **Update available** flag when you are behind and the new version runs in
  this world.
- Each module is checked against this world's Foundry and game-system
  versions (shown under the plans line). A module that cannot run here says
  **Can't run** and why, for example "Needs Foundry 14" or "Needs PF2e 8.0.0
  or newer". Its switch cannot turn it on, and **All modules** skips it.
  When an older version of that module does run here, the row names it
  ("Needs Foundry 14 · 1.11.2 runs here"); the SpazzMods Installer installs
  that version.
- Only released modules are listed. A module that is not published yet shows
  only in a world where it is already installed. Live versions of every module,
  premium ones too, show without a patron token.
- A GM can stage installed modules on or off, review the full set of changes,
  using each card's switch or **All modules** in the bottom bar to change the
  whole installed catalog, then apply them with one world reload. Required dependencies are turned on
  with their parent and cannot be turned off while another active module needs
  them. Players keep the same list in read-only mode.
  The master switch keeps Hub and world-required modules on.
- Free rows link to their public GitHub repo. Premium rows link to the
  SpazzMods Supporter tier or Complete tier on Patreon.
  Complete includes Supporter and Subsystem Forge. Row badges show the product's
  plan, not proof of your membership. The gate still decides download access.
- A **Get the Installer** button in the window gets you the one-click
  installer for the whole catalog.
- **Get Help** in the window opens the [SpazzMods Support](https://github.com/Spazzletopia-Studios/spazzmods-support)
  guide for setup and live troubleshooting.
- Works offline — the catalog paints right away, and a quiet note appears
  only if the live version check cannot reach the server.

## Setup and live support

Start with the [SpazzMods Support guide](https://github.com/Spazzletopia-Studios/spazzmods-support)
for installation, Foundry/PF2e version details, and live troubleshooting. When
reporting a problem, include the module version, Foundry and PF2e versions, the
exact action that failed, and any console error text.

---

**Foundry v13–v14 · any game system** (the hub itself needs no system; it
lists the modules made for the world's system, Pathfinder Second Edition or
5E).

## Settings

| Setting | Scope | Notes |
|---|---|---|
| Catalog server URL | world (GM) | Where the hub fetches the catalog. Leave as default. |
| Patron token | client | No longer needed since 0.8.0: live versions of every module show without it. Kept so an entered token is not lost; stored on this computer only, never replicated to other players. |

## Optional scene-control owner

The Hub is the canonical owner of the shared **SpazzMods** scene-control API at
`game.spazzmodsHub.sceneControls.addTool(controls, tool)`. SpazzMods packages
use it when the Hub is active. Each package also keeps a small local fallback,
so the Hub is never a required dependency and disabling it never removes that
package's tools. Repeated registrations merge by tool name without duplicates.

The Hub also discovers active Downtime Suite, Field & Flame, Earn Income,
Subsystem Forge's Reputation page, and Rest Flow installs and adds launchers for them. Their
existing Token Controls buttons remain in place. Missing packages are left out.

## Character and NPC sheet tools

On PF2e's character and NPC sheets (including token NPC sheets), **SpazzMods** groups existing header controls for
Runes, Level Up, Add Item Spellcasting, Staff Nexus, Fling Magic, Talent Trees,
Living Shop, and Ultimate Shapeshift's Forms. Only controls the owning module
already displays are included. NPCs get their own eligible tools, such as
Talent Trees and Runes, not character-only actions. Token, Sheet, Close, and other authors' tools
stay in the header. Click outside or press Escape to close the dropdown.

This is optional Hub behavior. Without the Hub, each module keeps its normal
header controls. No other module needs changes or a new dependency. Future
modules can mark their own header node with `data-spazzmods-sheet-tool`; they
still own its visibility, click and keyboard handlers. The Hub moves the node
without copying callbacks or changing the character. The current PF2e AppV1
sheet is covered; this does not replace AppV2's built-in controls menu.

## Zero AI

This module contains no AI-generated assets. Its icons are Foundry's bundled
Font Awesome set; there are no images at all.

## Fonts

Ships local copies of **Cinzel** and **Cinzel Decorative** (in `fonts/`),
redistributed under the SIL Open Font License — see `fonts/OFL-Cinzel.txt`.
The window wears the Spazzletopia midnight look on its own; with the
**Spazzletopia Theme** module installed, its palette takes over via the shared
`--spz-*` custom properties.

## Legal

Not affiliated with or endorsed by Paizo or Foundry Gaming. Pathfinder is a
trademark of Paizo Inc. See LICENSE.
