# Determining the conformation of a protein that corresponds to its lowest possible energy state

## Contents
<nav>
  <ul>
	  <li><a href="#section1">Abstract</a></li>
	  <li><a href="#section2">Project Contribution</a></li>
    <li><a href="#section3">About QR Code Generator Project</a></li>
    <li><a href="#section4">Generate QR Code in Python</a></li>
    <li><a href="#section5">General Implementation</a></li>
    <li><a href="#section6">Project Summary</a></li>
    <li><a href="#section7">How exactly is qrcode generated using a quantum computer in this project ?</a></li>
    <li><a href="#section8">Adding Error Correction code</a></li>
    <li><a href="#section9">Using Quantum Fourier Transform (QFT), to support larger messages</a></li>
    <li><a href="#section10">Why only 7 bits instead of 8 to represent a letter ?</a></li>
    <li><a href="#section11">Future Scopes and Improvements</a></li>
  </ul>
</nav>


<section id="section1">
  <h2>Abstract</h2>
  <p>

Nowadays we all use **QR code** for multiple purposes like making payments, sharing WiFi, etc. Have you ever wished to generate such QR code on your own ?, this project is for generating a QR code using `Qiskit` Sdk and `Python` programming language.
  
  </p>
</section>

<section id="section2">
  <h2>Project Objective</h2>
  <p>
    
The passage describes a scientific endeavor to find the lowest energy conformation of a protein. The conformation of a protein refers to the specific shape it takes on, which is determined by the way its constituent amino acid units fold and interact with one another. The energy of a protein conformation is a measure of how stable and favorable it is energetically.
To determine the lowest energy conformation of a protein, the scientists start with a random configuration of the protein's atoms. They then use an optimization algorithm to iteratively adjust the configuration in order to minimize the energy. The optimization process involves changing the positions of the atoms in the protein in small increments until a configuration with a lower energy is found.
To aid in this optimization process, the scientists encode the protein folding problem into a qubit operator. A qubit is a unit of quantum information that can exist in two states (0 or 1) simultaneously, which allows for powerful parallel processing. The qubit operator is a mathematical representation of the protein folding problem that can be manipulated using quantum computing algorithms.
By encoding the protein folding problem into a qubit operator, the scientists are able to apply quantum computing techniques to the problem. This enables them to use the principles of quantum mechanics to solve the problem more efficiently than classical computing methods. It also allows them to ensure that all physical constraints are satisfied, meaning that the resulting protein conformation is physically plausible and satisfies the laws of thermodynamics and other physical principles.
In summary, the passage describes a scientific approach to finding the lowest energy conformation of a protein. This involves using an optimization algorithm to iteratively adjust the configuration of the protein atoms while ensuring that physical constraints are satisfied. To aid in this process, the scientists encode the protein folding problem into a qubit operator and use quantum computing techniques to solve the problem more efficiently.
  
  </p>
</section>

<section id="section3">
  <h2>Project Implementation</h2>
  <p>
    
The project utilizes the *problem encoding*, which refers to the method used to represent the protein folding problem in a way that can be solved by a quantum computer. Two types of qubits are used for this purpose: *configuration qubits* and *interaction qubits*.

1. **Configuration qubits** are qubits that describe the position and orientation of the            different beads that make up the protein. In other words, they encode the geometry or shape      of the protein. The position of each bead is described using a series of turns in a              tetrahedral lattice, which is a diamond-shaped lattice. The movement of the protein through      the lattice is encoded using the configuration qubits.

2. **Interaction qubits**, on the other hand, encode the interactions between different amino      acids in the protein. These interactions are important for stabilizing the folded structure      of the protein. In the context of quantum computing, the interaction qubits are used to          represent the pairwise interactions between amino acids, which are described using a            mathematical function known as the **Hamiltonian**.

It uses a tetrahedral lattice, it is important because it allows for the efficient representation of the protein's geometry using a minimal number of qubits. The tetrahedral lattice is a regular lattice that is well-suited for describing the structure of proteins, as it closely approximates the natural environment in which proteins fold.

