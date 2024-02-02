# Quantum Optimization of Protein Folding Landscapes: Exploring Minimum Energy Conformations

Although, in the Qiskit implementation of the **protein folding problem**, the formula `2(n-3)` is commonly used as a rough estimate for the number of qubits required to represent a protein molecule with `n` amino acids. This formula assumes that each amino acid can be represented by two qubits and that the backbone of the protein can be represented by a linear chain of qubits with two endpoints.

While this formula can provide a quick estimate of the number of qubits needed, it is a very simplified model that does not take into account the complexity of the protein structure and the interactions between the amino acids.

In practice, the number of qubits required to accurately represent a protein molecule can vary widely depending on the *specific protein* and the *level of detail* needed for the simulation. More sophisticated models and algorithms are typically used to determine the number of qubits needed for a given protein simulation.

## Encoding the qubits into beads 

A Pauli operators is created for nearest neighbor interactions. The type of operator depends on whether beads belong to the same set, how far they are from each other and whether they host a side chain.

An interaction between 2 beads is encoded using 1 qubit. Given the possibility of interactions between main-main, main-side, side-main, side-side beads, we need at most :math:`4*N*N` qubits to encode all interactions, where :math:`N` equals main_chain_len. Note that some qubits may not be necessary because of no contacts between respective beads. Such qubits are deleted in the compression phase happening during the creation of a final qubit operator for the problem.

Also note that, using a normal coarse grained model on the tetra-hedral lattice the simulation of this system would require **35 qubits**, which is computationally intensive. We therefore introduced a denser encoding of the polymer configuration that requires only **2 qubits per turn** `ti = q2i−1q2i`, reducing the total number of qubits to **22**. This variant generated 5-local (instead of 3-local) terms in the qubit Hamiltonian while keeping the total number of Pauli strings within an affordable range for small instances. To further reduce the number of qubits we also integrate the side chains with the corresponding bead along the primary sequence and neglect interactions with l > 1.

## Contact operator fuctionality

It is a method for building contact operators in the context of the protein folding problem. Contact operators are mathematical objects used to represent the interactions between pairs of amino acids (beads) in a protein chain.

The method described in the passage assigns an index to each bead in the protein chain. The index of a bead is determined by its position in the chain and its location relative to other beads. Specifically, the index of a lower bead is given by its position in the chain, while the index of an upper bead is determined by its position within a block.

To encode this information, the passage suggests multiplying the position of the lower bead by the length of the protein chain, and adding the position of the upper bead within the block. The resulting number uniquely identifies the pair of beads and serves as an index for the corresponding entry in the contact operator.

Overall, the passage is describing a specific method for constructing contact operators for the purpose of solving the protein folding problem. By assigning indices to each bead in the chain based on its position and location relative to other beads, this method allows for efficient computation of the interactions between pairs of amino acids in the protein chain.

### what is a block in here means

A "block" refers to a group of adjacent beads in the protein chain. The position of an upper bead within a block is determined by its position relative to the other beads in the block. For example, if a block contains five beads, the first bead in the block would have an upper bead position of 1, the second bead would have an upper bead position of 2, and so on.

The indexing scheme described in the passage is based on the idea of dividing the protein chain into blocks and assigning a unique index to each pair of beads based on their positions within the blocks. By using this indexing scheme to construct contact operators, researchers can efficiently model the interactions between pairs of amino acids in the protein chain, which is essential for understanding how proteins fold and function.

The contact operators is build according to the following indexing formula:
```bash
    lower_bead_position * chain_len + upper_bead_position
```
In order to eloborate, this formulas explaination, let's take an example to understand this statement better. Let's say we have a protein chain consisting of 10 amino acids, labeled A1, A2, A3, A4, A5, A6, A7, A8, A9, and A10. To build contact operators for this protein chain, we can use the indexing scheme described in the passage as follows:

The lower bead position of each amino acid is simply its position in the chain. So, A1 has a lower bead position of 1, A2 has a lower bead position of 2, and so on up to A10, which has a lower bead position of 10.

