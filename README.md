General information about the CTL course available at https://ctl.polyphys.mat.ethz.ch/

# :wave: PROJECT Shortest path

Shortest paths play a role in the mechanical behavior of entangled polymers. Envision a box that contains hundreds or thousands of linear polymers, where each polymer is represented by a path (embedded in *D* dimensions) with *n+1* nodes (monomers) and *n* undirected edges (bonds) connecting adjacent nodes. The entanglement network is then usually constructed as follows: Fix all terminal nodes of all polymers in space, and shorten all polymer contours until the total contour length of all the polymeric paths reached a global minimum. During the shortening process, the polymers are not allowed to cross each other, while polymers might cross themselves. 

## Shortest path in 2D

Here we first focus on a related but simpler *D=2*-dimensional problem. 

1. Load a configuration from the DATA directory. The data format is described there along with a function *load_configuration(filename)* that you can use to load a configuration (single polymer + obstacles). 
2. Visualize the situation (polymer plus obstacles). 
3. Keep the two terminal nodes of the polymer in place, and maximally shorten the polymer contour length, while the polymer is not allowed to cross any of the obstacles. 
4. Calculate the final polymer contour length (*L*<sub>pp</sub>), known as the length of the shortest (or primitive) path, the end-to-end distance *R* of the polymer, and the number of 'kinks' (*Z*) on the shortest contour (known as number of entanglements; to this end you need to define a 'kink'). In the figure below, the red contour is the shortest path. It seems to exhibit *Z*=7 kinks.
5. Instead of operating on the configuration files provided in the DATA directory: Generate a single random path with *n+1* nodes and *n* randomly oriented bonds with identical length *b*, where the first node is placed at the origin, and all nodes and bonds residing in the *x*-*y*-plane. Generate *M* random positions within a square of side length *2nb*, centered at the origin, and contained in the *x*-*y*-plane. These random positions serve as obstacles (see figure below for *n*=19 bonds, only a part of all the obstacles is shown). 
6. Fix *b=1*, *n=10* or *n=100* and study the effect of *M* on *Z* and *L*<sub>pp</sub>. Plot the mean squared end-to-end distance $\langle$ *R*<sup>2</sup> $\rangle$ of the polymer versus *n* at fixed *b=1* to find the exponent $\nu$ in the relationship $\langle$ *R*<sup>2</sup> $\rangle$ = (*n*$^{\nu}$*b*)<sup>2</sup>. 

<img src="http://www.complexfluids.ethz.ch/images/PROJECT-shortest-path.png">

 

## Shortest path in 3D

Similar as before, but 
1. the polymer with *n* randomly oriented bonds of identical length *b* is generated in 3D. 
2. The *M* point-like obstacles are replaced by *M* random 3D walks with *n* bonds (bond length *b*). 
3. Keep the two terminal nodes of the polymer in place (also keep all the *M* random walks immobile), and maximally shorten the polymer contour length, while the polymer is not allowed to cross any of the random walks. 
4. As for the 2D case: Calculate the final polymer contour length (*L*<sub>pp</sub>), known as the length of the shortest (or primitive) path, the end-to-end distance *R* of the polymer, and the number of 'kinks' (*Z*) on the shortest contour (known as number of entanglements; to this end you need to define a 'kink'). 
5. The following task goes beyond the scope of this course, but the full entanglement analysis of a polymeric system (such as a polymer melt) considers all polymers to be mobile, and one has to find the shortest multiple disconnected path, while chain ends are fixed.  
