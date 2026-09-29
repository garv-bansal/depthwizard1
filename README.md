# <p align="center"><img align="center" width="80" src="docs/screenshots/logo.svg"/> DepthWizard</p>
<h2 align="center">Single-View Height Estimation and 3D Flythrough from One Optical Image</h2>
<hr>
<h2 align="center">TEAM ALGOHOLIC1 : Smart India Hackathon 2026 (SIH 2026) 🌟</h2>
<img src="docs/screenshots/app.jpg"  width="100%"/>
<h2 align="center">COMPLETE DESCRIPTION</h2>

### PS ID : SIH26175

### Team ID : 175991

### Organisation : Indian Space Research Organisation (ISRO), Department of Space

### Theme : Disaster Management

### Category : Software

### PS Title :
Single-View Height Estimation and 3D Flythrough

### PS Description :
Develop an end-to-end software pipeline that transforms single-view optical RGB remote-sensing images into high-precision elevation maps, for both non-georeferenced and georeferenced imagery:
1. Non-Georeferenced RGB Imagery (PNG / JPG): Produce a Relative Digital Surface Model (rDSM).
2. Georeferenced RGB Imagery (GeoTIFF): Produce an Absolute Digital Surface Model (DSM) with metric height values.
3. Elevation Extraction: Use a pre-trained monocular depth model to extract structure from single-view optical imagery.
4. Scale Calibration: Convert relative depth to absolute height using a low-resolution DEM (e.g. SRTM 30 m), scene statistics, semantic priors or a few Ground Control Points.
5. Visualization Layer: Project the optical image onto a 3D terrain mesh in a rendering engine (Unity / Three.js / Babylon.js) with first-person navigation and analysis of heights and slopes.
6. Validation: Measure RMSE, MAE and correlation against LiDAR across urban, sparse, hilly and forested landscapes, and deploy as a standalone application.

### Idea Title :
DepthWizard, a single-image 3D elevation platform that turns one optical image into a measurable, navigable 3D city.

### Idea Description :
A depth model can only rank heights: it says "this roof is higher than that street", never "this roof is 31 m". DepthWizard turns that ranking into metres, and then into a 3D city you can fly through.
1. Fine-tuned AI: Depth Anything V2, fine-tuned on the GAMUS dataset and Dutch/Swiss LiDAR (HeightNet), so it understands top-down imagery.
2. Tilt-free rotation ensemble: the image is predicted at 0°, 90°, 180° and 270° and averaged. This cancels the model's fake slope and gives a free per-pixel confidence map.
3. Scalable calibration: relative depth becomes metres from a learned scene prior, a known height, Ground Control Points, shadow lengths or the GHSL building-height grid.
4. Terrain fusion: Copernicus GLO-30 DEM supplies the ground, the image supplies buildings and trees, giving heights in metres above sea level.
5. 3D city: buildings extruded with flat roofs and vertical walls, textured with the original image and exported as glTF.
6. Measured, not claimed: built-in RMSE, MAE and correlation against LiDAR, split by landscape type.

### Abstract/ Summary :
Accurate elevation data is essential for urban planning, disaster response and defence, but LiDAR flights, stereo pairs and InSAR need special sensors, cost a lot and take days to weeks. Single-image depth models are cheap and fast, but they are trained on street photos, only rank heights and never give metres.
DepthWizard closes that gap. It takes one optical satellite or aerial image, predicts depth with a fine-tuned model, converts it to metres, fuses it with a global terrain model, and builds a 3D city you can fly or walk through, measure, and validate against LiDAR, on an ordinary laptop CPU and offline after the first run.

