# BlackHoleShader

This is a black hole shader for Unity. Because it is performed by ray tracing, it conforms to the actual appearance of the black hole. 
The shader also condsidered the gravity redshift effect which is in theory caused by the differences of gravitational force between the observer and the light source.

<p align="center">
  <img width="800px" src="https://github.com/ReanSchwarzer1/Cygnus-X1/blob/main/Unity%20Sim%20of%20a%20Black%20Hole/Black%20Hole%20SSERD/BBH.PNG">
</p>

## Parameters
| parameter | description |
| --- | --- |
| Quad Scale | If the black hole goes out of the drawing, please enlarge this. |
| Speed Of Light | Speed Of Light (m / s). The default value is 1. |
| Schwarzschild Radius | If this value is changed significantly, fine tuning of other parameters may be necessary. |
| N Steps | Number of steps in solving differential equation. Increasing this value makes the black hole visible from far away. |
| Step Size | Step size in solving differential equation. Reducing this value improves accuracy but slows down the calculation. |
| Escape Velocity | When the speed of light exceeds this speed, light is considered to have escaped from the gravity of the black hole. This is the ratio to the speed of light. |
| Max Winding Of Light | Maximum winding number of light around the black hole. When this is exceeded, the calculation will be stopped. |
| Ring Radius | Outer radius of accretion disc. |
| Redshift Texture | Lookup texture to represent gravity redshift. |
| N Divisions Of r | Number of divisions of disk noise in the r direction. |
| N Divisions Of phi | Number of divisions of disk noise in the phi direction. |
| sigma | Variance of Gaussian blur. |
| Step Width | Sampling step width of Gaussian blur. |
| Threshold | Threshold of bloom. |
| Suppression | Suppression of bloom. |

## Redshift Texture
Redshift texture is a lookup texture for gravitational redshift.
The horizontal axis is 3a / R, and the vertical axis is a / r0.
Where R, r0 are the position (radius) of the light source and the position (radius) of the observer.
To generate this texture, use the python notebook.
Please install the following python packages, set the parameters, and run the notebook.

Used values of Cygnus X1 to generate the redshift texture.

### Requirements
* Python3
* Jupyter Notebook
* Numpy
* Scipy
* Matplotlib
* Pillow
To run the notebook and generate the textures.

### Color Matching Functions
Downloaded data of 2-deg XYZ CMFs [here](http://cvrl.ucl.ac.uk/cmfs.htm). Selected 0.1mm as step size and csv as format.
### Parameters
| parameter | description |
| --- | --- |
| size | Size of texture. If you increase this, the calculation will be slower. |
| temperature | Temperature inside the accretion disc. Black holes are actually very hot, but if set as so, they maybe look bad. |
| base_temperature | Base temperature of color temperature. The light is white at this temperature. |



Thanks to conjLob for providing the shader code.










