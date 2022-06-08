# Dislocations-Research

See the [Dislocations.nb Guide](https://docs.google.com/document/d/1CMYfdGpIORvps4SmJXQvFXV0BvZFhSqLlSqkU6s1098/edit?usp=sharing)
for further details. It outlines all the user-intended functions, covers important implementation details and conversions from math to code, and gives a few examples.

### Here are a few pictures:

<p align="center">
<img src="/images/1.png" alt="graphene with a dislocation" width="300"/><img src="/images/2.png" alt="a loop of graphene" width="300"/><img src="/images/3.png" alt="haldane model zoomed in" width="150" style="100"/>
</p>

_left_: A simple dislocation example. Lines are connections between sites. Note the continued hexagonal pattern everywhere$^\star$

_center_: A cylinder of graphene (imagine the transparent connections as "deeper into the screen" or "behind" the other connections, creating the topology of a cylinder).

_right_: Connections that are imaginary or complex are drawn with an arrow (this is the Haldane Model).


<img src="/images/dis.png" alt="dislocation 1" width="300"/>

_left_: A larger and more complicated dislocation (Burgers vector is diagonal)

_center_: Illustration of an eigenstate localized on the crystal's edge (Haldane Model)

_right_: Illustration of an eigenstate localized on the crystal's edge (Kane-Mele Model) 




<img src="/images/band1.png" alt="band" width="300"/>



$^\star$
The crystal is uniform everywhere except at the dislocation, as expected. You can tell this from the uniform hexagon pattern everywhere except at the center of the crystal, which is on the dislocation line. 
Note that the locations of the sites drawn carry no meaning: only the connections are meaningful. (this was the simplest design choice for creating a dislocation on a computer:
create a perfect crystal, manipulate the connections, and don't worry about about drawing distances accurately since we only care about connections anyway).

