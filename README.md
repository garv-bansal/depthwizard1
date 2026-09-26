# <p align="center">DepthWizard</p>
<h2 align="center">Single-View Height Estimation and 3D Flythrough</h2>
<h2 align="center">TEAM AlGOHOLIC1</h2>
<h2 align="center">COMPLETE DESCRIPTION</h2>

### PS ID : SIH26175

### Team ID : 175991

### Organization : Indian Space Research Organisation(ISRO) 

### Department : Department of Space / Indian Space Research Organisation

<hr>

### PS Title :
DepthWizard - Single-View Height Estimation and 3D Flythrough

<hr>

### PS Description :
Accurate Digital Elevation Models (DEMs) and Digital Surface Models (DSMs) are important for urban planning, disaster management and reconnaissance. Traditional elevation acquisition methods such as LiDAR, stereo imaging and InSAR can require specialised sensors, additional data or significant computational resources.

Single-view depth estimation provides an alternative, but monocular depth models generally produce relative depth rather than absolute metric elevation. They can also suffer from domain gaps when applied to aerial or remote-sensing imagery.

DepthWizard addresses this by combining:

1. A pretrained monocular depth-estimation model.
2. Depth correction and refinement.
3. Metric scale calibration using available scene information.
4. Ground and building separation.
5. 3D mesh generation with real vertical building faces.
6. Interactive Three.js visualisation and measurement.

<hr>

### Overview :
DepthWizard is an end-to-end software pipeline that transforms a single optical RGB image into a measurable and navigable 3D representation of a city.

The pipeline supports both non-georeferenced and georeferenced imagery:

- **PNG / JPG** → relative surface model.
- **GeoTIFF with CRS** → absolute DSM in metres when a valid metric calibration source is available.

The system combines monocular depth estimation, image processing, geometric calibration, building extraction, terrain generation and an interactive Three.js viewer.

The goal is to provide a usable tool rather than only a concept: **one optical image in, a measurable and navigable 3D city out.**

<hr>

### Input and Output :
#### Non-Georeferenced Images

For PNG/JPG images without spatial metadata:

```text
RGB Image
   ↓
Relative Depth
   ↓
Calibration / Height Scaling
   ↓
Relative Surface Model
   ↓
3D Terrain + Buildings
   ↓
Three.js Flythrough
```

The result is a relative surface model without an absolute geographic height datum.

#### Georeferenced GeoTIFF

For GeoTIFF imagery containing coordinate-system metadata:

```text
GeoTIFF + CRS
   ↓
Depth Estimation
   ↓
Detrending
   ↓
Metric Calibration
   ↓
DSM / nDSM / DTM
   ↓
3D City Mesh
   ↓
Interactive Flythrough
```

Absolute metric elevation requires at least one real measurement or a valid scene-based calibration source. The system does not silently guess a metric scale.


