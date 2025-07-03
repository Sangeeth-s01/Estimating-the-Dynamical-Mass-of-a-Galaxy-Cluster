# 📡 Estimating the Dynamical Mass of a Galaxy Cluster

This project uses real observational data from the Sloan Digital Sky Survey (SDSS) to estimate the **dynamical mass** of a galaxy cluster using Python. By analyzing the redshifts and spatial distribution of galaxies, we compute the velocity dispersion and apply the virial theorem to infer the total gravitational mass of the cluster.

---

## 📌 Objectives
- Identify galaxy cluster members using spectroscopic redshift (`specz`)
- Visualize redshift and spatial distributions
- Calculate peculiar velocities and velocity dispersion
- Estimate cluster size (in Mpc) from angular diameter
- Use the **virial theorem** to compute **dynamical mass**
- Compare with estimated luminous mass to infer presence of **dark matter**

---

## 🛰️ Tools & Libraries
- `pandas` – for data manipulation
- `matplotlib` – for visualizations
- `astropy` – for cosmological constants and conversions
- `numpy` – for numerical operations
- `Jupyter Notebook`

---

## 📈 Project Workflow

### 1. Data Preparation
- Loaded SDSS redshift data (`.csv` file)
- Grouped galaxies by `objid` and averaged redshift for multiple observations

### 2. Cluster Member Identification
- Created a histogram of redshift values
- Automatically detected the redshift peak (`z_peak`) with `numpy.histogram`
- Filtered galaxies within a redshift window (`z_peak ± 0.03`)

### 3. Velocity Dispersion
- Used the **relativistic Doppler formula** to compute peculiar velocities
- Calculated standard deviation (dispersion) of velocities

### 4. Cluster Size & Mass Estimation
- Converted maximum projected separation to angular radius (in radians)
- Computed cluster diameter using angular diameter distance formula
- Applied the **virial theorem**:

```math
M = \frac{3 \cdot \sigma^2 \cdot R}{G}
```

- Converted result to solar masses (`M_sun`)

### 5. Luminous Mass Estimate
- Used a simple estimate: `M_lum = 200 × 10^12 M_sun`

---

## 📊 Sample Visualizations
- Redshift histogram with mean and z_peak overlay
- Velocity distribution (histogram of peculiar velocities)
- Angular distribution of projected separation

![Redshift Histogram](screenshots/redshift_histogram.png)
![Velocity Distribution](screenshots/velocity_histogram.png)
![Angular Distribution](screenshots/angular_distribution.png)

---

## 🧠 Key Insights
- **Cluster Redshift:** ~0.094
- **Velocity Dispersion:** ~2.69 × 10^6 m/s
- **Cluster Diameter:** ~2765 Mpc
- **Estimated Dynamical Mass:** ~7.70 × 10^15 M_sun
- **Estimated Luminous Mass:** ~2.00 × 10^14 M_sun

➡️ This discrepancy suggests a dominant presence of **dark matter** within the cluster.

---

## 📁 Files
- `galaxy_cluster_mass_estimation.ipynb` – Jupyter notebook with full analysis
- `galaxies.csv` – sample SDSS data
- `screenshots/` – visual outputs

---

## 🚀 How to Run
1. Clone the repository
2. Install required packages:
   ```bash
   pip install pandas matplotlib numpy astropy
   ```
3. Open the notebook:
   ```bash
   jupyter notebook galaxy_cluster_mass_estimation.ipynb
   ```

---

## 📚 References
- Sloan Digital Sky Survey (SDSS): https://www.sdss.org/
- Astropy Documentation: https://docs.astropy.org
- Wikipedia: [Velocity Dispersion](https://en.wikipedia.org/wiki/Velocity_dispersion)

---

## 📬 Contact
If you're interested in astrophysics, scientific Python, or open data projects — feel free to connect or reach out!

🧑‍💻 _Author: Sangeeth s  
🔗 [LinkedIn](https://www.linkedin.com/in/sangeeth-s--1906-/)  
📧 sangeeth.s1706@gmail.com