Overall, the problem encoding involves representing the protein folding problem using a combination of configuration qubits and interaction qubits, with the position and orientation of the beads encoded using a series of turns in a tetrahedral lattice.

  </p>
</section>

<section  id="section4">
  <h2>Hamiltonian System</h2>
  <p>
    
The algorithm uses the Hamiltonian of the system to model the protein folding problem. Hamiltonian is a mathematical expression used to describe the total energy of a physical system. In this case, the system consists of two types of qubits, configuration qubits, and interaction qubits.
The Hamiltonian of the system is defined as the sum of three terms: *H_gc*, *H_ch*, and *H_in* as shown in the below equation.
```bash
 H(q) = H_gc(q_cf) + H_ch(q_cf) + H_in(q_cf,q_in)
```
1. **H_gc**, represents the geometrical constraint term, which governs the growth of the primary    sequence of amino acids without bifurcations. It describes the spatial arrangement of the        beads (amino acids) on the lattice and ensures that the protein chain does not intersect or      form knots during folding.

2. **H_ch**, is the chirality constraint, which enforces the right stereochemistry for the          system. It ensures that the protein chain folds into the correct three-dimensional shape,        with the correct arrangement of atoms and functional groups.

3. **H_in**, is the interaction energy term that takes into account the interactions between the    different amino acids in the protein chain. In this case, only nearest-neighbor interactions    are considered. These interactions are important because they determine the stability and        folding of the protein structure.

Overall, the Hamiltonian captures the essential physical and chemical factors that influence protein folding and enables the calculation of the lowest energy state (ground state) of the system, which corresponds to the most stable protein conformation.

![](asset/Captur.jpg)
  
  </p>
</section>

<section id="section5">
  <h2>Project Details</h2>
  <p>
    
In the proposed algorithm, the length of the side chains of amino acids, which are the groups of atoms that branch off the main chain of a protein. These side chains can vary in length and complexity, and they can greatly affect the folding and stability of a protein. The elongated side chains (i.e., side chains that are longer than normal) would require the introduction of additional penalty terms. Penalty terms are mathematical expressions that are added to the energy function of a system to penalize certain configurations or behaviors. In the context of protein folding, penalty terms might be added to discourage the formation of energetically unfavorable conformations or to penalize the presence of strained bonds or angles. 

These additional penalty terms are still under development, meaning that researchers are still working to determine the best way to incorporate them into protein folding simulations. Therefore, in tsome exaples of the propsed project, we do not consider any side chains at all in order to simplify the simulation and focus on the main chain of the *neuropeptide*.

**Neuropeptide** refers to a short chain of amino acids that acts as a signaling molecule in the nervous system. Neuropeptides are a type of peptide, which is a compound consisting of two or more amino acids linked by peptide bonds. The neuropeptide mentioned in this passage has a primary sequence of **N** amino acids with the letter codes **{A,P,R,L,R,F,Y,M,N,}**.

In general, the maximum length of side chains can vary depending on the amino acid. Some amino acids, such as glycine and alanine, have very small side chains consisting of only one or two atoms. Others, like phenylalanine and tryptophan, have larger aromatic side chains. The longest side chain is found in the amino acid lysine, which has a chain of four carbon atoms. However, in the context of the passage you mentioned earlier, it seems that the length of secondary chains is limited to one for the purpose of describing the shape of the protein chain. Our model allows for side chains of the maximum length of one. 
    
  </p>
</section>

<section id="section6">
  <h2>Prtein Interaction</h2>
  <p>
    
In order to describe inter-residue contacts for proteins, the authors use knowledge-based potentials that are derived using quasi-chemical approximation. The term "quasi-chemical approximation" refers to a method used to derive the properties of a system by considering it to be in equilibrium with a reservoir of similar but distinct systems. The potentials used in this study are introduced by Miyazawa and Jernigan in their publication, which is referenced as [5].
The knowledge-based potentials are based on the statistical analysis of known protein structures, and they describe the likelihood of a particular pair of residues forming a contact in a protein structure. In other words, the potential indicates the probability of two amino acids being in close proximity in a folded protein structure. The potential is derived based on the frequency of occurrence of specific pairs of amino acids in protein structures.
In addition to the knowledge-based potentials, the authors also allow for random contact maps or interaction maps that provide a random interaction pattern. The contact maps can also be customized to enhance certain configurations of the protein, such as alpha helix or beta sheet structures. By using these different types of contact maps, the authors can explore different possibilities for the folded protein structure and analyze how the different types of interactions affect the folding process.

