# Case-ViewFactor-OpenFOAM-v2206
This is the OpenFoam v2206 seting of a Vacuum Radiation Test case

This is the case of a 2D thermally-driven square cavity with gray and diffuse walls. The case is solved in transient regime using the buoyantPimpleFoam solver. 


## Running case

The commands to run the case are:

1) faceAgglomerate

2) viewFactorsGen

3) buoyantPimpleFoam

Optional:

In case of modifying the mesh in the "blockMeshDict" file. The "boundary" file located in "constant/polyMesh/boundary" must be modified as indicated in the OpenFoam v2206 documentation, ie.:

     floor
     {
         type            wall;
         inGroups        2(wall viewFactorWall);
         nFaces          100;
         startFace       3100;
     }

And repeat the commands:

1) faceAgglomerate

2) viewFactorsGen

3) buoyantPimpleFoam

## Mesh

blocks
(
    hex (0 1 2 3 4 5 6 7) (80 80 1) 
    simpleGrading (
    			( (0.5 0.5 8) (0.5 0.5 0.125) )
   			( (0.5 0.5 8) (0.5 0.5 0.125) ) 
    			1
    		  )
);

