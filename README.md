# Crystals-And-Dislocations

This is a code library for generating crystals with dislocations. See the [Dislocations.nb Guide](https://docs.google.com/document/d/1CMYfdGpIORvps4SmJXQvFXV0BvZFhSqLlSqkU6s1098/edit?usp=sharing)
for further details on the Mathematica file `Dislocations.nb` (the library). It outlines all the user-intended functions, covers important implementation details and conversions from math to code, and gives a few examples. `Dislocations.nb` also has a Demos section which has many more examples and pictures.

## Illustrations made with this library:

### 1. Basic Functionality Demo:

<p align="center">
<img src="/images/1.png" alt="graphene with a dislocation" width="300"/><img src="/images/2.png" alt="a loop of graphene" width="300"/><img src="/images/3.png" alt="haldane model zoomed in" width="150" style="100"/>
</p>

Lines are connections between sites. Note that only hexagonal crystals are shown in this demo, but any unit cell and any Hamiltonian can be created and analyzed in the same exact way--square, hexagonal, cubic, diamond, fcc, bcc, hcp, etc., with any pattern of connections between sites.

**_left_**$^\dagger$: A crystal with a simple dislocation (Burgers vector = {1,0,0}). Note the the hexagonal pattern continues at all points$^\dagger$.

**_center_**: Connections that wrap over the boundary are drawn transparent. This is a cylinder of graphene: imagine the transparent connections as looping around the back of the crystal (they're "deeper into the screen" or "behind" the other connections), making the crystal's topology one of a cylinder. The bottom left point can easily be removed to make it a perfect cylinder--this removal is not possible to anticipate in general, so it is left in.

**_right_**: Connections that are imaginary or complex are drawn with an arrow. The crystal drawn is the Haldane Model. 


### 2. Wavefunction Drawing Demo:

<p align="center">
  <img src="/images/!dis.png" alt="dislocation 1" width="250"/> <img src="/images/!haldane.png" alt="haldane wavefn" width="250"/> <img src="/images/!KM.png" alt="kanemele wavefn" width="250"/>
</p>

Wavefunctions are drawn with radius $\propto$ amplitude, color $\propto$ phase. The crystal's connections are still drawn too.

**_left_**$^\star$: A crystal with a dislocation (Burgers vector = {2,3,0}).

**_center_**: One of the eigenstates or "wavefunctions" localized on the crystal's edge, robust against the dislocation (Haldane Model) (imaginary connections are now drawn in addition to the real red connections). This state appears because the crytal is finite and has no periodic boundary conditions.

**_right_**: Same as **_center_** (but with Kane Mele Model).

### 3. Band Diagram Demo:

<p align="center">
<img src="/images/band1.png" alt="band" width="500"/><img src="/images/band2.png" alt="band" width="500"/>
</p>

**_left/first_**: Band plot for a crystal (not shown) that has two periodic directions (see **_below_** for an alternate angle).

**_right/second_**: Band plot for the same crystal, but the crystal is periodic in only one direction. Note the minor differences which are hard to see at first glance (a few curves that now appear in the 1D case): these are the energies of states that live on the edge/boundary that was introduced going from fully periodic to periodic in only one direction.

**_below_**: An alternate view of the **_left/first_** band plot.

<img src="/images/band1.5.png" alt="band alt view" width="300"/>

### 4. Overview & Indexing Vectors and Wavefunctions in a Hamiltonian:
The notebook offers code for creating crystals (reading cif files, importing unit cells and creating Hamiltonians efficiently), adding dislocations (and other crystal manipulation functions like shifting and removing sites and cells), and drawing bands/wavefunctions. These are built on top of very helpful Hamiltonian indexing functions which let you convert between a coordinate/site in the crystal and an index in the Hamiltonian. `IndexOfCoord` assigns a unique number or "index" to each coordinate on a grid, and `CoordiOfIndex` is the inverse of that, giving the $i^{th}$ component of the coordinate which has index $i$. They're very abstract and can be used in other contexts besides just Hamiltonians. The code also has variations that can be used to index Hamiltonians and eigenvectors even when sites were removed (ie in a dislocation), which require just 1 more piece of information. See the Guide for more. 


<br>
<br>


$^\dagger$
An electron in the bulk of this crystal sees the crystal as being perfectly uniform, except for the single point at the very center. That's because the hexagon pattern continues at all points in the crystal except for the center point (this is the definition of the dislocation). Some hexagons do look stretched, but note that the locations of the sites drawn carry no meaning: only the connections are meaningful. 

This was the simplest design choice for creating a dislocation on a computer:
start with a perfect crystal, manipulate the connections and remove some sites to create the dislocation, and don't worry about about drawing distances accurately afterwards since we only care about connections anyway.
