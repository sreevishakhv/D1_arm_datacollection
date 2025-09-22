# Data Collection and Processing Pipeline

This project provides a pipeline for collecting and processing data for vision-based tasks using the Unitree Go2 robot and D1 arm. Follow the steps below to set up your environment and collect your dataset.

## 1. Install Dependencies

### Unitree Go2 SDK 2
- Download and install the Unitree Go2 SDK 2 from the official Unitree Robotics website.
- Follow the official installation instructions for your platform.

### D1 SDK
- Install the D1 SDK as required for controlling the D1 arm.
- You may have received an executable, but a proper installation is recommended for full control.
- Refer to the D1 SDK documentation for installation steps.

## 2. Data Collection

### Collect Data with Joystick
- Run `collect_with_joystick.py` to collect data using a joystick interface.
- This will generate a dataset (e.g., a JSON file) with recorded actions.

```bash
python3 collect_with_joystick.py
```

## 3. Data Interpolation
- Use `interpolate.py` to interpolate the collected data for smoother trajectories or denser sampling.

```bash
python3 interpolate.py
```

## 4. Apply Forward Kinematics
- Use `apply_forward_kinematics.py` to process the interpolated data and compute the forward kinematics.
- This step will save the actions part of the dataset.

```bash
python3 apply_forward_kinematics.py
```

## 5. Collect Image Data
- Use `collect_with_image.py` to collect the image part of the dataset.
- This will save images corresponding to the actions in your dataset.

```bash
python3 collect_with_image.py
```

## 6. Build Vision-Based Dataset
- After completing the above steps, you will have:
  - A JSON file with actions (from step 3)
  - Images (from step 5)
- Use these together as your vision-based dataset for further training or analysis.

---

**Note:**
- Ensure all SDKs and dependencies are properly installed and configured before running the scripts.
- Refer to the individual script files for additional arguments or configuration options.