To determine the upper bead position of each amino acid, we need to divide the protein chain into blocks. Let's say we choose to use blocks of size 3. Then, the first block would consist of A1, A2, and A3; the second block would consist of A4, A5, and A6; the third block would consist of A7, A8, and A9; and the final block would consist of A10 alone.

Within each block, the upper bead position of an amino acid is simply its position within the block. For example, within the first block, A1 has an upper bead position of 1, A2 has an upper bead position of 2, and A3 has an upper bead position of 3. Similarly, within the second block, A4 has an upper bead position of 1, A5 has an upper bead position of 2, and A6 has an upper bead position of 3. The same holds for the other blocks.

To compute the index of a pair of amino acids, we can use the formula provided in the passage:

Index = lower_bead_position * chain_len + upper_bead_position
For example, to compute the index of the pair (A1, A4), we can use the following:

Lower bead position of A1 is 1, and the upper bead position of A1 within the first block is 1.
Lower bead position of A4 is 4, and the upper bead position of A4 within the second block is 1.
So, the index of the pair (A1, A4) is:
1 * 10 + 1 = 11
Using this indexing scheme, researchers can efficiently compute the interactions between pairs of amino acids in the protein chain, which is crucial for understanding the folding and function of proteins.

Consequently, In the example I gave earlier, we used the indexing scheme to compute the index of the pair (A1, A4), which was 11. This index can help researchers efficiently compute the interactions between the two amino acids in the pair.

The interactions between pairs of amino acids in a protein chain are typically represented using a contact map or contact operator, which is a matrix that encodes the pairwise interactions between all amino acids in the chain. The contact operator is typically a large matrix, and computing all entries of the matrix can be computationally expensive.

However, using the indexing scheme described in the passage, researchers can efficiently compute the interactions between pairs of amino acids without having to compute all entries of the contact operator. Specifically, they can compute the entry in the contact operator corresponding to the pair (A1, A4) directly using the index 11, without having to compute any other entries of the contact operator.

For example, let's say we have a contact operator with dimensions 10 x 10, where each row and column corresponds to an amino acid in the protein chain. To compute the interaction between A1 and A4, we can use the index 11 to access the corresponding entry in the contact operator. This would involve finding the entry at row 1 and column 4, since A1 and A4 are in positions 1 and 4, respectively, in the protein chain.

By using the index 11 to access the corresponding entry directly, we can avoid the need to compute any other entries in the contact operator. This can significantly reduce the computational cost of computing pairwise interactions between all amino acids in the protein chain.

## Project Implementation 
A robust and versatile optimisation scheme was utilized , bringing together variational quantum algorithms specifically adapted to classical cost functions and evolutionary strategies (genetic algorithms), to simulate the folding of the 9 amino acid **Bradykinin peptide** on 17 qubits.

<p align="center">
  <a href="https://pubchem.ncbi.nlm.nih.gov/compound/Bradykinin#section=Isomeric-SMILES">
    <img src="https://github.com/ShisheerKaushik24/Junior-Researcher-Project-2/blob/master/asset/structure.png" width="250" height="150" />
  </a>
</p>

*<p align="center"><small>Source: PubChem</small></p>*

The above image is the 2-D chemical structure of Bradykinin peptide.

<p align="center">
    <img src="https://github.com/ShisheerKaushik24/Junior-Researcher-Project-2/blob/master/asset/description.png" width="400" height="150" />
</p>

*<p align="center"><small>Source: PubChem</small></p>*

The above image is the molecular description of Bradykinin peptide.

From the sequence of turns we got the cartesian coordinates of each of the aminoacids of the protein. And finally, the structure plot of the protein in 3D is created as seen below. 

<p align="center">
    <img src="https://github.com/ShisheerKaushik24/Junior-Researcher-Project-2/blob/master/asset/protein-structure.png" width="250" height="150" />
</p>