### Status :
We have implemented these features:
1. PNG / JPG → Relative DSM, and GeoTIFF → Absolute DSM, DTM and nDSM, exported as georeferenced GeoTIFFs.
2. Four engines: zero-shot, fine-tuned, direct metric, and the default hybrid that fuses them.
3. React + three.js viewer with fly, walk (1:1 scale) and VR modes, click-to-measure heights, slopes and elevation profiles, and height / slope / uncertainty layers.
4. FastAPI backend with background jobs, live progress, downloads and a LiDAR validation panel.
5. Runs on a laptop CPU, works offline after the first run, and ships as one Docker container.
6. Accuracy measured on 9 LiDAR scenes (AHN4 Netherlands + swissSURFACE3D Switzerland, 0.5 m), with no training tile within 3 km of a test scene:

| Engine | RMSE (raw) | MAE | Correlation r | Urban | Sparse | Hilly | Forest |
|---|--:|--:|--:|--:|--:|--:|--:|
| Zero-shot Depth Anything V2 + one known height | 5.37 m | 3.45 m | 0.78 | 6.20 | 3.73 | 4.41 | 7.55 |
| **DepthWizard hybrid, fully automatic** | **4.91 m** | **2.49 m** | **0.84** | 5.06 | 4.08 | 3.20 | 6.18 |

**Example: Interlaken, Switzerland** (swisstopo imagery, 300 m × 300 m at 0.5 m, fully automatic, no height typed in)

<img src="docs/screenshots/interlaken-input-output.jpg"  width="100%"/>

| 3D Flythrough | Height Layer |
|---|---|
| <img src="docs/screenshots/interlaken-flythrough.jpg"/> | <img src="docs/screenshots/interlaken-height-layer.jpg"/> |

Checked against swissSURFACE3D LiDAR inside the app: **RMSE 1.41 m, MAE 1.05 m, correlation r = 0.92**, with no adjustment.

<img src="docs/screenshots/interlaken-validation.jpg"  width="100%"/>

