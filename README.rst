pennylane_to_qiskit_hamiltonian
===============================

This function helps to covert Pennylane Hamiltonian to QISKit Hamiltonian

Example
=======
Prepare a qubit hamiltonian in Pennylane:

.. code-block:: bash

  print(h_pennylane)

.. code-block:: bash

  (-0.10633119275955037) [I0]
    + (0.1702977824748741) [Z0]
    + (0.1702977824748741) [Z1]
    + (-0.2200940322812765) [Z2]
    + (-0.22009403228127644) [Z3]
    + (0.16834151984303647) [Z0 Z1]
    + (0.045404703169106816) [Y0 X1 X2 Y3]
    + (-0.045404703169106816) [Y0 Y1 X2 X3]
    + (-0.045404703169106816) [X0 X1 Y2 Y3]
    + (0.045404703169106816) [X0 Y1 Y2 X3]
    + (0.1202071443598718) [Z0 Z2]
    + (0.1656118475289786) [Z0 Z3]
    + (0.1656118475289786) [Z1 Z2]
    + (0.1202071443598718) [Z1 Z3]
    + (0.17407821153636974) [Z2 Z3]

Then convert it to QISKit hamiltonian. And they are ready to be solved in QISKit VQE:

.. code-block:: bash

  h_qiskit = to_qiskit_hamiltonian(h_pennylane,4)
  print(h_qiskit.print_details())
  
.. code-block:: bash

  IIII	(-0.10633119275955037+0j)
  ZIII	(0.1702977824748741+0j)
  IZII	(0.1702977824748741+0j)
  IIZI	(-0.2200940322812765+0j)
  IIIZ	(-0.22009403228127644+0j)
  ZZII	(0.16834151984303647+0j)
  YXXY	(0.045404703169106816+0j)
  YYXX	(-0.045404703169106816+0j)
  XXYY	(-0.045404703169106816+0j)
  XYYX	(0.045404703169106816+0j)
  ZIZI	(0.1202071443598718+0j)
  ZIIZ	(0.1656118475289786+0j)
  IZZI	(0.1656118475289786+0j)
  IZIZ	(0.1202071443598718+0j)
  IIZZ	(0.17407821153636974+0j)


