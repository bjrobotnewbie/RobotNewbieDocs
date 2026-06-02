# Habitat-Sim

- [documentation](https://aihabitat.org/docs/habitat-sim/)

## Summary

**Habitat-Sim** is an open-source, high-performance 3D physics simulator developed by Meta AI Research (formerly Facebook Research), tailored specifically for **embodied AI** and robotics research. Built with C++ for core performance and Python for usability, it prioritizes simulation speed while maintaining robust physical realism, making it ideal for training and testing intelligent agents in complex virtual environments.

The simulator supports a wide range of 3D environments, including scanned indoor/outdoor datasets (e.g., HM3D, Matterport3D, Gibson, Replica) and CAD-based scenes with articulated objects (e.g., ReplicaCAD, YCB objects). It integrates the **Bullet physics engine** for accurate rigid-body dynamics and collision detection, and offers configurable sensors such as RGB-D cameras and egomotion trackers. Agents, including mobile manipulators (Fetch), fixed-base arms (Franka), and quadrupeds, can be imported via URDF for flexible robot modeling.

A key strength is its **extreme efficiency**: single-threaded rendering reaches several thousand FPS, while multi-process GPU acceleration exceeds 10,000 FPS. It can simulate interactive tasks like object rearrangement at over 8,000 steps per second, enabling large-scale reinforcement learning and dataset generation. Habitat-Sim is typically used alongside **Habitat-Lab**, a modular library for defining embodied tasks (navigation, instruction following, manipulation) and end-to-end experiment workflows.

Widely adopted in academia and industry, Habitat-Sim drives research in sim-to-real transfer, robotic manipulation, and interactive AI, providing a fast, scalable, and realistic platform to advance embodied intelligence.
