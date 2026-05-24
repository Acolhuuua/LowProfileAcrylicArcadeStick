# Low-Profile Acrylic Arcade Stick

This repository contains the design files and supporting information you need to build a custom low‑profile arcade stick with two acrylic panels (top + bottom) and a PETG chassis. Files include DXF and Fusion 360 models for the mechanical parts, 3D printable geometry, and the PCB assets (Gerber/BOM/positions). If you're new to these file types, read the notes below — every step is explained for people unfamiliar with laser cutting, 3D printing, or PCB fabrication.

---

**What's included**

- **Acrylic panels (laser cut DXF):** [AcrylicCuts/ArcadeStickAcrylicTopLayer.dxf](AcrylicCuts/ArcadeStickAcrylicTopLayer.dxf) and [AcrylicCuts/ArcadeStickAcrylicBottomLayer.dxf](AcrylicCuts/ArcadeStickAcrylicBottomLayer.dxf). Use these files in your laser cutter software to cut the top and bottom acrylic plates.
- **CAD / 3D models (Fusion 360):** Example bodies and mounts are in [CADFiles/Fusion/](CADFiles/Fusion/). Key Fusion files include [CADFiles/Fusion/ArcadeStickAcrylicTopLayer.f3d](CADFiles/Fusion/ArcadeStickAcrylicTopLayer.f3d) and [CADFiles/Fusion/ArcadeStickAcrylicBottomLayer.f3d](CADFiles/Fusion/ArcadeStickAcrylicBottomLayer.f3d). Open these in Fusion 360 to inspect or export STL/DXF for manufacturing.
- **STL (3D print):** The 3D printable chassis and internal parts (if any) are stored in the Fusion/STL export area inside the CAD folder. Export to STL from Fusion if you need to print.
- **PCB assets:** The repository includes the PCB supporting files in the `PCB/` folder. See [PCB/bom.csv](PCB/bom.csv) and [PCB/positions.csv](PCB/positions.csv). There is also a Gerber export included (use this to order PCBs from a manufacturer).

---

**Required hardware & fasteners (purchase links)**

These are the mechanical parts you will need to physically assemble the stick. Links are provided to the specific items the designer used:

- **Shoulder screw 25mm; M6:** https://es.aliexpress.com/item/1005007145726828.html?spm=a2g0o.order_list.order_list_main.64.3df41802u8bRF8&gatewayAdapt=glo2esp
- **Chicago screws 22mm; D3M2:** https://es.aliexpress.com/item/1005007330108497.html?spm=a2g0o.order_list.order_list_main.34.3df41802u8bRF8&gatewayAdapt=glo2esp
- **Chicago screws 12mm; D3M2:** https://es.aliexpress.com/item/1005007330108497.html?spm=a2g0o.order_list.order_list_main.125.3df41802u8bRF8&gatewayAdapt=glo2esp
- **Springs (15mm; 12mm):** https://es.aliexpress.com/item/1005010652050490.html?spm=a2g0o.order_list.order_list_main.136.3df41802u8bRF8&gatewayAdapt=glo2esp
- **Thin washers (14mm; 20mm):** https://es.aliexpress.com/item/1005001878385012.html?spm=a2g0o.productlist.main.1.b91677436lLDC8&algo_pvid=1a090554-de7d-4154-9ad3-9f98efd32106&pdp_ext_f=%7B%22order%22%3A%221340%22%2C%22eval%22%3A%221%22%2C%22fromPage%22%3A%22search%22%7D&utparam-url=scene%3Asearch%7Cquery_from%3A%7Cx_object_id%3A1005001878385012%7C_p_origin_prod%3A#nav-review
- **M6 thin nut:** https://es.aliexpress.com/item/1005006331696313.html?spm=a2g0o.order_list.order_list_main.245.3df41802u8bRF8&gatewayAdapt=glo2esp

Notes:
- Chicago (binding) screws are commonly used to fasten stacked acrylic panels without countersinking: they pass through the holes in the top panel and thread into the bottom piece to clamp the stack.
- Shoulder (shouldered) screws are useful where a smooth shaft is needed to act as a pivot or spacer; confirm which locations in the DXF require them by measuring the hole callouts in the CAD files before ordering.

---

**PCB parts & electronics**

When populating the PCB, you'll need the following components (refer to [PCB/bom.csv](PCB/bom.csv) for quantities and reference designators):

