# FML-project-IITJ
## Quantum Machine Learning [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

[![Python version 3.9](https://img.shields.io/badge/python-v3.9-brightgreen)](https://docs.python.org/3/whatsnew/3.9.html)


[Proposal Title](#proposal-title) | [Problem Statement](#problem-statement) | [contributors](#contributors) | [Plan of Action](#plan-of-action) | [Implementation details](austism) | [Project Report](prompt/report.pdf) | [Project Slides](prompt/ppt.pdf) | [Video](https://youtu.be/uIKkJragaoU?si=E95tmCCPxxCMWNke) | [Conclusion](#conclusion) |

The implementation of the project can be accessed via the following link: [here](austism).<br>
Also access the implemented [code notebook](austism/penn.ipynb).

## CSL7670 : Fundamentals of Machine Learning-Project Proposal
### Contributors:

| Author           | Linkedin profile                                 |
|------------------|-------------------------------------------------|
| Shisheer S Kaushik(M23IQT0063) | [Kaushik](https://www.linkedin.com/in/shisheerkaushik24/) | 
| Thirumalai M(M23IQT008)| [Thiru](https://www.linkedin.com/in/m-thirumalai/?originalSubdomain=in)| 
| Haris Ansari(M23IQT003)| [Haris](https://www.linkedin.com/in/haris-ansari-647861176/?originalSubdomain=in)| 
| Sumit Kumar(M23IQT007) | [Sumit](https://www.linkedin.com/in/sumit-kumar-690869195/) |                                                          

#### Proposal Title

**QCNN - Automated Medical Image Diagnostics using QML**

#### Problem Statement

In the realm of image classification, the endeavor to harness the capabilities of Quantum Convolution Neural
Networks (QCNN) emerges as an intriguing challenge. Our mission is to delve into the unique convergence of
quantum computing and image analysis. Specifically, we aim to implement a model classifying face image
data set to predict disorders (i.e.,Parkinson’s, Autism, etc), And to unravel the mysteries of QCNN
architecture and its application in classifying images, while keeping a keen focus on the medical dataset and
targeted towards disorders. Furthermore, we endeavor to draw comparisons between the QCNN and its
classical counterpart, the Convolution Neural Network (CNN).<br>

#### Objectives

Our project’s primary objectives include:<br>
• Building a diagnostic model for medical images.<br>
• Employing Convolution Neural Networks (CNNs) and transfer learning techniques.<br>
• Understanding the CNN in terms of Quantum Gates and circuits<br>
• Comparing the results between Classical CNN and QCNN.<br>
• Enabling real-time image interpretation to expedite the diagnostic process.<br>

#### Plan of Action

To successfully execute our project, we propose a structured plan of action:<br>
**Week 1**: Literature Survey and Data Preparation<br>
• Analyzing critically and concisely earlier research and literature related QCNN.<br>
• Gain a thorough understanding of medical data set and its unique challenges.Preprocess the dataset,
ensuring it’s structured and cleaned.<br>

**Week 2**: Quantum Circuit Design<br>
• Begin the design of quantum circuits for the QCNN model. Translate Convolution and pooling layers
into quantum gate operations.<br>
• Implement a QCNN architecture designed for 4 qubits. Verify that the circuits match the classical CNN
layers in functionality.<br>

**Week 3**: Quantum Model Training<br>
• Set up the training pipeline for the QCNN. Define loss functions and optimization strategies for
quantum parameters.<br>
• Train the QCNN, aiming to minimize the loss function through iterations. Evaluate its performance on
the training data.<br>

**Week 4**: Testing, Evaluation and Comparison<br>
• Employ a dedicated test dataset to assess the QCNN’s image classification capabilities. Calculate
accuracy, precision, and recall.<br>
• Create a comparative analysis with a classical CNN model for image classification, focusing on their
respective performance.<br>

#### Conclusion
By adhering to this 4-week plan, we aim to unravel the potential of Quantum Convolution Neural Networks
in image classification and shed light on their quantum prowess in comparison to traditional approaches.<br>

**First steps to run locally**

Create a conda environment with the required dependencies:
```bash
conda env create -n quantumproj environment.yml && conda activate quantumproj
```
Installing pennylane :
```bash
python3 -m pip install -U pennylane --upgrade
```
PennyLane comes with high performance built-in simulators, such as `default.qubit`, `default.mixed`, and `lightning.qubit`. In addition, it supports additional quantum simulators and quantum hardware via an array of plugins. Visit the [plugins](https://pennylane.ai/plugins.html) page for details. As a instance, to use 'qiskit' :
```bash
python3 -m pip install -U pennylane-qiskit
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

This work is licensed under a [Apache v2.0](LICENSE) license.

<hr>

Created and maintained by [@Shisheer S Kaushik][1].

[1]: https://github.com/ShisheerKauhik24
