# OptiX-PathTracer-Indirect-Lighting
Extra Implementation Results for [UCSD CSE 168 Rendering](http://cseweb.ucsd.edu/~viscomp/classes/cse168/sp20/168.html) assignments.

## Importance Sampling
- Implement Cosine/BRDF importance sampling as following commands:
 ```
 importancesampling <cosine/brdf>
 ```
 
Cornell Simple             | Cosine Importance Sampling | BRDF Importance Sampling
:-------------------------:|:--------------------------:|:-------------------------:
![](https://github.com/yuyingyeh/OptiX-PathTracer/blob/master/rv/direct3x3_ori.png)  |  ![](https://github.com/yuyingyeh/OptiX-PathTracer/blob/master/rv/direct3x3_center.png) |  ![](https://github.com/yuyingyeh/OptiX-PathTracer/blob/master/rv/direct3x3_analytic.png)
Bias ? / Variance ?      |  Bias ? / Variance ? |  Bias ? / Variance ?

## Separate Direct and Indirect Lighting
