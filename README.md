# OptiX-PathTracer-Indirect-Lighting
Extra Implementation Results for [UCSD CSE 168 Rendering](http://cseweb.ucsd.edu/~viscomp/classes/cse168/sp20/168.html) assignments.

## Importance Sampling
- Implement Cosine/BRDF importance sampling as following commands:
 ```
 importancesampling <cosine/brdf>
 ```
 
Cornell Simple             | Cosine Importance Sampling | BRDF Importance Sampling
:-------------------------:|:--------------------------:|:-------------------------:
![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/importancesampling/cornellSimple.png)  |  ![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/importancesampling/cornellSimpleCosine.png) |  ![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/importancesampling/cornellSimpleBRDF.png)
Bias 11.4 / Variance 5507.3|  Bias 6.0 / Variance 3952.8|  Bias 5.4 / Variance 3900.4

Cornell NEE                | Cosine Importance Sampling | BRDF Importance Sampling
:-------------------------:|:--------------------------:|:-------------------------:
![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/importancesampling/cornellNEE.png)  |  ![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/importancesampling/cornellNEECosine.png) |  ![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/importancesampling/cornellNEEBRDF.png)
Bias 0.0 / Variance 189.4  |  Bias 0.0 / Variance 94.7  |  Bias 0.0 / Variance 88.3

Cornell RR                 | Cosine Importance Sampling | BRDF Importance Sampling
:-------------------------:|:--------------------------:|:-------------------------:
![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/importancesampling/cornellRR.png)  |  ![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/importancesampling/cornellRRCosine.png) |  ![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/importancesampling/cornellRRBRDF.png)
Bias 0.1 / Variance 325.5  |  Bias ? / Variance ?       |  Bias ? / Variance ?

## Separate Direct and Indirect Lighting
