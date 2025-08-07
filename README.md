
## Description

The robotic arm consists of:
- 3 links (L1, L2, L3)
- 3 revolute joints (servo motors)
- Operates in a 2D plane (X-Y)

The purpose of this project is to calculate the end-effector's position and orientation given joint angles.

## Forward Kinematics

Given:
- Joint angles: `θ1`, `θ2`, `θ3` (in radians or degrees)
- Link lengths: `L1`, `L2`, `L3` (in any consistent unit)

The position of the end-effector (x, y) is calculated using:

x = L1 * cos(θ1) + L2 * cos(θ1 + θ2) + L3 * cos(θ1 + θ2 + θ3)
y = L1 * sin(θ1) + L2 * sin(θ1 + θ2) + L3 * sin(θ1 + θ2 + θ3)

Orientation of the end-effector:

φ = θ1 + θ2 + θ3

## Requirements

- Python (optional for simulation)
- NumPy (for trigonometric operations)
- Matplotlib (for visualizing arm movement)

## Example (Python)

```python
import numpy as np

# Define lengths
L1 = 10
L2 = 8
L3 = 5

# Define joint angles in radians
theta1 = np.radians(30)
theta2 = np.radians(45)
theta3 = np.radians(-20)

# Compute (x, y)
x = L1*np.cos(theta1) + L2*np.cos(theta1 + theta2) + L3*np.cos(theta1 + theta2 + theta3)
y = L1*np.sin(theta1) + L2*np.sin(theta1 + theta2) + L3*np.sin(theta1 + theta2 + theta3)

# Compute orientation
phi = np.degrees(theta1 + theta2 + theta3)

print(f"End-Effector Position: ({x:.2f}, {y:.2f})")
print(f"End-Effector Orientation: {phi:.2f} degrees")
```
## Result

<img width="1849" height="615" alt="Screenshot 2025-08-07 032829" src="https://github.com/user-attachments/assets/d6c7fd16-7e25-40c2-98c0-066d396dc801" />
