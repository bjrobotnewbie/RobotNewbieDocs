# GAZEBO

- [documentation](https://gazebosim.org/docs/latest/getstarted/)

## Summary

**Gazebo** is an open-source, high-fidelity 3D robotics simulator originally released in 2002, now maintained by Open Robotics as part of the Gazebo Sim (modern Ignition) project. It is widely regarded as the **de facto simulation platform for ROS** (Robot Operating System), designed to accurately and efficiently simulate robots, sensors, and environments in complex indoor and outdoor scenarios.

At its core, Gazebo supports **multiple physics engines**—including ODE (default), Bullet, Simbody, and DART—enabling realistic rigid-body dynamics, collision detection, and physical interactions between objects. It features **advanced 3D rendering** (via OGRE) with high-quality lighting, shadows, and textures, paired with an extensive library of configurable sensors such as RGB-D cameras, LiDARs, IMUs, and contact/force sensors, all with customizable noise models.

Built with a **modular, plugin-based architecture**, Gazebo uses the **Simulation Description Format (SDF)** to define worlds, robots, and objects, while also supporting URDF for ROS compatibility. It provides both a **Qt-based graphical interface (gzclient)** for visualization and interactive editing, and a **headless server (gzserver)** for physics computation and sensor data generation, making it suitable for large-scale, parallel, and cloud-based simulations.

Deeply integrated with ROS 1/2, Gazebo enables seamless **sim-to-real transfer** by mirroring real-world sensor data and robot behavior. It is extensively used in research, education, and industry for **algorithm testing, robot design validation, synthetic data generation, and continuous integration** workflows. After over two decades of development, the modern Gazebo Sim (formerly Ignition) continues to evolve with improved performance, modularity, and compatibility, solidifying its role as a foundational tool in robotics development.

