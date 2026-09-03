# INTELLISORT

### PLC-Based Conveyor Color Sorting System

INTELLISORT is a simulation-based industrial automation project developed using **CODESYS**. The system detects products, identifies their colors, and controls the corresponding sorting mechanism using PLC logic.

The project demonstrates the practical use of **Ladder Diagram, Structured Text, HMI visualization, counters, sensor inputs, and emergency-stop logic**.

---

## Project Overview

In industrial production lines, products often need to be identified and sorted automatically according to their characteristics.

INTELLISORT simulates this process using a conveyor system. When a product is detected, its color is identified, and the corresponding sorter is activated. After sorting confirmation, the relevant product counter is increased.

The project is designed as a learning and simulation project for understanding PLC-based automation systems.

---

## Features

- Conveyor motor control
- Product detection
- Red, green, and blue color identification
- Unknown/other product detection
- Individual sorting outputs
- Separate counters for each color
- HMI-based control and monitoring
- Simulation controls for testing
- Sort confirmation using rising-edge detection
- Emergency stop and reset logic
- PLC programming using LD and ST

---

## System Working

The basic operating sequence is:

```text
Start
  ↓
Conveyor Runs
  ↓
Product Detected
  ↓
Color Identified
  ↓
Corresponding Sorter Activated
  ↓
Sort Confirmation
  ↓
Product Counter Increased
  ↓
Sorter Reset
  ↓
System Ready for Next Product
```

---

## Color Sorting Logic

| Product Color | Sorting Output | Counter |
|---|---|---|
| Red | RedSorter | RedCount |
| Green | GreenSorter | GreenCount |
| Blue | BlueSorter | BlueCount |
| Other/Unknown | No color sorter | No color counter |

The system uses separate counter instances so that each color is counted independently.

---

## Main Components

### PLC

The PLC executes the control logic and processes the sensor inputs.

### Conveyor Motor

The conveyor transports products through the sorting process.

### Product Detection Sensor

Detects the presence of a product on the conveyor.

### Color Sensors

The simulation uses separate inputs for red, green, blue, and unknown products.

### Sorting Outputs

The corresponding sorter output is activated according to the detected color.

### Sort Confirmation

Confirms that the sorting operation has occurred and triggers the counter increment.

### HMI

The HMI provides operator controls, status indications, simulation buttons, and product counters.

---

## Software Used

- **CODESYS**
- **Ladder Diagram (LD)**
- **Structured Text (ST)**
- **CODESYS Visualization**

---

## Input and Output Overview

### Inputs

| Variable | Description |
|---|---|
| `GVL.Start` | Starts the system |
| `GVL.Stop` | Stops the system |
| `GVL.EmergencyStop` | Emergency stop input |
| `GVL.EStopReset` | Resets the emergency-stop condition |
| `GVL.ProductDetect` | Detects a product |
| `GVL.SortConfirm` | Confirms sorting |
| `GVL.ColorRed` | Red color detection |
| `GVL.ColorGreen` | Green color detection |
| `GVL.ColorBlue` | Blue color detection |
| `GVL.Unknown` | Unknown/other product detection |

### Outputs

| Variable | Description |
|---|---|
| `ConveyorMotor` | Controls conveyor movement |
| `RedSorter` | Activates red sorting mechanism |
| `GreenSorter` | Activates green sorting mechanism |
| `BlueSorter` | Activates blue sorting mechanism |

### Counters

| Variable | Description |
|---|---|
| `RedCount` | Number of red products sorted |
| `GreenCount` | Number of green products sorted |
| `BlueCount` | Number of blue products sorted |

---

## HMI

The HMI includes:

- Start and Stop controls
- Emergency Stop and Reset controls
- Conveyor and sorter status indicators
- Red, green, and blue product counters
- Simulation-only color selection buttons
- Product Detect control
- Sort Confirm control

The simulation section allows the system to be tested without physical sensors or actuators.

---

## Simulation Procedure

To test a red product:

1. Reset the simulation.
2. Start the conveyor.
3. Activate `ProductDetect`.
4. Select the red color.
5. Activate `SortConfirm`.
6. Observe the red sorter and red counter.
7. Reset the simulation before testing the next product.

The same procedure can be followed for green and blue products.

---

## Safety

The project includes emergency-stop and reset logic.

When the emergency stop is activated, the system is designed to stop the controlled operation. The reset input is used to clear the emergency-stop condition.

> This project is a simulation and is not intended for direct use on industrial machinery without proper safety validation and hardware implementation.

---

## Project Structure

```text
INTELLISORT/
│
├── README.md
│
├── PLC/
│   └── INTELLISORT.project
│
└── Images/
    ├── main-hmi.png
    ├── simulation.png
    ├── red-sorting.png
    ├── green-blue-sorting.png
    └── plc-logic.png
```

---

## Project Screenshots

### Main HMI

_Add your main HMI screenshot here._

### Simulation Section

_Add your simulation screenshot here._

### Sorting and Counters

_Add your sorting screenshot here._

### PLC Logic

_Add your ladder logic screenshot here._

---

## Learning Outcomes

Through this project, I learned:

- PLC project planning
- I/O mapping
- Ladder Diagram programming
- Structured Text programming
- HMI design in CODESYS
- Rising-edge detection
- Counter implementation
- Sensor-based control logic
- Emergency-stop handling
- PLC simulation and testing
- Basic industrial automation workflow

---

## Future Improvements

- Integration with real color sensors
- Integration with physical actuators
- Conveyor speed control
- Automatic product spacing
- Fault and alarm management
- Data logging
- Production statistics
- Industrial communication
- Improved HMI diagnostics

---

## Author

**Saurabh Verma**

Electrical Engineering Student  
Interested in PLC Programming, Industrial Automation, and Control Systems.

---

## License

This project is intended for educational and learning purposes.
