#Introduction

To run grid based calculations in Quantics you require and Input file and an Operator file.

##Operator File

To specify a Hamiltonian, you need an operator file. 
The operator file ``ho.op'' codes the Harmonic oscillator Hamiltonian above. You will see
there are 3 SECTIONS. 

The OP-DEFINE-SECTION contains a title that will be printed in output.

The HAMILTONIAN-SECTION defines the operator. The line beginning "modes" defines the fact there
is a single coordinate, labelled "x". The 2 lines between the dashes (these are not required
for the operator, and are included to help readability) define 2 terms that can be related to
the Hamiltonian.

The PARAMETER-SECTION defines the mass and frequency. Values of a proton mass with a
frequency close to 3500 cm$^{-1}$ are given. This is an approximate C--H stretch.

##Input File

To run a calculation you need an input file. Look at ho.inp. Again there are various SECTIONs.

The OPERATOR-SECTION defines the file containing the operator - here "ho.op".

The PRIMITIVE-BASIS-SECTION defines the ``primitive basis set'' - a grid of points on which
the wavepacket will be propagated. Here 121 points between $x=-2$ au and $x=2$ au are defined.
( $1$ au $\sim 0.5 \AA$ ).

The SPF-BASIS-SECTION defines the number of ``single-particle'' basis functions that will
be used to describe the evolving wavepacket. For a 1D problem only 1 function is required.

The INIT-WF-SECTION defines the initial wavefunction. A Harmonic oscillator ground-state 
eigenfunction is specified here for mode $x$. The 4 parameters specify the centre of the
wavepacket, its momentum, and the frequency and mass of the harmonic oscillator. Notice that
the oscillator has been displaced to $x=2.0$ au. 

Finally, the RUN-SECTION defines what will be calculated. Here we are running a propagation 
that will last for 20 fs with output written ever 0.5 fs. Output will be written to a 
directory ``ho''.
