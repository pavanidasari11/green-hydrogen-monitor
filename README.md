# Green Hydrogen Production Monitoring & Analysis System

An academic, beginner-friendly web application designed to simulate, monitor, and analyze green hydrogen production data from a simulated water electrolyzer. 

---

## 📌 Project Objective
This project demonstrates how a software application processes, tracks, and analyzes production data from an electrolyzer. Since this is a software-only academic project, it does not connect to real physical sensors. Instead, data is manually inputted via forms or loaded using a mock database seed utility.

---

## 🛠️ Technologies Used
- **Backend:** Python 3 + Flask (Web Framework)
- **Database:** SQLite (Relational SQL Database)
- **Frontend UI:** HTML5, CSS3 Grid & Flexbox (Vanilla styling)
- **Frontend Interaction:** Vanilla JavaScript (Live input calculation preview)
- **Data Visualization:** Chart.js (Loaded via CDN)

---

## 📐 Main Calculations

The system calculates key performance metrics using the following standard engineering equations:

1. **Energy Used ($kWh$):**
   $$\text{Energy Used (kWh)} = \text{Power Used (kW)} \times \text{Operating Time (h)}$$

2. **Hydrogen Mass Produced ($kg$):**
   $$\text{Hydrogen Produced (kg)} = \text{Hydrogen Production Rate (kg/h)} \times \text{Operating Time (h)}$$

3. **Energy Used per kg of Hydrogen ($kWh/kg$):**
   $$\text{Energy Used per kg H₂ (kWh/kg } H_2\text{)} = \frac{\text{Energy Used (kWh)}}{\text{Hydrogen Produced (kg)}}$$

---

## 📂 Project Structure
```text
green_hydrogen_monitor/
│
├── app.py                  # Main Flask routes and SQLite database integration
├── database.db             # Generated SQLite database file
├── requirements.txt        # Project dependencies (Flask)
├── README.md               # Setup and project documentation
│
├── templates/              # HTML Templates
│   ├── base.html           # Unified sidebar navigation layout
│   ├── dashboard.html      # Latest status metrics and Chart.js trend graphs
│   ├── add_data.html       # Data entry form with live JS preview calculations
│   ├── analysis.html       # Averages, cumulative stats, and trend observations
│   ├── history.html        # Tabular historical database view
│   └── about.html          # Scientific concepts and formula descriptions
│
└── static/
    ├── css/
    │   └── style.css       # Clean, modern clean-energy themed styles
    └── js/
        └── script.js       # Script initializing Chart.js datasets
```

---

## 📋 Database Structure
A single SQLite table named `production_data` is used.
- `id` (INTEGER, Primary Key)
- `timestamp` (TEXT)
- `power` (REAL)
- `operating_time` (REAL)
- `energy_consumed` (REAL)
- `temperature` (REAL)
- `pressure` (REAL)
- `hydrogen_rate` (REAL)
- `hydrogen_produced` (REAL)
- `specific_energy_consumption` (REAL)

---

## 🚀 Setup & Execution Instructions

Follow these simple steps to set up and run the project locally on your machine:

### 1. Prerequisite
Ensure you have **Python 3.x** installed. You can check your version in a terminal using:
```bash
python --version
```

### 2. Install Dependencies
Navigate to the root directory `green_hydrogen_monitor` and install the package dependencies listed in `requirements.txt`:
```bash
pip install -r requirements.txt
```

### 3. Run the Flask Web Application
Execute the main script to initialize the SQLite database and start the local development server:
```bash
python app.py
```

### 4. Open in Browser
Once the server starts up, open your web browser and navigate to:
```text
http://127.0.0.1:5000/
```

---

## 💡 How to Use the Web System
1. **Load Demo Data:** Click the **🔄 Load Demo Data** button in the header bar or the Dashboard placeholder to seed the database with realistic historic run data.
2. **Dashboard:** Look at the visual card metrics showing the status of the latest run, along with the interactive graphs showcasing production and efficiency over time.
3. **Add Data:** Navigate to **Add Data**, fill in parameters (Power Used, Operating Time, Operating Temp, Operating Pressure, H2 rate). Check out the **Live Preview** block calculations that refresh as you type! Submit the form to commit it to the SQLite database.
4. **Analysis:** Review cumulative totals (overall electricity used and H2 produced) along with academic checks indicating if temperature and pressure were optimal.
5. **History:** Open the log table to browse all recorded history entries chronologically.

---

## ⚠️ Project Limitations
- **No Physical Sensors:** This is a software-only representation. There is no physical connection to real-time industrial PLC controllers or IoT microcontrollers.
- **Configurable Thresholds:** Range boundaries (e.g. Temperature 60°C - 80°C) are defined purely for project demonstrations and do not represent hard industrial machine limits.