- RP2040-ZERO board (or equivalent RP2040 breakout)
- 6.2 x 6.2 mm tactile push buttons (thinner profile variants recommended for low-profile builds)
- Hole-mount JST 2.54 mm 5‑pin horizontal connector (for e.g. RGB or I/O)
- Hole-mount JST 2.54 mm 2‑pin horizontal connector (power / ground / VUSB as needed)
- Kaihl Choc V2 low-profile mechanical switches and matching hot‑swap SMD sockets (if using hot‑swap footprints)
- SK6812 MINI‑E RGB LEDs (addressable LEDs for per-key or status lighting)

Important PCB note: due to problems with the designer's KiCad libraries, the full KiCad project is not included here. Instead the exported Gerber files plus the BOM and positions CSV are included in `PCB/` so you can send these to a PCB manufacturer and assemble the board. If you need the original KiCad project files, contact the designer — they may be able to provide them or clean up the libraries on request.

---

**Other consumables & recommended extras**

- Shaft extensor and balltop: any compatible joystick shaft extender and balltop can be used — the enclosure and hole sizes are standard, so choose what feels best to you.
- Keycaps: Haute42 keycaps are compatible; any keycap set designed for the same layout/spacing will work.
- Push button rubber caps (silicone dust caps) are recommended to protect buttons and provide a soft surface.

---

**How to use each file type (step-by-step)**

1. DXF files (laser cutting): open the DXF files from `AcrylicCuts/` in your laser cutter software. Verify material thickness and scale settings before cutting. Do a single test cut on scrap material to confirm fit with fasteners.
2. Fusion 360 (`*.f3d`): open the files in Fusion 360 to inspect the 3D geometry. Export STL for 3D printing (PETG recommended for the chassis), or export DXF from Fusion if you prefer to generate your own laser-cut paths.
3. STL (3D printing): prepare the chassis parts for printing with PETG (recommended) and appropriate infill/support settings for strength. Check hole clearances (screws/press fits) against actual hardware and scale if needed.
4. PCB (Gerber/BOM/Positions): send the Gerber ZIP and the BOM/positions files in `PCB/` to your chosen PCB manufacturer. After fabrication, assemble using the BOM. Use the positions CSV for pick-and-place machines or to cross-check component placement.

---

**Assembly overview (high level)**

1. Manufacture parts: laser-cut the acrylic panels, 3D‑print the PETG chassis pieces, and order the PCB.
2. Test-fit: stack the acrylic layers and chassis parts and dry-fit all fasteners (Chicago screws, shoulder screws) without tightening to confirm alignment.
3. Populate the PCB: solder the RP2040, connectors, switches/LEDs, and any SMD sockets. Test continuity and power before plugging the board into your host device.
4. Install controls: mount joystick (use shaft extensor + balltop), install switches and keycaps, and add push button rubber caps.
5. Final assembly: once everything fits, fasten the acrylic stack using the Chicago screws and secure any M6 locations with thin nuts and washers as required. Re-test all switches and joystick travel.

Tips:
- Always test-fit mechanical fasteners before applying adhesive or final tightening.
- If a hole is tight, gently ream it with a drill bit the same diameter as the screw shank; acrylic can crack if stressed — work slowly.

---

**Tools you'll likely need**

- Laser cutter (for DXF) or access to a cutting service
- 3D printer (PETG) or printing service for the chassis
- Soldering iron and basic electronics tools (flux, solder, tweezers, wire cutters)
- Small screwdrivers / hex keys depending on fasteners
- Files, sandpaper, and deburring tools for acrylic edges

---

**Troubleshooting & support**

If parts do not fit: measure the hole diameters in the Fusion files and compare against the screw diameters you ordered. Material thickness differences (e.g., 2 mm vs 3 mm acrylic) are a common cause of misfit.

If you need the original KiCad project or different PCB footprints, contact the maintainer — the gerber/BOM/positions are included as a fallback because the KiCad libraries were not cleaned up for public release.

---

**Want changes or improvements?**

If you'd like a different top layout, alternate hole patterns, or a cleaned KiCad project, open an issue or contact the designer and request the change. Small tweaks (e.g., screw hole size) can be done quickly in Fusion 360 and re-exported.

---

**License & attribution**

- **License:** This project is licensed under the GNU General Public License v3.0 (GPL-3.0). See [LICENSE](LICENSE) for the full text. By using, modifying, or redistributing this project or derivative works, you agree to be bound by the terms of GPLv3, which require that any distributed modifications or derivative works be released under the same license (share-alike).

---