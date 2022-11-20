<h1>Estimator_Routine</h1>

<h2> Introduction </h2>

<p> 
  The Estimator : <br><br>
    gives you the calculated and interpreted expectation values of quantum operators.The Estimator requires that you have the circuit with 'no measurements'. The reason    why is that in running algorithms like VQE, the Estimator will bind single-qubit rotations to get your hamiltonians so we cannot have measurements.<br>
  
  One of the interesting uses of Estimator is that it could be especially used for calculating hamiltonians with respect to observables.<br>
  
  Hamiltonians : <br><br>
  A hamiltonian is a quantum mechanical operator and it has the total energy information inside a system including kinetic and potential energy. This is the reason why   is that we need to calculate it. If you can compute its energy value, you can find its energy in nature or its cost in machine learning. It can be said to find the     ground state and excited states, so it is closely related to quantum physics, quantum chemistry, and quantum machine learning !<br>
  
  To calculate hamiltonians, a parametrized circuit is needed. It is easy to make a random parametrized circuit using RealAmplitudes.

</p>

<h2>  Building an Estimator routine to compute the expectation values of custom Hamiltonians with respect to certain observables. </h2>

<p> 
  The main obejct is to compute  ⟨𝜓1(𝜃)|𝐻1|𝜓1(𝜃)⟩ ,  ⟨𝜓2(𝜃)|𝐻2|𝜓2(𝜃)⟩ , and  ⟨𝜓3(𝜃)|𝐻3|𝜓3(𝜃)⟩  and all the circuits consist of 5 qubits :
  
  1) I am starting by making three random circuits using RealAmplitudes :  𝜓1(𝜃)  for reps = 2,  𝜓2(𝜃)  for reps = 3, and  𝜓3(𝜃)  for reps = 4.
  2) After that i am defining the Hamiltonians using SparsePauliOp :
  
      - 𝐻1=𝑋1𝑍2+3𝑌0𝑌4 
  
      - 𝐻2=2𝑋3 
  
      - 𝐻3=3𝑌2+5𝑍1𝑋3
  
  3) Making a list of evenly spaced values for theta between 0 and 1 using numpy.linspace. Note that the number of parameters is different for reps of each circuit.
 
  4) I used the Estimator with options defined in the cell to calculate each expectation value
</p>

