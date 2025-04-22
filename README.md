# BTP_project_6th-sem
# Intelligent TransPortation System for Emergency Vehicles
 Project Description
This project delivers a complete simulation-based Intelligent Transportation System (ITS) tailored to improve the mobility of emergency vehicles in congested urban environments.

Using SUMO (Simulation of Urban Mobility) and the Python TraCI API, the system simulates a dynamic environment of 800–1000 mixed vehicles—cars, buses, bikes, and emergency units—with realistic road infrastructure and actuated traffic lights.

The simulation intelligently responds to emergency situations using:

Proximity-based vehicle yielding

Real-time lane switching logic

Traffic light coordination

Shortest path routing using A* Algorithm

Q-Learning for dynamic policy optimization

1km-radius V2X-inspired communication to pre-clear the path for emergency vehicles

# Technologies Used
SUMO (Simulation of Urban MObility)

Python + TraCI (Traffic Control Interface)

XML (SUMO Network & Route Definitions)

Pandas (Traffic data analysis)

Q-Learning (Emergency path decision-making)

A* Algorithm (Optimal path detection)

Matplotlib / CSV / Custom logging

# System Architecture
+-------------+      +---------------------+      +-----------------+
| SUMO Engine | <--> | Python + TraCI API  | <--> | Emergency Logic |
+-------------+      +---------------------+      +-----------------+
       |                        |
       V                        V
 Vehicle Network         Data Logging & Analysis

SUMO provides the simulation engine with defined edges, nodes, and traffic lights.

Python TraCI controls vehicle behavior at each simulation step.

Emergency vehicles are dynamically spawned and initiate interaction.

Data is continuously logged for analysis and future RL training.

# Features
✅ Emergency Vehicle Detection

✅ Lane Clearing Logic (Left/Right Decisions)

✅ Dynamic Lane Switching

✅ Traffic Light Manipulation

✅ Realtime Visualization (SUMO-GUI)

✅ CSV Logging of vehicle speed, position, and lane info

✅ Q-Learning + A* Integration for Intelligent Path Planning

✅ 1 km Radius Informative Broadcast to Vehicles Ahead (V2X-like)

# How It Works
SUMO Network is loaded with preconfigured vehicle types, routes, and traffic light programs.

An emergency vehicle is injected at runtime using Python’s traci.vehicle.add() command.

At every simulation step:

Vehicle positions and speeds are tracked.

Nearby vehicles within 80 meters detect the emergency vehicle and switch lanes if safe.

Traffic flow is logged into a structured CSV.

Q-Learning determines the optimal strategy to reduce delay.

A* algorithm ensures the shortest path is chosen dynamically.

A "1km radius alert" is simulated where vehicles along the predicted path are notified to yield.

#  Sample Output Parameters
Step | Edge ID | Avg Speed | Vehicle Count | Occupancy | Traffic Flow
120 | -E10 | 12.5 m/s | 22 | 0.67 | 220 veh/hr

# How to Run the Simulation
# 1. Clone the repository
git clone https://github.com/your-username/emergency-traffic-sumo.git
cd emergency-traffic-sumo/src

# 2. Make sure SUMO is installed and in PATH
sumo-gui --version

# 3. Run the simulation (GUI or headless)
set gui=True && python main.py     # For GUI mode (Windows)
python main.py                     # Headless

# 4. Check data/ folder for simulation logs

# Future Scope (Already Implemented in Prototype)
✅ Q-Learning for traffic light control adaptation

✅ Shortest path detection using A*

✅ Broadcast-based vehicle reaction system (conceptually similar to V2X)

📡 Integration with real map data (OSM)

🧠 Integration with real-time GPS input for real-world deployment

# Developed By
Ayush Jain
B.Tech Student
The LNM Institute of Information Technology, Jaipur
Under guidance of Prof. Bharavi Mishra
