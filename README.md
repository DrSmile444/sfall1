# sfall1 (Fallout 1 Engine Extension)

**sfall1** is a plugin that adds engine tweaks, fixes, and modding features to **Fallout 1**.

Main features of **sfall1** (the engine-tweak mod for *Fallout 1*):

* Increased movement and combat speed (up to \~10× normal)
* Ability to play in a window and in higher colour / graphical modes (e.g. 16-bit / “modern” colour modes)
* Use of Direct3D9 instead of DirectDraw
* Mouse enhancements: scroll wheel usable in inventory / barter / conversation / save-load menus; ability to assign actions to middle mouse button; adjust mouse sensitivity beyond the vanilla limits
* Ability to adjust or remove the 13-year time limit in the game’s plot/mechanics
* Fixes for broken perks such as Pathfinder and Sharpshooter
* Additional script functions for modders (extending what scripting can do)

Development history:

- It was originally started by **Timeslip**, who later focused on **sfall** for **Fallout 2**
- **Crafty** continued the Fallout 1 branch (“sfall1”), porting back many FO2-only features to FO1.

> **Important**: **sfall1 (Fallout 1)** is **not the same** as **sfall (Fallout 2)**.
> sfall (FO2) is maintained by the sfall team and targets Fallout 2 specifically. 

---

## What is here?

- A curated archive of **sfall1** versions found on the Internet (historical releases).
- Each version lives in its own **branch** and **tag**, with a corresponding **GitHub Release** for easy download.
- The **`main`** branch tracks the **latest** known stable version.

> For sfall (FO2), see the official repo and docs: **sfall-team/sfall** and its GitHub Pages.
> https://github.com/sfall-team/sfall

---

## Installing (Fallout 1)

1. Back up your FO1 directory.
2. Download the desired **sfall1** version from this repo’s **Releases**.
3. Extract all files, including `ddraw.dll` and `ddraw.ini` into your Fallout 1 game folder.
4. Tune options in `ddraw.ini` if you want.

> Notes:
> - Feature sets vary by version. See each version’s [`CHANGELOG/<version>.md`](CHANGELOG/) or original notes. 

---

## sfall1 vs sfall (FO2) — Key Differences

- **Target game**:
    - **sfall1** → Fallout 1 (Crafty’s continuation). 
    - **sfall (FO2)** → Fallout 2 (ongoing team maintenance). 
- **Features**:
    - Both provide engine tweaks and modder QoL, but **FO2 sfall** has broader, actively maintained feature sets.

---

## Credits

- **Timeslip** — original author of sfall (engine tweaks). 
- **Crafty** — continued Fallout 1 branch (“sfall1”). 
- **sfall team** — current maintainers of sfall (Fallout 2). 
- **Many community contributors over the years** (see [`CREDITS.md`](CREDITS.md)).

---

## Licensing

This archive contains third-party releases that did not ship with explicit license files.
Our root MIT license applies only to our own scripts and documentation.
Third-party artifacts remain under their original licenses or permissions; where unclear, they are marked as unknown in [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md).
We’re happy to correct licensing info or remove items at a rightsholder’s request (see [`DISTRIBUTION_POLICY.md`](DISTRIBUTION_POLICY.md)).

---

## Disclaimer

This is an archival convenience for the community. We do **not** own Fallout or sfall/sfall1. Respect all upstream licenses and the Fallout EULA. See [`LICENSE`](LICENSE) file.
