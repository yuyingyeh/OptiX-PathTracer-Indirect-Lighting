# OptiX-PathTracer-Indirect-Lighting
Extra Implementation Results for [UCSD CSE 168 Rendering](http://cseweb.ucsd.edu/~viscomp/classes/cse168/sp20/168.html) assignments.
1. Importance Sampling
2. Separate Direct and Indirect Lighting completely

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
Bias 0.1 / Variance 325.5  |  Bias 0.0 / Variance 166.9 |  Bias 0.0 / Variance 152.3

Dragon.                    | Cosine Importance Sampling | BRDF Importance Sampling
:-------------------------:|:--------------------------:|:-------------------------:
![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/importancesampling/dragon.png)  |  ![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/importancesampling/dragonCosine.png) |  ![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/importancesampling/dragonBRDF.png)
Bias 0.0 / Variance 15.1  |  Bias 0.0 / Variance 11.0   |  Bias 0.0 / Variance 8.9

## Separate Direct and Indirect Lighting
I use stratification for direct lighting only and avoid double computing initial direct lighting NEE sample. For the subsequent bounces, I use NEE as in the standard way. We can observe that the noise is largely reduced for direct lighting but only slightly reduced for combined image since it's still very noisy for indirect lighting. 

Cornell NEE                | Direct Only | Indirect Only
:-------------------------:|:--------------------------:|:-------------------------:
![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/separate/cornellNEE.png)  |  ![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/separate/cornellNEEDirectOnly.png) |  ![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/separate/cornellNEEIndirectOnly.png)
Bias 0.0 / Variance 189.4  |  -  |  -

Cornell NEE Separate       | Direct Only | Indirect Only
:-------------------------:|:--------------------------:|:-------------------------:
![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/separate/cornellNEESeparate.png)  |  ![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/separate/cornellNEESeparateDirectOnly.png) |  ![](https://github.com/yuyingyeh/OptiX-PathTracer-Indirect-Lighting/blob/master/separate/cornellNEESeparateIndirectOnly.png)
Bias 0.1 / Variance 183.4  |  -  |  -
