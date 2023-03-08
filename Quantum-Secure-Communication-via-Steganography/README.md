<!-- Title: -->
<div align="center">
  <h1> <a href="https://github.com/ShisheerKaushik24/Quantum_projects"> Quantum Secure Communication via Steganography </a></h1>
  <h2> A detailed description of the project
</div>
<br>
 
## Abstract
The idea is to encode the sender's text`(secret message)` using the concept of interference. The secret message is encoded based on the cover file`(a text sentence in this case)`. A Demo video of interactive working implementation is available here: [Demo](https://drive.google.com/file/d/1RHY_QOV1cPRRPEe5KYRz-5Mahdmc7Ia7/view?usp=sharing). 

More detailed explaination can be found [here:](https://shisheerkaushik.netlify.app/)

The evaluation was done using three different communication protocols, namely *BB84*, *BB92*, and *Ekert91*, to evaluate the performance of the system. I compared the relative results obtained using each protocol to obtain more precise and accurate results. Additionally, I utilized a real quantum simulator named `FakeWashingtonV2()` to simulate the behavior of a real quantum computer. This simulator was chosen because it is a widely used open-source quantum simulator that can accurately simulate the behavior of a real quantum computer. By using this simulator, I was able to test the system's performance under realistic conditions and compare it with the theoretical predictions obtained through simulations.

## General Implementation 

I have implemented Quantum Steganography using qiskit in this project. And, I have chosen the cover file and the secret message to be in text formats to make it easier for new learners to understand the concept of quantum steganography while also trying it out interactively in a console.   

![q_stegalyzer](asset/dat0.png)

I have chosen our cover file and the secret message to be in text formats to make it easier for new learners to understand the concept of quantum steganography while also trying it out interactively in a console. 

## Implementation Details

The encoder circuit is based on 7 qubits but our interactive application has an option to create circuits based on the number of qubits selected and view them instantaneously.  

Here are some steps to interactively play with our application:

1. Choose the number of qubits using the slider. I would suggest that you choose 7 for the encoding and decoding scheme to work flawlessly. You can also test out other number of qubits to view the generated circuit.  

![no_of_qubits](asset/img2.png)

2. Enter the Secret message and press enter. For instance, let us try a letter, NOTE: Enter only small letters [i.e f,h,l, etc ]

![secret_msg](asset/dat1.PNG)

![secret_msg](asset/dat2.PNG)

Here, you can also view the generated circuit.

Above is the transpilated circuit generated with respect to the secret key entered, using the special gates during Quantum Simulation  

![secret_msg](asset/dat3.PNG)

3. This graph shows the output generated with respect the secret key entered

4. Upload a sentence where you wish to hide your message and press enter. NOTE: Enter only small words [i.e family,hindrance,lanquage, etc ]

![encode](asset/dat4.PNG)

5. Click on encode to view the encoded message

![encode](asset/dat5.PNG)

6. Then click on decode to finally view your original secret message

![decode](asset/dat6.PNG)

All the simulation was done qiskit sdk: [Secret key used: Qiskit]

a] Simulator

![decode](asset/img7.PNG)

The fig(a) graph selected is the output generated from the Quantum Simulator [ qasm_simulator]

b] Quantum Cumpter [ibmq-melbourne]

![decode](asset/img6.PNG)

The fig(b) graph slected is the output generated from the Real Quantum Computer [ ibmq-melbourne]

## Future Scopes and Improvements
As it is seen in the graphs, the simulation done on `FakeWashingtonV2()` quantum computer is comparatively different from the one done on simulation. It’s because Quantum computers are exceedingly difficult to engineer, build and program. As a result, they are crippled by errors in the form of noise, faults and loss of quantum coherence, which is crucial to their operation and yet falls apart before any nontrivial program has a chance to run to completion. 

<table align="center">
  <caption>Comparison results of `qasm_simulation` and `FakeWashingtonV2()` for BB84 prtotcol</caption>
  <tr>
    <td><img src="asset/img8.png" alt="On Simulator [qasm]" width="85%"></td>
    <td><img src="asset/img9.png" alt="On real Quantum Computer [ibmq-bogota]" width="85%"></td>
  </tr>
</table>

<table align="center">
  <caption>Comparison results of `qasm_simulation` and `FakeWashingtonV2()` for BB92 prtotcol</caption>
  <tr>
    <td><img src="asset/img8.png" alt="On Simulator [qasm]" width="85%"></td>
    <td><img src="asset/img9.png" alt="On real Quantum Computer [ibmq-bogota]" width="85%"></td>
  </tr>
</table>

<table align="center">
  <caption>Comparison results of `qasm_simulation` and `FakeWashingtonV2()` for Ekert91 prtotcol</caption>
  <tr>
    <td><img src="asset/img8.png" alt="On Simulator [qasm]" width="85%"></td>
    <td><img src="asset/img9.png" alt="On real Quantum Computer [ibmq-bogota]" width="85%"></td>
  </tr>
</table>

# License

This work is licensed under a [MIT License](LICENSE) license.

<hr>

Created and maintained by [@Shisheer S Kaushik][1].

[1]: https://github.com/ShisheerKauhik24
