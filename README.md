# Relative-Distance  
  
| Postion |   prev    |        now      |  
| ------- |:---------:| ---------------:|  
|Camera   |   0,0,0   |    xca,yca,zca  |  
|P|g      |   x,y,z   |       x,y,z     |  
|P|i      |    X,Y    |       X',Y'     |  
  
## Rules:  
1. "g" means "global".  
2. "i" means "image".  
3. image's center point is (Xcen, Ycen)  
  
## Assumption:  
1. previous position of camera is (0,0,0)  
2. the focus length of camera is f  
  
## Known:  
1. P|i (X,Y) & (X',Y')  
2. P|g is fixed  
  
## Solution:  
  x / z = (X-Xcen) / f -> x = (X-Xcen) / f * z  
  y / z = (Y-Ycen) / f -> y = (Y-Ycen) / f * z  
  
  (x-xca) / (z-zca) = (X'-Xcen) / f -> x - xca = (X'-Xcen) / f * (z-zca)  
  xca = x - (X'-Xcen) / f * (z-zca) = (X-Xcen) / f * z - (X'-Xcen) / f * (z-zca)  
  (y-yca) / (z-zca) = (Y'-Ycen) / f -> y - yca = (Y'-Ycen) / f * (z-zca)  
  yca = y - (Y'-Ycen) / f * (z-zca) = (Y-Ycen) / f * z - (Y'-Ycen) / f * (z-zca)  
  
This time, we have the Camera's postion by using two parameters _z and zca  
