---
layout: default-layout
title: Dynamsoft Camera Enhancer - iOS 2.x Release Notes 
description: This is the documentation - iOS 2.x Release Notes page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, iOS 2.x Release Notes
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: iOS 2.x Release Notes
---

# Release Notes - iOS 2.x

## 2.1.1 (12/28/2021)

### New

- Added a new feature `SMART_TORCH`. Users can enable this feature via the method [`enableFeatures`]({{site.ios-api}}camera-enhancer.html#enablefeatures) by specifying `EnumSMART_TORCH`. When `SMART_TORCH` is enabled, a torch button will be displayed automatically when the environment light level is low. Users can click on the torch button to turn on/off the torchlight.
- Overwrite `DCECameraView` method [`setTorchButton`]({{site.ios-api-auxiliary}}dcecameraview.html#settorchbutton). Users can set the position, size and image of the torch button. The previous `setTorchButton` method is deprecated.

### Fixed

- Fixed a bug that might affect the processing speed.
- Fixed a bug that `enableFeatures` might not have effects.

## 2.1.0 (12/16/2021)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

{%- include release-notes/product-highlight-2.1.0.md -%}

<div class="fold-panel-end"></div>

### Changelog

#### New

- Added method [`setScanRegion`]({{site.ios-api}}camera-enhancer.html#setscanregion) and [`getScanRegion`]({{site.ios-api}}camera-enhancer.html#getscanregion) to [`CameraEnhancer`]({{site.ios-api}}camera-enhancer.html) class for users to set or get the region of interest. The scan region will determine how frames will be cropped.
- Added class [`iRegionDefinition`]({{site.ios-api-auxiliary}}region-definition.html). The class will be used to define the parameters for method [`setScanRegion`]({{site.ios-api}}camera-enhancer.html#setscanregion).
- Added property [`scanRegionVisible`]({{site.ios-api}}camera-enhancer.html#scanregionvisible) to control and check the visibility of the scan region.
- Added method [`setTorchButton`]({{site.ios-api-auxiliary}}dcecameraview.html#settorchbutton) to [`DCECameraView`]({{site.ios-api-auxiliary}}dcecameraview.html) class for users to set the position of the torch button. Property [`torchButtonVisible`]({{site.ios-api-auxiliary}}dcecameraview.html#torchbuttonvisible) is added to set and check the visibility of the torch button.
- Extended the JSON template of [`updateAdvancedSettingsFromFile`]({{site.ios-api}}camera-enhancer.html#updateadvancedsettingsfromfile) and [`updateAdvancedSettingsFromString`]({{site.ios-api}}camera-enhancer.html#updateadvancedsettingsfromstring). Added fast mode configuration parameters to the template.

## 2.0.0 (10/19/2021)

<div class="fold-panel-prefix"></div>

### Version Highlights <i class="fa fa-caret-down"></i>

<div class="fold-panel-start"></div>

{%- include release-notes/product-highlight-2.0.0.md -%}

<div class="fold-panel-end"></div>

### Changelog

#### Improved

- Updated the mechanism of the video buffer. The capability of real-time frame processing and transferring is improved.

#### Breaking Change(s)

- Added method [`initLicense`]({{site.ios-api}}camera-enhancer.html#initlicense) to replace `initLicenseFromDLS`.
- Upgraded the [`basic camera-control APIs`]({{site.ios-api}}camera-enhancer.html#basic-camera-control-methods).
- Upgraded the usage of [`camera enhancer features`]({{site.ios-api}}camera-enhancer.html#enhanced-features).
- Renamed class `CameraView` to [`DCECameraView`]({{site.ios-api-auxiliary}}dcecameraview.html). The features of the class are extended as well.
- Renamed class `Frame` to [`DCEFrame`]({{site.ios-api-auxiliary}}dceframe.html). The features of the class are extended as well.
