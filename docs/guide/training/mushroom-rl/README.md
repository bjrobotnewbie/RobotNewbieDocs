# mushroom-rl

Python 库，用于强化学习。

## 项目链接

- GitHub: <https://github.com/MushroomRL/mushroom-rl>

## 项目概述

**********
MushroomRL

**********
.. image:: https://github.com/MushroomRL/mushroom-rl/actions/workflows/continuous_integration.yml/badge.svg?branch=dev

:target: https://github.com/MushroomRL/mushroom-rl/actions/workflows/continuous_integration.yml

:alt: Continuous Integration

**What is MushroomRL**

==================

MushroomRL is a Python Reinforcement Learning (RL) library whose modularity allows

to easily use well-known Python libraries for tensor computation (e.g. PyTorch,

Tensorflow) and RL benchmarks (e.g. OpenAI Gym, PyBullet, Deepmind Control Suite).
It allows to perform RL experiments in a simple way providing classical RL algorithms

(e.g. Q-Learning, SARSA, FQI), and deep RL algorithms (e.g. DQN, DDPG, SAC, TD3,

TRPO, PPO).
`Full documentation and tutorials available here <http://mushroomrl.readthedocs.io/en/latest/>`_.
**Installation**

============

**You can do a minimal installation of ``MushroomRL`` with:**

.. code:: shell

**pip3 install mushroom_rl**

**Installing everything**

---------------------
``MushroomRL`` contains also some optional components e.g., support for ``OpenAI Gym``

environments, Atari 2600 games from the ``Arcade Learning Environment``, and the support

for physics simulators such as ``Pybullet`` and ``MuJoCo``.
Support for these classes is not enabled by default.
**To install the whole set of features, you will need additional packages installed.**

**You can install everything by running:**

.. code:: shell

**pip3 install mushroom_rl[all]**

**This will install every dependency of MushroomRL, except the Plots dependency.**

**For ubuntu>20.04, you may need to install pygame and gym dependencies:**

.. code:: shell

**sudo apt -y install libsdl-image1.2-dev libsdl-mixer1.2-dev libsdl-ttf2.0-dev \**

libsdl1.2-dev libsmpeg-dev libportmidi-dev ffmpeg libswscale-dev \

libavformat-dev libavcodec-dev swig

**Notice that you still need to install some of these dependencies for different operating systems, e.g. swig for macOS**

**Below is the code that you need to run to install the Plots dependencies:**

.. code:: shell

**sudo apt -y install python3-pyqt5**

**pip3 install mushroom_rl[plots]**

**You might need to install external dependencies first. For more information about mujoco-py**

**installation follow the instructions on the `project page <https://github.com/openai/mujoco-py>`_**

WARNING! when using conda, there may be issues with QT. You can fix them by adding the following lines to the code, replacing ``<conda_base_path>`` with the path to your conda distribution and ``<env_name>`` with the name of the conda environment you are using:
.. code:: python

import os

os.environ['QT_QPA_PLATFORM_PLUGIN_PATH'] = '<conda_base_path>/envs/<env_name>/bin/platforms'

**To use dm_control MushroomRL interface, install ``dm_control`` following the instruction that can**
