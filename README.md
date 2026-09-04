# INTELLISORT

### PLC-Based Conveyor Color Sorting and Counting System

INTELLISORT is a simulation-based industrial automation project developed using **CODESYS V3.5 SP22**.

The system simulates a conveyor-based process in which products are detected, identified by color, sorted into their corresponding categories, and counted automatically.

This project demonstrates the practical application of **PLC programming, Ladder Diagram, Structured Text, HMI visualization, rising-edge detection, counters, sensor logic, and emergency-stop control**.

---

## Project Overview

INTELLISORT combines two main functions:

1. **Color Sorting** — identifies products and activates the corresponding sorting output.
2. **Product Counting** — counts each successfully confirmed red, green, and blue product separately.

When a product is detected, its color is identified. The corresponding sorter output is activated. After sorting confirmation, the relevant counter increases and the sorting state is reset.

The project was developed as a learning and simulation project to understand the basic workflow of an industrial automation system.

---

## Main Features

- Conveyor motor control
- Product detection
- Red, green, and blue color identification
- Unknown/other product detection
- Individual color sorting outputs
- Separate counters for each color
- HMI-based control and monitoring
- Simulation-only control section
- Sort confirmation using rising-edge detection
- Emergency-stop and reset logic
- PLC programming using LD and ST
- CODESYS visualization

---

## System Working

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
Relevant Counter Increased
  ↓
Sorter Reset
  ↓
System Ready for Next Product
```

---

## Sorting and Counting Logic

| Product Type | Sorting Output | Counter |
|---|---|---|
| Red | `RedSorter` | `RedCount` |
| Green | `GreenSorter` | `GreenCount` |
| Blue | `BlueSorter` | `BlueCount` |
| Other/Unknown | No color sorter | No color counter |

Each color has its own counter so that products are counted independently.

The counter is increased only when the corresponding product has been confirmed as sorted.

---

## Main Components

### PLC

The PLC executes the control logic and processes the sensor inputs.

### Conveyor Motor

The conveyor transports products through the sorting and counting process.

### Product Detection

The product detection input identifies when a product is present.

### Color Sensors

The simulation uses separate inputs for:

- Red
- Green
- Blue
- Other/Unknown

### Sorting Outputs

The corresponding sorter output is activated according to the detected color.

### Sort Confirmation

The sort confirmation signal confirms the sorting operation and triggers the relevant counter increment.

### Product Counters

Separate counters record the number of red, green, and blue products sorted.

### HMI

The HMI provides operator controls, process indications, simulation buttons, sorter status, and product counters.

---

## Software Used

- **CODESYS V3.5 SP22**
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
| `GVL.EmergencyStop` | Emergency-stop input |
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
- Product detection indication
- Color sensor indication
- Red, green, and blue sorter indications
- Individual product counters
- Simulation-only color selection buttons
- Product Detect and Sort Confirm controls
- Run and Alarm status indications

The HMI allows the operator to monitor both the **sorting process** and the **number of products sorted**.

---

## HMI Screenshots

### Main HMI

The main HMI provides the control panel, process visualization, simulation controls, and product counters.

![INTELLISORT Main HMI](Images/hmi.png)

### Running State

The running state shows the conveyor operating and the sorting and counting process during simulation.

![INTELLISORT Running State](Images/running.png)

### Alarm State

The alarm state shows the HMI response when the alarm condition is active.

![INTELLISORT Alarm State](Images/alarm%20state.png)

---

## Simulation Procedure

To test a red product:

1. Reset the simulation.
2. Start the conveyor.
3. Activate `ProductDetect`.
4. Select the red color.
5. Activate `SortConfirm`.
6. Observe the red sorter.
7. Verify that `RedCount` increases.
8. Reset the simulation before testing the next product.

The same procedure can be followed for green and blue products.

> The simulation controls imitate sensor signals because physical sensors and actuators are not connected.

---

## Safety

The project includes emergency-stop and reset logic.

When the emergency stop is activated, the controlled operation is stopped. The reset input is used to clear the emergency-stop condition.

> This project is a simulation and is not intended for direct use on industrial machinery without proper safety validation and hardware implementation.

---

## Project Structure

```text
INTELLISORT/
│
├── README.md
├── INTELLISORT.project
│
└── Images/
    ├── hmi.png
    ├── running.png
    └── alarm state.png
```

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
- Combining sorting and counting functions in a PLC system

---

## Author

**Saurabh Verma**

Electrical Engineering Student  
Interested in PLC Programming, Industrial Automation, and Control Systems.

---

## License

This project is intended for educational and learning purposes.