### Tech Stacks Used :
⦿ <b>AI / ML :</b>
* [![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)](https://www.python.org/)
  [![PyTorch](https://img.shields.io/badge/PyTorch-ffffff?style=for-the-badge&logo=pytorch&logoColor=EE4C2C)](https://pytorch.org/)
  [![Depth Anything V2](https://img.shields.io/badge/Depth%20Anything%20V2-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)](https://depth-anything-v2.github.io/)
  [![OpenCV](https://img.shields.io/badge/opencv-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)](https://opencv.org/)
  [![NumPy](https://img.shields.io/badge/numpy-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
  [![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)](https://scipy.org/)

⦿ <b>Geospatial & 3D :</b>
* [![GDAL](https://img.shields.io/badge/rasterio%20%2F%20GDAL-5CAE58?style=for-the-badge&logo=osgeo&logoColor=white)](https://rasterio.readthedocs.io/)
  [![trimesh](https://img.shields.io/badge/trimesh-555555?style=for-the-badge)](https://trimesh.org/)
  [![Copernicus](https://img.shields.io/badge/Copernicus%20GLO--30-003399?style=for-the-badge)](https://portal.opentopography.org/datasetMetadata?otCollectionID=OT.032021.4326.1)

⦿ <b>FrontEnd :</b>
* [![React](https://img.shields.io/badge/react-20232a?style=for-the-badge&logo=react&logoColor=61DAFB)](https://react.dev/)
  [![Three.js](https://img.shields.io/badge/three.js-000000?style=for-the-badge&logo=three.js&logoColor=white)](https://threejs.org/)
  [![Vite](https://img.shields.io/badge/vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)

⦿ <b>BackEnd :</b>
* [![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com/)

⦿ <b>Deployment :</b>
* [![Docker](https://img.shields.io/badge/docker-0db7ed?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
  [![Railway](https://img.shields.io/badge/Railway-131415?style=for-the-badge&logo=railway&logoColor=white)](https://railway.app/)

### Important URLS :
⭐️ <b>DepthWizard Live Prototype :</b> [Click Here to Open](https://depthwizard-production-09d9.up.railway.app/)

⭐️ <b>SIH Idea PPT :</b> [Click Here to View](docs/Algoholic1_26175_GarvBansal.pdf)

⭐️ <b>Youtube Video :</b> [Click Here to View](https://youtu.be/HquYqR6ITIg?si=8GHgUzxU-IZQIYHt)

⭐️ <b>Technical Documentation :</b> [Click Here to View](docs/TECHNICAL.md)

⭐️ <b>Training Guide :</b> [Click Here to View](training/TRAINING.md)

⭐️ <b>Benchmark Guide :</b> [Click Here to View](mathsandml/benchmark/BENCHMARK.md)

---

## Project Created & Maintained By

## :heart: Team Algoholic1
1. [Garv Bansal](https://github.com/garv-bansal)
2. [Arpit Parashar](https://github.com/arpitparashar06)
3. [Arpit Jain](https://github.com/arpitjain0214-pixel)
4. [Bhavdeep Singh](https://github.com/Bit-wise-Bhavi)
5. [Devanshi Yadav](https://github.com/Devanshi-Yadav20)
6. [Manya Tyagi](https://github.com/manyaaaa-11)

### Hire Us
<a href="https://www.linkedin.com/in/garvbansal2/"> <img src="https://img.shields.io/badge/garv-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>
<a href="https://www.linkedin.com/in/arpit-jain-8044a9365/"> <img src="https://img.shields.io/badge/arpit jain-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>
<a href="https://www.linkedin.com/in/arpit-parashar06/"> <img src="https://img.shields.io/badge/arpit parashar-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>
<a href="https://www.linkedin.com/in/bhavdeep-singh-55a06931a/"> <img src="https://img.shields.io/badge/bhavdeep-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>
<a href="https://www.linkedin.com/in/devanshi-yadav-26a4323a2/"> <img src="https://img.shields.io/badge/devanshi-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>
<a href="https://www.linkedin.com/in/manya-tyagi-a68352380/"> <img src="https://img.shields.io/badge/manya-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>

### How-to-run

- Download Python 3.10+ from the Official website [link](https://www.python.org/downloads/) (if not installed)
- Clone this Repository.
- Double-click `start.command` on macOS, `start.bat` on Windows, or run `./start.sh` on Linux.
- The first run sets everything up and downloads the depth model once. After that it starts in seconds and opens http://127.0.0.1:8000.
- Or run with Docker: `docker build -t depthwizard .` then `docker run -p 8000:8000 depthwizard`.
- Optional: put a free [OpenTopography](https://portal.opentopography.org/) key in `.env` as `OPENTOPO_KEY=...` to get heights in metres above sea level.
- Or you can directly use our application by accessing this website [link](https://depthwizard-production-09d9.up.railway.app/).

### References
1. Yang et al., "Depth Anything V2," NeurIPS 2024. [Link](https://arxiv.org/abs/2406.09414)
2. Xiong et al., "GAMUS: A Geometry-aware Multi-modal Semantic Segmentation Benchmark for Remote Sensing Data," arXiv 2023. [Link](https://arxiv.org/abs/2305.14914)
3. Chen et al., "HTC-DC Net: Monocular Height Estimation from Single Remote Sensing Images," IEEE TGRS 2023. [Link](https://doi.org/10.1109/TGRS.2023.3321255)
4. Mou & Zhu, "IM2HEIGHT: Height Estimation from Single Monocular Imagery," 2018. [Link](https://arxiv.org/abs/1802.10249)
5. He, Sun & Tang, "Guided Image Filtering," IEEE TPAMI 2013. [Link](https://ieeexplore.ieee.org/document/6319316)

Example imagery and reference LiDAR: © swisstopo (SWISSIMAGE, swissSURFACE3D), open government data.
Demo imagery: 'sadanand' by hareesh via [OpenAerialMap](https://openaerialmap.org/), CC-BY 4.0.

## Support

💙 If you like this project, give it a '⭐' and share it with your friends!
You are free to send us PRs and issues, We'd love to help and improve this.

<h1 align="center">🙏 THANK YOU 🙏</h1>

![Typing SVG](https://readme-typing-svg.demolab.com?font=Oldenburg&color=5B4FFF&lines=Best+Wishes+from+Team+Algoholic1)
