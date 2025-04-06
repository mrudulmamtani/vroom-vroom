# **Aerodynamic Optimization Using Xcos**

This project implements a control system for aerodynamic optimization of a vehicle's spoiler angle based on velocity and yaw inputs. The system is modeled and simulated using **Scilab Xcos**, with blocks like PID controllers, transfer functions, and inputs/outputs.
<video src="https://github.com/mrudulmamtani/vroom-vroom/blob/main/vroomvroomvid.mp4" controls>
</video>

## **Project Overview**

The goal is to optimize the spoiler angle dynamically to reduce drag and improve vehicle stability. The system uses:

- **Inputs**: Vehicle velocity and yaw angle.
- **Controller**: A PID controller for real-time spoiler adjustment.
- **Actuator Dynamics**: Modeled using a second-order transfer function.
- **Output**: Spoiler angle visualized using a scope.

---

## **Features**

- Real-time simulation of aerodynamic optimization.
- Adjustable PID parameters for tuning.
- Transfer function modeling of actuator dynamics.
- Visual output of the spoiler angle response.

---

## **Requirements**

To run this project, you need:

1. **Scilab** (version 6.1 or later)
2. **Xcos** (built into Scilab)
3. A Windows 11 or Linux environment (WSL for OpenFOAM if needed)

---

## **Setup Instructions**

1. Install Scilab from [Scilab Official Website](https://www.scilab.org/download).
2. Open Scilab and initialize Xcos:

```scilab
loadXcosLibs();
xcos();
```

3. Clone this repository:

```bash
git clone https://github.com/mrudulmamtani/aerodynamic-optimization-xcos.git
cd aerodynamic-optimization-xcos
```

4. Open the `.zcos` file in Xcos:
    - Launch Xcos from Scilab.
    - Go to **File > Open**, then select `spoiler_control.zcos`.

---

## **How to Run the Simulation**

1. Open the `spoiler_control.zcos` file in Xcos.
2. Configure simulation parameters:
    - Go to **Simulation > Setup**.
    - Set the final time to `30 seconds`.
    - Choose solver as `Runge-Kutta`.
3. Click the green "Play" button in the toolbar to start the simulation.
4. Observe the output on the scope block.

---

## **System Design**

### Block Diagram Components

| Block | Purpose |
| :-- | :-- |
| Input | Accepts velocity and yaw values |
| Expression | Computes reference spoiler angle |
| PID | Adjusts spoiler angle dynamically |
| CLR | Models actuator dynamics (second-order) |
| Scope | Displays the resulting spoiler angle |

### Key Parameters

- **PID Gains**:
    - Proportional (Kp): `2.5`
    - Integral (Ki): `0.1`
    - Derivative (Kd): `0.05`
    - Filter Coefficient (N): `100`
- **Actuator Transfer Function**:
    - Numerator: `[^1]`
    - Denominator: `[0.5, 1.2, 1]`

---

## **Customization**

### Adjusting PID Parameters

Modify the PID block parameters in Xcos:

1. Double-click the PID block.
2. Set new values for Kp, Ki, Kd, or N.

### Changing Actuator Dynamics

Modify the CLR block transfer function:

1. Double-click the CLR block.
2. Update numerator/denominator coefficients.

---

## **Troubleshooting**

### Blank Xcos Screen

If you see a blank screen after running programmatic code:

- Ensure all blocks are properly initialized in Scilab.
- Use manual creation in Xcos as an alternative.


### Simulation Errors

- Check block connections for mismatched input/output ports.
- Verify that all blocks are configured with correct parameters.

---

## **Contributing**

Contributions are welcome! Feel free to fork this repository, make improvements, and submit pull requests.

---

## **License**

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

---

## **Acknowledgments**

Special thanks to Scilab's open-source community for providing tools like Xcos for dynamic system modeling.

---