Finally, the secret binary message and the binary measurement are printed as shown below. In this specific run of the code, the input message was **u**, the secret code was **01110101**, and the measurement was **10001011**.

![](asset/bern-vazi/result.png)

And the histogram of the result is plotted as shown below. 

![](asset/bern-vazi/graph.png)

  </p>
</section>

<section id="section7">
  <h2>How exactly is qrcode generated using a quantum computer in this project ?</h2>
  <p>

The message is encoded into a quantum state using quantum gates, and the measurement results are then used to generate the QR code using the classical library qrcode.

In more detail, the quantum circuit is designed to encode the binary message into a superposition of quantum states, and then use the measurement results to extract the encoded message. The H gate is applied to all qubits to put them in a superposition of states. The `Z gate` is applied to the qubits corresponding to **1** in the oracle to flip the phase of those states. Finally, the `H gate` is applied to all qubits except the last one to encode the message.

The qubits are then measured, and the measurement results are used to extract the encoded message in binary format. The extracted message is then passed to the qrcode library to generate the QR code.

Therefore, the quantum circuit is used to encode the message into a quantum state, and the classical code is used to extract and use the information from the quantum state to generate the QR code as shown below.

![](asset/bern-vazi/qr_code.png)

The code uses the *Bernstein-Vazirani algorithm* as a subroutine to encode the message into a quantum state.

Verified the obtained *QR-code* with the Google_lens:

<img src="asset/Google_lens_2.jpg" alt="Google_lens_2" width="65%" />

In the *Bernstein-Vazirani algorithm*, a secret binary string (oracle) is encoded into a quantum state, and the algorithm's goal is to determine the secret binary string using the quantum state's measurement results. The oracle string is used to generate the quantum state by flipping the phase of the qubits corresponding to **1** in the oracle string.

In this model, the secret binary string is generated from the user's input message by converting it to binary and flipping the bits to create an oracle string. This oracle string is then used to encode the message into a quantum state using the `Z gate` to flip the phase of the qubits corresponding to **1** in the oracle string. This encoding process is equivalent to the encoding process in the Bernstein-Vazirani algorithm.
    
  </p>
</section>

<section id="section8">
  <h2>Adding Error Correction code</h2>
  <p>

According to the results obtained, the secret code for the message **u** is **01110001**, and the measurement obtained from the quantum circuit is **01111001**. These two binary strings should be equal for the encoding and decoding to be successful, and in this case they are different. This is expected, since *errors* can occur during the encoding process due to the **noisy nature** of quantum devices.

The `AerSimulator` in Qiskit also allows you to simulate noise in your quantum circuits. Specifically, you can add noise models to the simulator to simulate various types of errors, including:

  * Depolarizing error
  * Amplitude damping error
  * Phase damping error
  * Thermal relaxation error
  * Bit-flip error
  * Phase-flip error
  * Readout error

In order to mitigate error, an **error correction** step is added to the quantum circuit in case the measurement does not match the secret binary string. Specifically, it uses an `ancilla` qubit to flip the last qubit of the quantum register if necessary, effectively correcting the error.

![](asset/error/circuit.png)

The above image shows the improvised circuit with added correction steps.

![](asset/error/error_corc_code.png)

The correction steps was icluded as shown in the above code-snippet.

![](asset/error/simulator.png)

The above circuit was simulated using the `qasm_simulator` as shown above.

![](asset/error/result.png)

The secret binary message and the binary measurement are printed as shown below. For the input message **u**, the secret code was **01110101**, and but the measurement obtained were improvised, even though not accurate. It was **10101101**.

![](asset/error/graph.png)

The histogram of the result is plotted as shown above.
    
  </p>
</section>

<section id="section9">
  <h2>Using Quantum Fourier Transform (QFT), to support larger messages</h2>
  <p>

