# AI-Assignment-PEAS
Intelligent Agent Specification

## Project Overview
This repository contains the first assignment for the CS301 Artificial Intelligence course. The objective is to apply Russell & Norvig's agent frameworks (Chapter 2) to a real-world system.

## Chosen System: Agricultural Monitoring Drone
An autonomous agent designed for precision agriculture, specifically for early-stage crop disease detection.

### Task 1: PEAS Specification
- **Performance Measure**: Detection Accuracy (F1-score), Coverage Efficiency (Area/Battery), Response Latency, and Flight Safety.
- **Environment**: Rural farms, unpredictable weather, varying light, and physical obstacles.
- **Actuators**: Brushless motors (rotors), 3-axis gimbal stabilizer, wireless transmitter, and electronic speed controllers.
- **Sensors**: Multispectral cameras (NIR/Red-edge), RTK-GPS (centimeter-level), ultrasonic altimeters, and optical flow sensors.

### Task 2: Environment Classification
- **Partially Observable**: Sensors cannot see through objects or detect subsurface soil conditions.
- **Single-agent**: The drone operates independently in the field.
- **Stochastic**: Outcomes are uncertain due to environmental noise like wind and light changes.
- **Sequential**: Past movements and battery consumption dictate future actions.
- **Dynamic**: The world changes (moving obstacles/weather) while the agent deliberates.
- **Continuous**: Actions (speed/thrust) and perceptions occur in a real-valued space.

### Task 3: Critical Analysis
**1. Technical Challenge:** The **Stochastic** nature is most difficult because the AI must filter environmental noise (varying light/wind) to maintain reliable detection and flight stability.

**2. Utility Function:** `U = w1(Speed) + w2(Precision)`
By doubling the weight of Precision, the agent slows its flight velocity and lowers its altitude to maximize image resolution and detection confidence, sacrificing overall field coverage speed.