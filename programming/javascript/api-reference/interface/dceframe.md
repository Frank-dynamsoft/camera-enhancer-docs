---
layout: default-layout
title: Dynamsoft Camera Enhancer JavaScript API - Interface DCEFrame
description: This page shows the DCEFrame Interface of Dynamsoft Camera Enhancer JavaScript SDK.
keywords: DCEFrame, CameraEnhancer, api reference, javascript, js
needAutoGenerateSidebar: false
noTitleIndex: true
breadcrumbText: DCEFrame
---

# DCEFrame

`interface` DCEFrame

* canvas: `HTMLCanvasElement`

  A canvas element that holds the image data of the frame.

* data: `Uint8Array | Uint8ClampedArray | File`

  The raw image data.

* region: `Region`

  The region based on which the original frame is cropped.

* croppingRegionIndex: `number`

  The index of the region  

* sx: `number`

  The horizontal coordinate of the upper left point of the `data` on the original frame. If the frame was not cropped, the coordinate is 0.

* sy: `number`

  The vertical coordinate of the upper left point of the `data` on the original frame. If the frame was not cropped, the coordinate is 0.

* width: `number`

  The width of the image data.

* height: `number`

  The height of the image data.

* timeSpent: `number`

  The time in miniseconds spent in acquiring the frame.

* timeStamp: `number`

  The timeStamp at which point the frame acquisition finished.
