# **README for Energy Distribution Program**

---

## **Contents**

1. [Introduction](#introduction)  
2. [System Requirements and Installation](#system-requirements-and-installation)  
   2.1 [System Requirements](#system-requirements)  
   2.2 [Required Libraries](#required-libraries)  
   2.3 [Installation Process](#installation-process)  
3. [Program Features](#program-features)  
4. [Inputs, Outputs, and Core Calculations](#inputs-outputs-and-core-calculations)  
   4.1 [Inputs](#inputs)  
   4.2 [Outputs](#outputs)  
   4.3 [Core Calculations](#core-calculations)  
5. [Programming Techniques and Paradigms](#programming-techniques-and-paradigms)  
6. [Detailed Explanation of Algorithms](#detailed-explanation-of-algorithms)  
7. [Development Challenges and Solutions](#development-challenges-and-solutions)  
8. [Learning Reflections and Outcomes](#learning-reflections-and-outcomes)  
9. [Screenshots of the Development Process](#screenshots-of-the-development-process)  
10. [Software and Tools Used in Development](#software-and-tools-used-in-development)  
11. [References and Citations](#references-and-citations)

---

## **1. Introduction**

The **Energy Distribution Program** simulates renewable energy generation systems, including hydroelectric, solar, and wind power. It models energy outputs using user-defined parameters and environmental data, and then visualizes trends and provides financial analysis. The program is designed to demonstrate the practical application of various programming paradigms: **procedural**, **object-oriented**, and **event-driven** programming.

The program follows well-established principles from energy systems modeling (US Department of Energy, 2020; Fraunhofer Institute for Solar Energy Systems, 2020) and integrates these principles with robust, user-friendly software design. By simulating real-world scenarios and leveraging key algorithms, it offers a platform for exploring energy efficiency and cost savings.

---

## **2. System Requirements and Installation**

### **2.1 System Requirements**
- **Operating System**: Compatible with Windows, macOS, and Linux.
- **Python Version**: Python 3.9.1 or higher.

### **2.2 Required Libraries**
| **Library**       | **Purpose**                                                                                             |
|-------------------|---------------------------------------------------------------------------------------------------------|
| `random`          | Generates stochastic environmental variables (e.g., wind speed, solar radiation).                         |
| `datetime`        | Tracks system events and logs timestamps for simulations.                                                |
| `pandas`          | Handles and processes tabular data for financial analysis and energy outputs.                            |
| `matplotlib`      | Creates dynamic visualizations of energy trends and potential savings.                                   |
| `tkinter`         | Provides the user interface (GUI) for input and interaction.                                             |
| `logging`         | Captures runtime activities for debugging and diagnostics.                                              |

### **2.3 Installation Process**
1. **Install Python**:  
   Download Python 3.9.1 from [python.org](https://www.python.org/downloads/). Ensure Python is added to your system PATH.

2. **Install Required Libraries**:  
   Open a terminal and run:
   ```bash
   pip install pandas matplotlib
   ```

3. **Run the Program**:  
   Save the program as `energy_distribution.py` and execute it:
   ```bash
   python energy_distribution.py
   ```

---

## **3. Program Features**

1. **Energy Simulation**:  
   Simulates renewable energy outputs (hydroelectric, solar, wind) based on real-time environmental data.

2. **Dynamic Visualization**:  
   Uses `matplotlib` to generate real-time graphs of energy trends and financial savings.

3. **Financial Analysis**:  
   Calculates potential cost savings from using renewable energy, comparing grid usage costs with renewable energy outputs.

4. **Interactive GUI**:  
   Built with `tkinter`, the GUI allows users to input parameters, trigger simulations, and view results.

---

## **4. Inputs, Outputs, and Core Calculations**

### **4.1 Inputs**
- **User Inputs**:
  - Renewable energy capacities (e.g., wind turbine capacity in kW).
  - Grid electricity cost (e.g., in £/kWh).

- **Generated Inputs**:
  - Environmental data (e.g., wind speed, solar radiation, temperature) simulated using random distributions.

### **4.2 Outputs**
- **Text Reports**:
  - Energy generation, grid costs, and savings.
  
- **Graphical Outputs**:
  - Interactive plots of energy trends and financial analysis.

### **4.3 Core Calculations**

1. **Hydroelectric Power**:
   ```
   Power = Rainfall × Capacity Factor
   ```
   Models energy generation based on rainfall and system efficiency.

2. **Solar Power**:
   ```
   Power = Solar Radiation × Panel Efficiency × Solar Capacity
   ```

3. **Wind Power**:
   ```
   Power = 0.5 × Air Density × Turbine Efficiency × Wind Speed³ × Swept Area
   ```

4. **Cost Analysis**:
   ```
   Savings = Baseline Cost − Grid Usage Cost
   ```

---

## **5. Programming Techniques and Paradigms**

### **Procedural Programming**
Procedural programming is centered around step-by-step instructions that are executed in sequence. In this program, procedural programming is used for the core energy calculations, where each function performs specific tasks in a linear order.

#### **Advantages**:
- **Simplicity**: Making program easier to understand and implement.
- **Efficiency**: Well-suited for tasks with a clear sequence of steps.

#### **Disadvantages**:
- **Scalability**: As the program grows, procedural code can become harder to maintain and extend.
- **Reusability**: Procedures are often tightly coupled to the program, making code reuse difficult.

#### **Example**:
The calculation of solar power:
```python
def simulate_solar_power(solar_radiation, solar_capacity, panel_efficiency):
    return solar_radiation * solar_capacity * panel_efficiency
```

### **Object-Oriented Programming (OOP)**
OOP is used to organize the program into objects that represent different entities (e.g., energy systems, GUI elements). It allows for modular, reusable, and scalable code by encapsulating related data and behavior into classes.

#### **Advantages**:
- **Modularity**: Code is prepared into self-contained units (classes), making it easier to manage and expand.
- **Reusability**: Classes and objects can be reused across different parts of the program.

#### **Disadvantages**:
- **Complexity**: Can increase unnecessary complexity of the program, especially for small programs.
- **Memory Usage**: OOP can result in a higher memory consumption due to the creation of objects.

#### **Example**:
A class representing an energy system:
```python
class EnergySystem:
    def __init__(self, capacity, efficiency):
        self.capacity = capacity
        self.efficiency = efficiency

    def calculate_output(self):
        return self.capacity * self.efficiency
```

### **Event-Driven Programming**
Event driven programming is used to create interactive applications that responds to user actions, such as clicks or key presses. In this program the GUI is event driven, where events like button clicks trigger actions like running simulations and displaying results.
#### **Advantages**:
- **User Interaction**: Good for applications where user input drives the program.
- **Responsiveness**: Can provide real-time updates to the user.

#### **Disadvantages**:
- **Complexity**: Events and interactions can get unnecessary in big applications
- **Performance**: Event driven programs can become slow if not optimised.

#### **Example**:
In the GUI, a button click event triggers the simulation:
```python
def on_button_click():
    simulate_energy_output()
```

---

## **6. Detailed Explanation of Algorithms**

### **Weather Simulation Algorithm**
The weather simulation algorithm generates random environmental conditions to model real-world variability:
```python
def simulate_weather():
    temperature = random.uniform(15, 35)  # Temperature in Celsius
    wind_speed = random.uniform(0, 20)   # Wind speed in m/s
    solar_radiation = random.uniform(200, 1000)  # Solar radiation in W/m²
    return temperature, wind_speed, solar_radiation
```

### **Energy Calculation Algorithms**
- **Hydroelectric Power**:
  ```python
  def simulate_hydroelectricity(rainfall, hydro_capacity):
      return rainfall * hydro_capacity
  ```

- **Solar Power**:
  ```python
  def simulate_solar_power(solar_radiation, solar_capacity, panel_efficiency):
      return solar_radiation * solar_capacity * panel_efficiency
  ```

- **Wind Power**:
  ```python
  def simulate_wind_power(wind_speed, wind_capacity, turbine_efficiency):
      return wind_speed ** 3 * wind_capacity * turbine_efficiency
  ```

### **Cost and Savings Analysis Algorithm**
```python
def calculate_savings(grid

_usage, grid_cost, baseline_cost):
    grid_usage_cost = grid_usage * grid_cost
    return baseline_cost - grid_usage_cost
```

---

## **7. Development Challenges and Solutions**

### **Debugging Process**
- **Breakpoints**: Visual Studio Code’s debugger has been used to set breakpoints and to check variables during runtime. This has helped to identify issues with energy calculation issues and faults.
- **Logging**: The `logging` library was used to track the flow of the program and detect any runtime issues, particularly with a issue like user input handling and the event-driven parts of the GUI.

### **Problems Encountered and Solutions**
| **Issue**                  | **Solution**                                                                              |
|----------------------------|---------------------------------------------------------------------------------------------|
| Errors in energy calculations | Validated calculations against industry standards, like those provided by the US Department of Energy. |
| GUI freezing                | Introduced threading to handle long-running tasks asynchronously.                          |
| Invalid user inputs         | Implemented input validation functions to ensure all inputs were correct before executing calculations. |

---

## **8. Learning Reflections and Outcomes**

### **Key Reflections**
- Mastered the integration of multiple programming paradigms (procedural, object-oriented, event-driven) to solve complex real-world problems.
- Gained a deeper understanding of renewable energy systems and how algorithmic design can be used to simulate and analyze energy generation.

---

## **9. Screenshots of the Development Process**

### **1. User Interface Design**  
<img width="1512" alt="Screenshot 2024-12-06 at 02 18 05" src="https://github.com/user-attachments/assets/dc07a893-f47b-497e-9e17-90ef9163b819">
<img width="1512" alt="Screenshot 2024-12-06 at 02 18 26" src="https://github.com/user-attachments/assets/accb55a2-7b46-42ec-80bb-cd772d3f3f66">


### **2. Debugging Process**  
![Debugging Screenshot](path_to_debugging_screenshot.png)

### **3. Running Simulation**  
<img width="1512" alt="Screenshot 2024-12-06 at 10 06 30" src="https://github.com/user-attachments/assets/c87ef939-54c1-45ff-9828-8799f81e97f2">

<img width="1512" alt="Screenshot 2024-12-06 at 10 07 22" src="https://github.com/user-attachments/assets/3ea02157-3d17-45ed-a328-f5461f1c9039">

---

## **10. Software and Tools Used in Development**

- **Python 3.9.1**: Chosen for its extensive library support and ease of integration with scientific computation tools (Python Software Foundation, 2023).
- **Visual Studio Code**: The IDE of choice for its excellent debugging tools and support for Python development (Microsoft Corporation, 2023).

---

## **11. References**

Fraunhofer Institute for Solar Energy Systems (2020) *Photovoltaic technology basics*. Available at: https://www.ise.fraunhofer.de/ (Accessed: 3 December 2024).

Hunter, J.D. (2007) ‘Matplotlib: A 2D graphics environment’, *Computing in Science & Engineering*, 9(3), pp. 90–95.

International Renewable Energy Agency (2021) *Renewable energy technologies and grid integration*. Available at: https://www.irena.org/ (Accessed: 1 December 2024).

Knuth, D.E. (1997) *The art of computer programming, Volume 1: Fundamental algorithms*. Addison-Wesley.

McKinney, W. (2011) *Python for data analysis*. O’Reilly Media.

Microsoft Corporation (2023) *Visual Studio Code*. Available at: https://code.visualstudio.com/ (Accessed: 28 November 2024).

Python Software Foundation (2023) *Python programming language*. Available at: https://www.python.org/ (Accessed: 4 December 2024).

US Department of Energy (2020) *Hydropower basics*. Available at: https://www.energy.gov/ (Accessed: 4 December 2024).