### Tech Stacks Used :
⦿ <b>FrontEnd :</b> 
* [![EJS](https://img.shields.io/badge/ejs-ffffff?style=for-the-badge&logo=ejs&logoColor=90a93a)](https://ejs.co/)
  [![CSS](https://img.shields.io/badge/css-ffffff?style=for-the-badge&logo=css3&logoColor=235f9e)](https://www.w3schools.com/css/)
  [![SASS](https://img.shields.io/badge/SASS-ffffff?style=for-the-badge&logo=sass)](https://sass-lang.com/)
  [![Bootstrap](https://img.shields.io/badge/bootstrap-ffffff?style=for-the-badge&logo=bootstrap)](https://getbootstrap.com/) 

⦿ <b>BackEnd :</b>
* [![NodeJS](https://img.shields.io/badge/node.js-35495E?style=for-the-badge&logo=nodedotjs&logoColor=69a063)](https://nodejs.org/)
 [![ExpressJS](https://img.shields.io/badge/express.js-35495E?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)

⦿ <b>Database :</b>
* [![MongoDB](https://img.shields.io/badge/mongodb-ffca28?style=for-the-badge&logo=mongodb)](https://www.mongodb.com/)

⦿ <b>Deployment :</b>
* [![Render](https://img.shields.io/badge/render-0D0D0D?style=for-the-badge&logo=render&logoColor=white)](https://render.com/)

### Important URLS :
⭐️ <b>DepthWizard :</b> (https://knitkraft.onrender.com/)

[<img src="screenshots/download.gif" width="50%"/>](https://knitkraft.onrender.com/)

⭐️ <b>Main PPT :</b> [Click Here to View](https://www.canva.com/design/DAGP_9EsdGI/WQJE7HY9nDG7qmt9gBuDuA/edit)

[<img src="screenshots/finalppt.png"  width="50%"/>](https://www.canva.com/design/DAGP_9EsdGI/WQJE7HY9nDG7qmt9gBuDuA/edit)

⭐️ <b>Video : Understanding KnitKraft</b>

[👇🏻👇🏻👇🏻 Click Below 👇🏻👇🏻👇🏻](https://youtu.be/d0B1yQ7u524)

[![Watch this interactive YouTube video](https://img.youtube.com/vi/d0B1yQ7u524/hqdefault.jpg)](https://youtu.be/d0B1yQ7u524)

<hr>

## Project Created & Maintained By

## :heart: Team Algoholic1
1. [Garv Bansal](https://github.com/garv-bansal)
2. [Arpit Jain](https://github.com/arpitjain0214-pixel)
3. [Arpit Parashar](https://github.com/arpitparashar06)
4. [Bhavdeep Singh](https://github.com/Bit-wise-Bhavi)
5. [Devanshi Yadav](https://github.com/I-Himanshu)
6. [Manya Tyagi](https://github.com/manyaaaa-11)

### Hire Us
<a href="https://www.linkedin.com/in/garvbansal2/"> <img src="https://img.shields.io/badge/garv-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>
<a href="https://www.linkedin.com/in/arpit-jain-8044a9365/"> <img src="https://img.shields.io/badge/arpit jain-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>
<a href="https://www.linkedin.com/in/arpit-parashar06/"> <img src="https://img.shields.io/badge/arpit parashar-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>
<a href="https://www.linkedin.com/in/bhavdeep-singh-55a06931a/"> <img src="https://img.shields.io/badge/bhavdeep-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>
<a href="https://www.linkedin.com/in/devanshi-yadav-26a4323a2/"> <img src="https://img.shields.io/badge/devanshi-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>
<a href="https://www.linkedin.com/in/manya-tyagi-a68352380/"> <img src="https://img.shields.io/badge/manya-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>

## How to Run

### Prerequisites

Make sure you have the following installed:

* Python 3.10+
* Node.js 18+
* npm
* Git

### 1. Clone the Repository

```bash
git clone https://github.com/arpitparashar06/depthwizard.git
cd depthwizard
```

### 2. Setup Python Environment

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it:

**Windows:**

```bash
.venv\Scripts\activate
```

**Linux/macOS:**

```bash
source .venv/bin/activate
```

### 3. Install Python Dependencies

```bash
pip install -r requirements.txt
```

### 4. Start the Backend

From the project root:

```bash
python backend/server.py
```

The backend will start on:

```text
http://127.0.0.1:8000
```

### 5. Setup and Start the Frontend

Open a **new terminal** and navigate to the frontend:

```bash
cd frontend
```

Install the frontend dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

The frontend will be available at:

```text
http://localhost:5173
```

### 6. Open DepthWizard

Open the following URL in your browser:

```text
http://localhost:5173
```

### Running Both Services

DepthWizard requires both the backend and frontend to be running.

**Terminal 1 — Backend**

```bash
cd depthwizard
.venv\Scripts\activate
python backend/server.py
```

**Terminal 2 — Frontend**

```bash
cd depthwizard/frontend
npm run dev
```

Once both services are running, open:

```text
http://localhost:5173
```

The frontend communicates with the backend API to process the input imagery and generate the 3D city/elevation outputs.

## Support

💙 If you like this project, give it a '⭐' and share it with your friends!
You are free to send us PRs and issues, We'd love to help and improve this.

<h1 align="center">🙏 THANK YOU 🙏</h1>

![Typing SVG](https://readme-typing-svg.demolab.com?font=Oldenburg&color=67F7AD&lines=Best+Wishes+from+Team+Algoholic1)
