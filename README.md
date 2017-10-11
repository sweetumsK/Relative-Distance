# Relative-Distance  
  
|         |   prev    |       now       |  
| ------- |:---------:|:---------------:|  
|Camera   |   0,0,0   |    xca,yca,zca  |  
|P(g)     |   x,y,z   |       x,y,z     |  
|P(i)     |    X,Y    |       X',Y'     |  
  
## Rules:  
1. "g" means "global".  
2. "i" means "image".  
3. image's center point is (Xcen, Ycen)  
  
## Assumption:  
1. previous position of camera is (0,0,0)  
2. the focus length of camera is f  
  
## Known:  
1. P(i) (X,Y) & (X',Y')  
2. P(g) is fixed  
  
## Solution:  
  x / z = (X-Xcen) / f -> x = (X-Xcen) / f * z  
  y / z = (Y-Ycen) / f -> y = (Y-Ycen) / f * z  
    
  (x-xca) / (z-zca) = (X'-Xcen) / f -> x - xca = (X'-Xcen) / f * (z-zca)  
  >>`xca = x - (X'-Xcen) / f * (z-zca) = (X-Xcen) / f * z - (X'-Xcen) / f * (z-zca)`  
    
  (y-yca) / (z-zca) = (Y'-Ycen) / f -> y - yca = (Y'-Ycen) / f * (z-zca)  
  >>`yca = y - (Y'-Ycen) / f * (z-zca) = (Y-Ycen) / f * z - (Y'-Ycen) / f * (z-zca)`  
  
This time, we have the Camera's postion by using two parameters (z and zca)  
  
---  
If we have two points, we can use the equation of zca to get the relation between z of two points.  
## Situation:  
There are two points named P and Q.  
>>(XP-Xcen) / f * zP - (XP'-Xcen) / f * (zP-zca) = (XQ-Xcen) / f * zQ - (XQ'-Xcen) / f * (zQ-zca)  
>>(YP-Ycen) / f * zP - (YP'-Ycen) / f * (zP-zca) = (YQ-Ycen) / f * zQ - (YQ'-Ycen) / f * (zQ-zca)  

  ### Set:  
  >g(A*) = (A* - Acen) / f  
  
  
  g(XP) * zP - g(XP') * (zP-zca) = g(XQ) * zQ - g(XQ') * (zQ-zca)  
  g(YP) * zP - g(YP') * (zP-zca) = g(YQ) * zQ - g(YQ') * (zQ-zca)  
  [g(XP) - g(XP')] * zP - [g(XQ) - g(XQ')] * zQ = [g(XQ') - g(XP')] * zca  
  [g(YP) - g(YP')] * zP - [g(YQ) - g(YQ')] * zQ = [g(YQ') - g(YP')] * zca  
  >>[g(YQ') - g(YP')] * {[g(XP) - g(XP')] * zP - [g(XQ) - g(XQ')] * zQ} = 
  >>[g(XQ') - g(XP')] * {[g(YP) - g(YP')] * zP - [g(YQ) - g(YQ')]* zQ}  
  
  >>{[g(YQ') - g(YP')] * [g(XP) - g(XP')] - [g(XQ') - g(XP')] * [g(YP) - g(YP')]} * zP = 
  >>{[g(YQ') - g(YP')] * [g(XQ) - g(XQ')] - [g(XQ') - g(XP')] * [g(YQ) - g(YQ')]} * zQ  
  
rate?!  
zP / zQ =  
{[g(YQ') - g(YP')] * [g(XQ) - g(XQ')] - [g(XQ') - g(XP')] * [g(YQ) - g(YQ')]} /  
{[g(YQ') - g(YP')] * [g(XP) - g(XP')] - [g(XQ') - g(XP')] * [g(YP) - g(YP')]}  
