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
- One window lists every SpazzMods module — free and premium — each with a
  one-line pitch. Search the list or filter it by On, Off, Updates, and
  Missing.
- Descriptions stay folded until you open the row. Open rows, the selected
  filter, the search text, focus, and list position survive catalog redraws.
- Your installed version sits next to the latest release, with an
  **Update available** flag when you are behind.
- A GM can stage installed modules on or off, review the full set of changes,
  then apply them with one world reload. Required dependencies are turned on
  with their parent and cannot be turned off while another active module needs
  them. Players keep the same list in read-only mode.
- Free rows link to their public GitHub repo. Premium rows link to the
  SpazzMods Supporter tier or Complete tier on Patreon.
  Complete includes Supporter and Subsystem Forge. Row badges show the product's
  plan, not proof of your membership. The gate still decides download access.
- A **Get the Installer** button in the window gets you the one-click
  installer for the whole catalog.
- Works offline — the catalog paints right away, and a quiet note appears
  only if the live version check cannot reach the server.

---

**Foundry v13–v14 · any game system** (the hub itself needs no system; the
modules it lists are for Pathfinder Second Edition).

## Settings

| Setting | Scope | Notes |
|---|---|---|
| Catalog server URL | world (GM) | Where the hub fetches the catalog. Leave as default. |
| Patron token | client | Your Supporter or Complete token, if you have one. Stored on this computer only — never replicated to other players. Shows live versions for modules in your membership. |

## Optional scene-control owner

The Hub is the canonical owner of the shared **SpazzMods** scene-control API at
`game.spazzmodsHub.sceneControls.addTool(controls, tool)`. SpazzMods packages
use it when the Hub is active. Each package also keeps a small local fallback,
so the Hub is never a required dependency and disabling it never removes that
package's tools. Repeated registrations merge by tool name without duplicates.

The Hub also discovers active Downtime Suite, Campfire Kitchen, Earn Income,
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