The previous implementation is limited to encoding messages of length **1-2** characters. Hence, to make the project more practical, I have extend the encoding process to support larger messages. One possible approach is to use the [Quantum Fourier Transform](https://qiskit.org/textbook/ch-algorithms/quantum-fourier-transform.html) `QFT` to encode the message into a quantum state, similar to how the QFT is used in Shor's algorithm.

In this modified code, I first calculate the required number of qubits based on the length of the binary message, and then apply the `QFT` to the qubits. The oracle is applied by flipping the qubits corresponding to a **1** in the binary message. Finally, the `inverse QFT` is applied to the qubits, and the measurement is performed on all qubits except the last one. The resulting binary measurement is used to generate the QR code. *Note that the QFT is applied in a similar way to how it is used in Shor's algorithm to factor integers*.

The number of letters that can be encoded using QFT-based encoding depends on the number of qubits available in the quantum computer. Each qubit can represent two values, **0** or **1**, so the number of possible states that can be encoded using **n** qubits is **2^n**.

For example, if you have **5** qubits, you can encode **2^5 = 32** different states, which can represent a larger number of characters than the approach used in the original code. However, it is important to note that the number of qubits needed to encode a message grows exponentially with the length of the message, making it challenging to encode longer messages on current quantum computers.

![](asset/qft/message.png)

Unlike earlier, this time the user inputs a message **warm** as shown above to encode which is then converted into binary format. 

![](asset/qft/simulator.png)

The above circuit is simulated using the `qasm_simulator` as shown above.

![](asset/qft/result.png)

For the the secret binary message **warm**, the secret code and it's binary measurement are printed as shown above.

![](asset/qft/graph.png)

Rhe respective histogram of the result is plotted as shown above.

![](asset/qft/qr_code.png)

And the respective QR code generated through quantum state is shown above .

Verified the obtained *QR-code* with the Google_lens:

<img src="asset/Google_lens_1.jpg" alt="Google_lens_1" width="50%" />
    
  </p>
</section>

<section id="section10">
  <h2>Why only 7 bits instead of 8 to represent a letter ?</h2>
  <p>
    
The fewer bits used, the more accurate the result. When converting from text to binary in Python, the data is prepended with **0b**, which is just a computational way of saying "binary is about to follow". In my script I scrape both of these off. If you were to google an [Ascii to binary](http://sticksandstones.kstrom.com/appen.html) table, you would see all text starts with 0. Again, we don't need that, so I scrape it off. Like the above explanation about how circuit depth effects accuracy, so does the number of qubits used, called circuit width. Both circuit width and depth to account for accuracy are taken into consideration, called quantum volume (or QV). For this interactive implementation, I ran all circuits on the quantum computer call **ibmq_16_melborne** with the highest quantum volume, with `QV64`.
    
  </p>
</section>

<section id="section11">
  <h2>Future Scopes and Improvements</h2>
  <p>

1. **Error Correction**: One potential issue with the current implementation is that the QR code may be susceptible to errors due to the inherent noise in quantum systems. To address this issue, we can use quantum error correction codes to protect the encoded message against errors. This would require a deeper understanding of quantum error correction and how to implement it in the circuit.

2. **Hybrid Approach**: Another approach to enhance the project is to use a hybrid classical-quantum approach, where the encoding process is performed on a classical computer, and the decoding process is performed on a quantum computer. This approach can potentially improve the efficiency of the overall process while leveraging the strengths of both classical and quantum computing.

3. **Security**: While the current implementation uses the Bernstein-Vazirani algorithm to encode the message, it is not inherently more secure than a classical QR code. To increase the security of the encoded message, we can explore other quantum cryptographic protocols, such as Quantum Key Distribution `QKD`, that leverage the properties of quantum mechanics to ensure secure communication.

4. **Generalization**: Finally, we can generalize the project to support other types of codes beyond QR codes, such as barcodes or other types of two-dimensional codes. This would require a deeper understanding of the structure and encoding schemes of other types of codes and how to implement them in a quantum circuit. 
    
  </p>
</section>
