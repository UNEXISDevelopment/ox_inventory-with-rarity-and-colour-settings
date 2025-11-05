# ox_inventory

A complete inventory system for FiveM, implementing items, weapons, shops, and more without any strict framework dependency.

![](https://img.shields.io/github/downloads/communityox/ox_inventory/total?logo=github)
![](https://img.shields.io/github/downloads/communityox/ox_inventory/latest/total?logo=github)
![](https://img.shields.io/github/contributors/communityox/ox_inventory?logo=github)
![](https://img.shields.io/github/v/release/communityox/ox_inventory?logo=github)

## 📚 Documentation

https://coxdocs.dev/ox_inventory

## 🎨 Rarity system + color settings (added in this build)

This build includes a non-breaking UI enhancement that colors tiles by item rarity and adds a persistent SETTINGS panel for base inventory colors.

- Rarity background classes are applied to inventory items, weapons, hotbar slots, and item notifications based on data in `data/items.lua` and `data/weapons.lua` (both Weapons and Ammo tables).
- Rarity priority: if a tile has `rarity-*`, it overrides the base theme color.
- SETTINGS button appears under CLOSE in the inventory controls (press F7 as a shortcut). Changes persist via localStorage on the client.

Quick start
- Add `rarity = 'common' | 'legendary' | 'epic'` to an item/weapon/ammo entry.
- Restart `ox_inventory` and open inventory to see the colored background.
- Open SETTINGS to adjust base tile color/opacity, border color/opacity, and label bar color.

Files
- Runtime helpers loaded by the UI (kept small and safe across updates):
	- `web/public/rarity-hotbar.js` → parses Lua data and applies `rarity-*` classes
	- `web/public/settings.css` → base theme variables, rarity styles, modal styles
	- `web/public/settings.js` → SETTINGS UI under CLOSE + persistence
- Build artifacts for immediate use are also present in `web/build/assets/`.

Details, troubleshooting, and customization tips are in `RARITY_SYSTEM_IMPLEMENTATION.md` (same folder).

## 💾 Download

https://github.com/communityox/ox_inventory/releases/latest/download/ox_inventory.zip

## Supported frameworks

We do not guarantee compatibility or support for third-party resources.

- [ox_core](https://github.com/communityox/ox_core)
- [esx](https://github.com/esx-framework/esx_core)
- [qbox](https://github.com/Qbox-project/qbx_core)
- [nd_core](https://github.com/ND-Framework/ND_Core)

## ✨ Features

- Server-side security ensures interactions with items, shops, and stashes are all validated.
- Logging for important events, such as purchases, item movement, and item creation or removal.
- Supports player-owned vehicles, licenses, and group systems implemented by frameworks.
- Fully synchronised, allowing multiple players to [access the same inventory](https://user-images.githubusercontent.com/65407488/230926091-c0033732-d293-48c9-9d62-6f6ae0a8a488.mp4).

### Items

- Inventory items are stored per-slot, with customisable metadata to support item uniqueness.
- Overrides default weapon-system with weapons as items.
- Weapon attachments and ammo system, including special ammo types.
- Durability, allowing items to be depleted or removed overtime.
- Internal item system provides secure and easy handling for item use effects.
- Compatibility with 3rd party framework item registration.

### Shops

- Restricted access based on groups and licenses.
- Support different currency for items (black money, poker chips, etc).

### Stashes

- Personal stashes, linking a stash with a specific identifier or creating per-player instances.
- Restricted access based on groups.
- Registration of new stashes from any resource.
- Containers allow access to stashes when using an item, like a paperbag or backpack.
- Access gloveboxes and trunks for any vehicle.
- Random item generation inside dumpsters and unowned vehicles.

## Copyright

Copyright © 2024 Overextended <https://github.com/overextended>

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see <https://www.gnu.org/licenses/>.
