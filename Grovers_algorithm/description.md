# Problem: We have an unsorted list and trying to find a particular element within that list of n length



- in the classical computing case, we will iterate the entire list with a worst case scenario of O(n) time complexity

- in the quantum computing scenario:
    - Our comparison operator will be that if we give as input the winning qubit (ex: we are looking for collapsed bits "11"), then we shall apply the Controlled Z-gate operator to get the inverse of that "-11". We shall also use a way to amplify the amplitude with something called Reflection operator which they also call "Grover's diffusion operator". The combination of the Oracle which finds does a side by side comparison of states (or 'bits' in classical computing terms), and the Reflection operator together constitute "Grover's iterate".
    - we create a superposition state of all qubits using the hadamard gate on each qubit, this way we can query each one of input states simultaneously on the oracle
    - the reflection operator is defined as two times the dot product of 's' (quantum states vector 's') minus the indentity matrix. 2|s*s| - I. Since it is a small system of 2 qubits (4 possible states) we will only need to apply amplitude amplification once. For 'n' we will have to apply amplitude amplification SQRT(n) times to get us closer to the answer.
    - in conclusion, we will apply hadamard gate to make superposition of qubits, then apply oracle gate {applies CZ gate}, then apply reflection gate {applies hadamard gate to bring back to '00', then Z gate (maps 1 to -1, but leaves 0 unchanged), then CZ gate (flips phase of target qubit), then apply hadamard again (transform back both qubits)}, then finally measure both qubits


Continuation of learning (3 qubits instead of 2): https://qiskit.org/textbook/ch-algorithms/grover.html#3.-Example:-3-Qubits-
