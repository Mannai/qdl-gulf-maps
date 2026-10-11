# qdl-gulf-maps

Input data for the Gulf mosaic build. The code and instructions live in
[Mannai/QDL-Mannai → atlas/mosaic](https://github.com/Mannai/QDL-Mannai/tree/main/atlas/mosaic).

| path | what |
|---|---|
| `images/` | 119 sheet images (full resolution) of the 121 QDL Gulf maps, 1787–1884; two images are shared by a parent and child record |
| `bundle/manifest.json` | per map: QDL ref, title, year, record URL, image size, detected frame, starting placement (catalogue corners or hand control points) |
| `data/land_gulf.wkb` | modern coastline: OpenStreetMap land polygons clipped to the Gulf, EPSG:3857 (© OpenStreetMap contributors, ODbL) |
| `data/dem_z11/part_*.npz` | Copernicus DEM GLO-90 elevation (m, int16) on the z11 canvas grid, in row chunks (© DLR/ESA, Copernicus) |
| `data/grid.json` | the canvas grid (web mercator, zoom 11) |

The map images come from the Qatar Digital Library / British Library. See each
record's QDL page (`record_url` in the manifest) for its usage terms; most are
public domain or Open Government Licence.

## Use

```bash
git clone https://github.com/Mannai/QDL-Mannai.git
git clone https://github.com/Mannai/qdl-gulf-maps.git
export MOSAIC_HOME=$PWD/qdl-gulf-maps
bash QDL-Mannai/atlas/mosaic/remote/setup.sh
bash QDL-Mannai/atlas/mosaic/remote/run.sh prep align
```

Build outputs (`work/`, `out/`, `logs/`, `.venv/`) are written inside this folder and are gitignored.
