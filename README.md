# PlotToData
Program that allows to extract the points of figures that are in image format. Practical tool to extract datasets from papers.

![imagen](https://user-images.githubusercontent.com/19601324/116791914-da0afe00-aa93-11eb-8ca9-e7ae9465272e.png)

[Download PlotToData.exe](https://github.com/EmilianoJan/PlotToData/releases/)


## Features:
1. Zoom and edit on the image
1. Axis configuration (linear, semi-logarithmic, logarithmic)
1. Saved in .mat, .csv, and NIST (.mtx) format
1. Matlab / Octave, and Python code automatic generation (using the matplotlib library)
1. Load images directly from clipboard
1. Multiplatform (on linux and mac systems it is required to install [Mono](https://www.monodevelop.com/download/))


## Usage tutorial:

First you must load or open the image from which you want to extract the points.


The next step is to configure the axes. To do this, click on the blue square. In light blue the end point of the axis is represented, while in dark blue the starting point. The points do not necessarily have to be located at the origin of the graph. Example following figure, however it is convenient that they cover as much of the graph as possible so that the error is as small as possible.
![imagen](https://user-images.githubusercontent.com/19601324/116791301-b2199b80-aa8f-11eb-8caa-07405d004388.png)

After establishing the positions of the axes, you must configure the initial and final values, the name of the axis and whether it is linear or logarithmic.

![imagen](https://user-images.githubusercontent.com/19601324/116791329-dd9c8600-aa8f-11eb-80b4-a4e66849563c.png)

Once completed, you can start adding data series by clicking "Add series". By clicking on the image, the points of that series will be added. Once all the points have been loaded, you must right click or ESC to exit the "adding points" mode.
![imagen](https://user-images.githubusercontent.com/19601324/116791380-3cfa9600-aa90-11eb-8084-93fbe052652f.png)


In case of having misconfigured the point of the series, you can zoom using the mouse scroll, click on the node and move it. If the displaced node is the first or last in the series, the "point aggregation" mode is entered. To move around the image you can use the central button to drag.

![imagen](https://user-images.githubusercontent.com/19601324/116791461-f0638a80-aa90-11eb-8059-4fa9cf519ecf.png)

Once all the data series have been added, the code can be generated by going to the "Code" tab. You can also save the data using the "Save" button. There are several possible save formats. If you choose to save in .csv or .mtx format, a file will be generated for each data series loaded.


To modify the properties of each of the parts, the displayed list can be used.

![imagen](https://user-images.githubusercontent.com/19601324/116791441-be522880-aa90-11eb-9716-d002aeab1579.png)

## Octave figure example 
![imagen](https://user-images.githubusercontent.com/19601324/116791974-51409200-aa94-11eb-9e91-15bfcacd39ff.png)
**code**
```matlab
% Loading series
Serie_1 = [ 0.0137533 0.06766498; 0.2598083 0.2899769; 0.973831 1.026347; 2.938465 2.958729; 9.97113 10.01057;]; 
LogSerie = [ 1.211121 0.2266482; 1.858014 0.6699489; 2.669801 1.037255; 4.153849 1.46789; 5.43495 1.721205; 6.677999 1.923857; 7.337576 2.012517; 8.466468 2.189837; 9.138729 2.2405; 9.944224 2.262753;]; 
figure % Generate plot
plot( Serie_1(:, 1), Serie_1(:, 2))
hold on
plot( LogSerie(:, 1), LogSerie(:, 2))
xlabel('X Axis')
ylabel('Y Axis')
title('Plot')
grid on
grid minor
legend('Serie 1' ,'LogSerie' ) 
```

## Python figure example 
**code**
```python
import numpy as np
import matplotlib.pyplot as plt

fig, ax = plt.figure()

# Loading series
Serie_1X = [ 0.03496503, 0.3496504, 0.8391609, 1.048951] 
Serie_1Y = [ 0.9752699, 1.95054, 5.921282, 9.996517] 
Serie_2X = [ 0.1048951, 0.2447552, 0.979021, 2.972028, 10.06993] 
Serie_2Y = [ 0, 0.2438175, 1.010101, 2.92581, 9.961686] 
Serie_3X = [ 1.258741, 1.993007, 2.727273, 4.86014, 7.412588, 9.93007] 
Serie_3Y = [ 0.2089864, 0.6617903, 0.9404389, 1.532567, 1.985371, 2.264019] 
ax.plot( Serie_1X , Serie_1Y, label= 'Serie 1')
ax.plot( Serie_2X , Serie_2Y, label= 'Serie 2')
ax.plot( Serie_3X , Serie_3Y, label= 'Serie 3')
ax.set_xlabel('X Axis')
ax.set_ylabel('Y Axis')
ax.set_title('Plot')
ax.grid(True)
plt.legend()
plt.show()

```

[Download PlotToData.exe](https://github.com/EmilianoJan/PlotToData/releases/)


