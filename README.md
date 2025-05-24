# Cairo-Transportation-System-
System finds shortest paths in Cairo, integrating traffic, time, and cost.
Smart City Transportation Network Optimization Project
Overview
This project is a Jupyter notebook (Smart_City_Transportation_Network_Optimization_Project.ipynb) designed to optimize Cairo's transportation network using graph-based algorithms and traffic signal optimization. It integrates three key algorithms:

Kruskal’s Algorithm: Optimizes the road network by computing the Minimum Spanning Tree (MST).
A Algorithm*: Finds the optimal path for emergency vehicles, prioritizing speed and accessibility.
Dijkstra’s Algorithm: Calculates the shortest path considering traffic flow patterns.
Traffic Signal Optimization: Prioritizes green light timings at intersections based on traffic flow and emergency vehicle presence.

The project leverages data from CSV files representing Cairo’s neighborhoods, facilities, roads, bus routes, metro lines, traffic patterns, and public transportation demand to model and visualize the transportation network.
Purpose
The goal is to enhance Cairo’s transportation infrastructure by:

Optimizing road connectivity using MST.
Ensuring rapid transit for emergency vehicles.
Minimizing travel time for commuters by factoring in traffic conditions.
Optimizing traffic signal timings to reduce congestion, especially during peak hours or for emergency vehicles.

Dependencies
To run the notebook, install the following Python libraries:

networkx: For graph-based algorithms and network modeling.
matplotlib: For visualizing the transportation network.
pandas: For data manipulation and CSV file handling.
gradio: For creating an interactive web interface to run algorithms and view results.
numpy: For numerical computations (optional, depending on specific implementations).

You can install these dependencies using pip:
pip install networkx matplotlib pandas gradio numpy

Setup Instructions

Clone or Download the Project:

Ensure you have the Smart_City_Transportation_Network_Optimization_Project.ipynb file and the required CSV data files (listed below) in the same directory.


Prepare Data Files:The project requires the following CSV files:

current_bus_routes.csv: Bus route data.
current_metro_lines.csv: Metro line data.
existing_roads.csv: Road network data.
important_facilities.csv: Key facilities (e.g., airports, hospitals) with coordinates and types.
intersections.csv: Intersection data with connected roads.
neighborhoods_districts.csv: Neighborhood data with population and coordinates.
potential_new_roads1.csv: Proposed new roads.
public_transportation_demand.csv: Public transport demand data.
traffic_flow_patterns.csv: Traffic flow data by time slot.

Ensure these files are correctly formatted and available in the working directory.

Set Up Environment:

Use a Python environment (e.g., Python 3.11 as indicated in the notebook).
Install dependencies as listed above.
If running on Google Colab, ensure the notebook is uploaded to Colab, and use the file upload functionality to load CSV files.


Run the Notebook:

Open the notebook in Jupyter or Google Colab.
Execute cells sequentially to load data, process it, and launch the Gradio interface.



Usage

Run the Notebook:

Execute the first cell to import libraries (networkx, matplotlib, pandas).
Upload CSV files using the file upload cell (Cell 2).
Process neighborhoods and facilities data (Cell 3) to create a unified node dataset.
Run the algorithm cell to initialize the transportation network and algorithms.
Launch the Gradio interface (Cell 4) to interact with the algorithms (Kruskal, A*, Dijkstra).
Use the traffic signal optimization cell (Cell 5) to analyze and optimize traffic signals.


Gradio Interface:

Cairo Transportation Network Optimizer:
Select an algorithm (Kruskal, A*, or Dijkstra) from the dropdown.
For A* and Dijkstra, choose start/end locations and a time slot (e.g., Morning, Afternoon).
Click “Run Algorithm” to view results and visualizations.
Use the “Quick Examples” section to test predefined scenarios.


Traffic Signal Optimization System:
Select the number of intersections (1–8) to optimize.
Choose a time slot (Morning, Afternoon, Evening, Night).
Indicate if an emergency vehicle (e.g., ambulance or police) is present and select its intersection.
Click “Analyze Intersections” to generate signal optimization tables, emergency adjustments, and analysis.
Download the results as a CSV file (traffic_signal_results.csv).




Outputs:

Visualizations: Network graphs showing MST, emergency paths, or shortest paths.
Tables: Traffic signal timings and emergency vehicle adjustments.
Analysis: Insights into optimal and suboptimal scenarios in Cairo’s context, with recommendations.



File Structure
Smart_City_Transportation_Network_Optimization/
├── Smart_City_Transportation_Network_Optimization_Project.ipynb
├── current_bus_routes.csv
├── current_metro_lines.csv
├── existing_roads.csv
├── important_facilities.csv
├── intersections.csv
├── neighborhoods_districts.csv
├── potential_new_roads1.csv
├── public_transportation_demand.csv
├── traffic_flow_patterns.csv
└── traffic_signal_results.csv (generated output)

Notes

The notebook assumes data files are correctly formatted with expected columns (e.g., ID, Name, X-coordinate, Y-coordinate, Type, Population for nodes; RoadID, Morning Peak(veh/h), etc., for traffic).
Missing values in coordinates or types are handled by filling with defaults (e.g., 0 for coordinates, “Unknown” for types).
Coordinates are scaled to a 0–100 range for visualization.
The traffic signal optimization uses a greedy approach, prioritizing intersections with higher traffic flow and allocating green times (30–150 seconds) proportionally, with emergency vehicles receiving 180 seconds.
The Gradio interface may require a public URL when running on Colab (automatically enabled with share=True).

Limitations

The greedy traffic signal optimization may be suboptimal for highly interconnected intersections or unpredictable driver behavior in Cairo.
Emergency vehicle prioritization may delay other routes during peak hours.
The notebook relies on static CSV data; real-time traffic data or smart camera integration could enhance accuracy.

Recommendations

Incorporate real-time traffic data or driver behavior analytics for better signal optimization.
Consider advanced algorithms (e.g., Reinforcement Learning) for complex scenarios.
Add smart camera systems to detect emergency vehicles automatically.

License
This project is licensed under the Apache License, Version 2.0. See the license notice in the file upload cell for details.
Contact
For questions or contributions, please contact the project maintainer or open an issue in the repository (if hosted).

