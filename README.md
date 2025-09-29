# Minecraft Block Bounding Boxes

This repository provides a JSON mapping of **Spigot block material enum names** to their corresponding **bounding box dimensions**.  
It is useful for plugins, mods, or tools that require collision or hitbox information without relying on NMS.

---

## 📄 Format

The JSON file maps each block material to its bounding box with the following structure:

    "MATERIAL_NAME": {
      "minX": <float>,
      "minY": <float>,
      "minZ": <float>,
      "maxX": <float>,
      "maxY": <float>,
      "maxZ": <float>
    }

### Example

    "CHISELED_NETHER_BRICKS": {
      "minX": 0.0,
      "minY": 0.0,
      "minZ": 0.0,
      "maxX": 1.0,
      "maxY": 1.0,
      "maxZ": 1.0
    },
    "WEATHERED_COPPER_DOOR": {
      "minX": 0.0,
      "minY": 0.0,
      "minZ": 0.8125,
      "maxX": 1.0,
      "maxY": 1.0,
      "maxZ": 1.0
    },
    "HEAVY_CORE": {
      "minX": 0.25,
      "minY": 0.0,
      "minZ": 0.25,
      "maxX": 0.75,
      "maxY": 0.5,
      "maxZ": 0.75
    }

---

## 🚀 Usage

- **Plugins/Mods**: Load this JSON and query bounding boxes by `Material` name.  
- **Tools**: Use it for hit detection, visualization, or debugging block interactions.  

Bounding boxes are defined in block-relative coordinates:
- `(0,0,0)` is the **minimum corner** of the block space.  
- `(1,1,1)` is the **maximum corner** of the block space.  

---

## ⚠️ Notes

- This data is based on bounding boxes obtained in Spigot.  
- Some blocks may have multiple bounding boxes in-game (e.g. fences, walls, doors), but this dataset provides a **single bounding box** per block material.  
- No NMS or version-specific code is required, this file is version-independent.

---

## 📜 License

MIT – free to use in any project.
