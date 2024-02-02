<!-- Badges: -->
[![License](https://img.shields.io/github/license/ShisheerKaushik24/Quantum_projects.svg?logo=CreativeCommons&style=flat-square)](https://github.com/ShisheerKaushik24/Quantum_projects/blob/master/LICENSE)
[![Contributions](https://img.shields.io/badge/contributions-welcome-orange?style=flat-square)](https://github.com/ShisheerKaushik24/Quantum_projects/pulls)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://github.com/ShisheerKaushik24/Quantum_projects/graphs/commit-activity)

<!-- Logo: -->
<div align="center">
  <a href="https://github.com/ShisheerKaushik24/Quantum_projects"><img src="https://github.com/ShisheerKaushik24/Quantum_projects/blob/master/asset/featured.png" height="300" width="550" /></a>
</div>

*<p align="center"><small>Source: IBM Quantum</small></p>*

<!-- Title: -->
<div align="center">
  <h1> <a href="https://github.com/ShisheerKaushik24/Quantum_projects"> Quantum Computing Projects </a></h1>
  <h2> All my Quantum Computing related projects
</div>
<br>
  
<!-- Author: -->
<div align="center">
  <b>Developer: <a target="_blank" href="https://github.com/ShisheerKaushik24">¹Shisheer S Kaushik</a></b>
<br>
</div>


## Description:
This repository contains a collection of my projects related to quantum computing. These projects cover various aspects of quantum computing, such as quantum algorithms, quantum programming, quantum simulation, and quantum hardware.

## List of Projects:</br>
The repository contains the following projects:</br>

1. [Android Malware Detection using VQC:](./android-malware-detection-using-vqc) 
   - Description: A Variational Quatum Classifier Model based project.

2. [Quantum QR-Code Generator](./QR-code-generator) 
   - Description: This project is based on Bernstein Vazirani Algorithm.

3. [Benchmarking and Solving Vehicle routing problem on various QPU's:](./Vehicle-routing-problem) 
   - Description: This project uses hybrid algorithms such as quantum approximate optimization algorithm and quadratic unconstrained binary optimization..
   

Each project includes detailed documentation and instructions on how to run the code. The repository is constantly updated with new projects as I explore more topics in quantum computing.

## Packages Used

- `Qiskit`: A quantum computing software development framework used to build and execute quantum circuits. Used in the Quantum Teleportation and Grover's Algorithm implementations.

- `NumPy`: A Python package for scientific computing that provides support for large, multi-dimensional arrays and matrices, as well as a large library of mathematical functions. Used in the Quantum Circuit Simulator project. To install, run `pip install numpy`.

- `Pennylane`: An open-source software library for quantum machine learning, quantum computing, and optimization. Used in the Quantum Machine Learning project to demonstrate a quantum support vector machine.
  
- `Dwave Ocean SDK`: It is a suite of open source Python tools on the D-Wave GitHub repository for solving hard problems with quantum computers.

## Getting Started:
To get started with these projects, simply clone or download the repository to your local machine. Each project has its own folder containing the necessary code and instructions on how to run it. Some projects may require installation of additional packages, such as Qiskit or Pennylane, which can be easily installed using pip.

**First steps to run locally**

Create a conda environment with the required dependencies:
```bash
conda env create -n quantumproj environment.yml && conda activate quantumproj
```
Install qiskit, qiskit-nature and PySCF via pip. 

Install pip first:
```bash
conda install -yc conda-forge pip==22.1.2 && python3 -m pip install -U --upgrade pip
```
Installing qiskit[all] :
```bash
python3 -m pip install -U qiskit[all]
```
Installing pennylane :
```bash
python3 -m pip install -U pennylane --upgrade
```
PennyLane comes with high performance built-in simulators, such as `default.qubit`, `default.mixed`, and `lightning.qubit`. In addition, it supports additional quantum simulators and quantum hardware via an array of plugins. Visit the [plugins](https://pennylane.ai/plugins.html) page for details. As a instance, to use 'qiskit' :
```bash
python3 -m pip install -U pennylane-qiskit
```
More details on installation are in  the [document](https://github.com/quantumlib/Cirq). 
Manually installing cirq :
```bash
python3 -m pip install -U cirq
```
Final step, installing PySCF (no support for native Windows platform, see [issue #750](https://github.com/pyscf/pyscf/issues/750)):
```bash
python3 -m pip install -U qiskit-nature[pyscf]
```

  
<br>
  
Alternatively, one can install the required dependencies via the [package_list.txt](package_list.txt) file:
```bash
conda create -yn quantumproj python==3.9.11 && conda activate quantumproj
```
```bash
conda update -yn base -c defaults conda && conda install -yc conda-forge pip==22.1.2
```
```bash
python3 -m pip install --user --upgrade pip && python3 -m pip install -r requirements.txt
```

## Contributions:
Contributions to the repository are always welcome! If you have any ideas for new projects or would like to contribute to an existing one, please feel free to open a pull request.

# License

This work is licensed under a [MIT License](LICENSE) license.

<hr>

Created and maintained by [@Shisheer S Kaushik][1].

[1]: https://github.com/ShisheerKauhik24
