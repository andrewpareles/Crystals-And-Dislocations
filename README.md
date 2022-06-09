# Crystal-Dislocation-Tools

See the [Dislocations.nb Guide](https://docs.google.com/document/d/1CMYfdGpIORvps4SmJXQvFXV0BvZFhSqLlSqkU6s1098/edit?usp=sharing)
for further details on the Mathematica file `Dislocations.nb` (the library). It outlines all the user-intended functions, covers important implementation details and conversions from math to code, and gives a few examples.

## Illustrations made with this library:

### 1. Basic Functionality Demo:

<p align="center">
<img src="/images/1.png" alt="graphene with a dislocation" width="300"/><img src="/images/2.png" alt="a loop of graphene" width="300"/><img src="/images/3.png" alt="haldane model zoomed in" width="150" style="100"/>
</p>

Lines are connections between sites. Note that only hexagonal crystals are shown in this demo, but any unit cell and any Hamiltonian can be created and used in the same exact way.

**_left_**: A crystal with a simple dislocation (Burgers vector = {1,0,0}). Note the the hexagonal pattern continues at all points$^\star$.

**_center_**: A cylinder of graphene: imagine the transparent connections as "deeper into the screen" or "behind" the other connections, making the crystal's topology one of a cylinder. Connections that wrap over the boundary are drawn transparent. (The bottom left point can easily be removed to make it a perfect cylinder--this removal is not really possible to do in general, so I left it in).

**_right_**: The crystal drawn is the Haldane Model. Connections that are imaginary or complex are drawn with an arrow.


### 2. Wavefunction Drawing Demo:

<p align="center">
  <img src="/images/!dis.png" alt="dislocation 1" width="250"/> <img src="/images/!haldane.png" alt="haldane wavefn" width="250"/> <img src="/images/!KM.png" alt="kanemele wavefn" width="250"/>
</p>

Wavefunctions are drawn with radius $\propto$ amplitude, color $\propto$ phase. The crystal's connections are still drawn too.

**_left_**: A crystal with a dislocation (Burgers vector = {2,3,0}).

**_center_**: One of the eigenstates or "wavefunctions" localized on the crystal's edge, robust against the dislocation (Haldane Model). This state appears because the crytal is finite, so has a boundary.

**_right_**: Same as **_center_** (but with the Kane Mele Model).

### 3. Band Diagram Demo:

<p align="center">
<img src="/images/band1.png" alt="band" width="500"/><img src="/images/band2.png" alt="band" width="500"/>
</p>

**_left/first_**: Band plot for a crystal that has two periodic directions (see **_below_** for an alternate angle).

**_right/second_**: Band plot for the same crystal, but the crystal is periodic in only one direction. Note the minor differences which are hard to see at first glance (a few lines that now appear in the 1D case): these are the energies of states that live on the edge/boundary that was introduced going from fully periodic to periodic in only one direction.

**_below_**: An alternate view of the **_left/first_** band plot.

<img src="/images/band1.5.png" alt="band alt view" width="300"/>

<br>


$^\star$
An electron in the bulk of this crystal sees the crystal as being perfectly uniform, except for the single point at the very center. That's because the hexagon pattern continues at all points in the crystal except for the center point (this is the definition of the dislocation). Some hexagons do look stretched, but note that the locations of the sites drawn carry no meaning: only the connections are meaningful. 

This was the simplest design choice for creating a dislocation on a computer:
start with a perfect crystal, manipulate the connections and remove some sites to create the dislocation, and don't worry about about drawing distances accurately afterwards since we only care about connections anyway.
