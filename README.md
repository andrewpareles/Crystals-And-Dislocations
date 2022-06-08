# Dislocations-Research

See the [Dislocations.nb Guide](https://docs.google.com/document/d/1CMYfdGpIORvps4SmJXQvFXV0BvZFhSqLlSqkU6s1098/edit?usp=sharing)
for further details. It outlines all the user-intended functions, covers important implementation details and conversions from math to code, and gives a few examples.

## Illustrations made with this library:

### 1. Basic Functionality Demo:

<p align="center">
<img src="/images/1.png" alt="graphene with a dislocation" width="300"/><img src="/images/2.png" alt="a loop of graphene" width="300"/><img src="/images/3.png" alt="haldane model zoomed in" width="150" style="100"/>
</p>

Lines are connections between sites. Note that only hexagonal crystals are shown in this demo, but any unit cell and any Hamiltonian can be created and used in the same exact way.

**_left_**: A simple dislocation, with Burgers vector = {1,0,0}. Note the continued hexagonal pattern everywhere$^\star$.

**_center_**: A cylinder of graphene: imagine the transparent connections as "deeper into the screen" or "behind" the other connections, creating the topology of a cylinder. Connections that wrap over the boundary are drawn transparent.

**_right_**: The crystal drawn is the Haldane Model. Connections that are imaginary or complex are drawn with an arrow.


### 2. Wavefunction Drawing Demo:

<p align="center">
  <img src="/images/!dis.png" alt="dislocation 1" width="300"/> <img src="/images/!haldane.png" alt="haldane wavefn" width="300"/> <img src="/images/!KM.png" alt="kanemele wavefn" width="300"/>
</p>

**_left_**: A crystal with a dislocation (Burgers vector = {2,3,0}).

**_center_**: One of the eigenstates or "wavefunctions" localized on the crystal's edge (Haldane Model).

**_right_**: One of the eigenstates or "wavefunctions" localized on the crystal's edge (Kane Mele Model).

### 3. Band Diagram Demo:

<p align="center">
<img src="/images/band1.png" alt="band" width="500"/><img src="/images/band2.png" alt="band" width="500"/>
</p>

**_left_**: Band plot of a crystal periodic in two directions (see **_below_** for an alternate angle).

**_right_**: Band plot of the same crystal, but periodic in only one direction. Note the couple of differences: these are the energies of states that live on the edge/boundary that was introduced going from fully periodic to periodic in only one direction.

**_below_**: An alternate view of the **_left_** band plot.

<img src="/images/band1.5.png" alt="band alt view" width="300"/>

<br>
<br>
<br>


$^\star$
The crystal is uniform everywhere except at the dislocation, as expected. You can tell this from the uniform hexagon pattern everywhere except at the center of the crystal, which is on the dislocation line. 
Note that the locations of the sites drawn carry no meaning: only the connections are meaningful. (This was the simplest design choice for creating a dislocation on a computer:
create a perfect crystal, manipulate the connections, and don't worry about about drawing distances accurately since we only care about connections anyway).
