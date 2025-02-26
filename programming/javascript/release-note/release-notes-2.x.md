---
layout: default-layout
title: Dynamsoft Camera Enhancer - JavaScript 2.x Release Notes 
description: This is the Release Notes page for Dynamsoft Camera Enhancer JavaScript SDK.
keywords:  camera enhancer, release notes, javascript
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: v2.x Release Notes
---

# Release Notes - JavaScript 2.x

## 2.1.0 (01/20/2022)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

{%- include release-notes/product-highlight-2.1.0.md -%}

<div class="fold-panel-end"></div>

### Changelog

#### New

* Added methods `getScanRegion()` and `setScanRegion()` to control which part of the original video frames are cropped when acquiring frames for a 3rd party application to use.
* Added method `setScanRegionMaskStyle()` to set the style of the indicator for the scan region.
* Added method `getVisibleRegion()` to return which part of the original video frames are currently visible in the video element.
* Added methods `startFetchingLoop()`, `stopFetchingLoop()`,`isFetchingLoopStarted()` and `getFrameFromBuffer()` plus properties `maxNumberOfFramesInbuffer`, `numberOfFramesInBuffer` and `loopInterval` to control the continuous fetching of frames into the buffer.
* Added methods `getFocus()` and `setFocus()` to control the camera focus.
* Added methods `setVideoFit()` and `getVideoFit()` to control the fitting style of the video element.
* Added the feature to display a view decorator with the methods `getViewDecorator()` and `setViewDecorator()`. Also, added methods `setViewDecoratorLineWidth()`, `setViewDecoratorStrokeStyle()`, `setViewDecoratorFillStyle()` and `setViewDecoratorMaskFillStyle()` to control the style of the view decorator.
* Added method `addScanRegionOverlayCanvas()` to return a canvas above the video stream for users to draw on.
* Added property `singelFrameMode` to handle the situation where no camera is available.
* Added property `ifSkipCameraInspection` to skip camera inspection upon initialization to save time.
* Added property `ifSaveLastUsedCamera` to keep track of last used camera.
* Added methods `on()` and `off()` to control event binding and unbinding.
* Added method `dispose()` to releases all resources used by a CameraEnhancer instance.

## 2.0.3 (10/29/2021)

* Fixed a bug that caused compiler errors in frameworks such as Angular, React, and Vue.

## 2.0.1 (10/26/2021)

* Improved the frame buffer mechanism.

## 2.0.0 (10/20/2021)

* [Well-wrapped APIs]({{ site.js-api }}) to control cameras based on the [MediaDevices](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices) interface.
* Automatic selection of the optimal camera to use.
* Built-in user interface for fast interaction.
* Built-in compatibility mode, suitable for scenes where no camera is available.
* Built-in frame buffer mechanism to save time for the application(s) making use of the video frames.
* Flexible frame acquisition methods, allowing automatic or manual interaction.
