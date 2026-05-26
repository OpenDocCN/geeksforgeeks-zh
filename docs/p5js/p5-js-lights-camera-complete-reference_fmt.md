# p5.js 灯光与摄像机完整参考

> 原文：[https://www.geeksforgeeks.org/p5-js-lights-camera-complete-reference/](https://www.geeksforgeeks.org/p5-js-lights-camera-complete-reference/)

## `camera()` 功能

`camera()` 功能设置三维草图的相机位置。它的参数定义了相机的位置、草图的中间（相机指向的位置）和向上的方向（相机的方向）。该功能模拟摄像头的运动，可以从各个角度观察物体。

**语法：**

```
new camera([x], [y], [z], [centerX], [centerY], [centerZ], [upX], [upY], [upZ])
```

## `lights()` 功能

`lights()` 功能设置默认的环境光和方向光。默认值为环境光 `(128, 128, 128)` 和方向光 `(128, 128, 128, 0, 0, -1)`。

**语法：**

```
lights()
```

## 互动

*   [p5.js `orbitControl()` 功能](https://www.geeksforgeeks.org/p5-js-orbitcontrol-function/)
*   [p5.js `noDebugMode()` 功能](https://www.geeksforgeeks.org/p5-js-nodebugmode-function/)

## 光

*   [p5.js `ambientLight()` 功能](https://www.geeksforgeeks.org/p5-js-ambientlight-function/)
*   [p5.js `specularColor()` 功能](https://www.geeksforgeeks.org/p5-js-specularcolor-function/)
*   [p5.js `directionalLight()` 功能](https://www.geeksforgeeks.org/p5-js-directionallight-function/)
*   [p5.js `pointLight()` 功能](https://www.geeksforgeeks.org/p5-js-pointlight-function/)
*   [p5.js `lights()` 功能](https://www.geeksforgeeks.org/p5-js-lights-function/)
*   [p5.js `lightFalloff()` 功能](https://www.geeksforgeeks.org/p5-js-lightfalloff-function/)
*   [p5.js `noLights()` 功能](https://www.geeksforgeeks.org/p5-js-nolights-function/)

## 材料

*   [p5.js `normalMaterial()` 功能](https://www.geeksforgeeks.org/p5-js-normalmaterial-function/)
*   [p5.js `texture()` 功能](https://www.geeksforgeeks.org/p5-js-texture-function/)
*   [p5.js `ambientMaterial()` 功能](https://www.geeksforgeeks.org/p5-js-ambientmaterial-function/)
*   [p5.js `emissiveMaterial()` 功能](https://www.geeksforgeeks.org/p5-js-emissivematerial-function/)
*   [p5.js `specularMaterial()` 功能](https://www.geeksforgeeks.org/p5-js-specularmaterial-function/)
*   [p5.js `shininess()` 功能](https://www.geeksforgeeks.org/p5-js-shininess-function/)

## 照相机

*   [p5.js `perspective()` 功能](https://www.geeksforgeeks.org/css-perspective-function/)
*   [p5.js `createCamera()` 功能](https://www.geeksforgeeks.org/p5-js-createcamera-function/)
*   `p5.Camera`
    *   [p5.Camera `pan()` 方法](https://www.geeksforgeeks.org/p5-camera-pan-method/)
    *   [p5.Camera `move()` 方法](https://www.geeksforgeeks.org/p5-camera-move-method/)
    *   [p5.Camera `tilt()` 方法](https://www.geeksforgeeks.org/p5-camera-tilt-method/)
    *   [p5.Camera `setPosition()` 方法](https://www.geeksforgeeks.org/p5-camera-setposition-method/)
*   [p5.js `setCamera()` 功能](https://www.geeksforgeeks.org/p5-js-setcamera-function/)