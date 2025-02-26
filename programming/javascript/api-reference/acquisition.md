---
layout: default-layout
title: Dynamsoft Camera Enhancer JavaScript API - Main Page
description: This is the main page of Dynamsoft Camera Enhancer JavaScript SDK Acquisition.
keywords: camera enhancer, acquisition, javascript, js
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: Acquisition
---

# Frame Acquisition

<!--

| [refreshInterval](#singleframemode) | Returns or sets how often the buffer is refreshed when the buffer is full. |
| [croppingRegions](#singleframemode) | Returns or sets a few regions that the DCE instance will enumerate when cropping consecutive frames. |
| [croppingRegionIndex](#singleframemode) | Returns or sets which of the cropping regions is to be used in cropping the next frame. |
-->


| API Name | Description |
|---|---|
| [setScanRegion()](#setscanregion) | Specifies which part of the original video is considered when processing frames. |
| [getScanRegion()](#getscanregion) | Returns the scan region. |
| [getFrame()](#getframe) | Returns a `DCEFrame` object which contains the image data of the latest frame from the video input. |
| [getFrameFromBuffer()](#getframefrombuffer) | Returns a `DCEFrame` object which contains the image data of the latest buffered frame. |
| [startFetchingLoop()](#startfetchingloop) | Starts a fetching loop that continuously put frames in a buffer. |
| [stopFetchingLoop()](#stopfetchingloop) | Stops the fetching loop. |
| [isFetchingLoopStarted()](#isfetchingloopstarted) | Returns the state of the fetching loop. |
| [maxNumberOfFramesInBuffer](#maxnumberofframesinbuffer) | Sets or returns how many frames can be buffered. |
| [numberOfFramesInBuffer](#numberofframesinbuffer) | Returns how many frames there are in the buffer. |
| [loopInterval](#loopinterval) | Returns or sets the start time of the next fetch operation. |
| [singleFrameMode](#singleframemode) | Returns or sets whether to enable the singe-frame mode. |


## setScanRegion

Specifies which part of the original video is considered when processing frames.

```typescript
setScanRegion(region: Region): void;
```

**Parameters**

`region`: a `Region` object that specifies a part of the video.

**Return value**

None.

**Code Snippet**

```js
let region = {
	regionLeft: 25,
	regionTop: 25, 
	regionRight: 75, 
	regionBottom: 75, 
	regionMeasuredByPercentage: true
};
enhancer.setScanRegion(region); 
```

**See also**

* [Region](interface/region.md)

## getScanRegion

Returns the scan region.

```typescript
getScanRegion(): Region;
```

**Parameters**

None.

**Return value**

A `Region` object which specifies the scan region.

**Code Snippet**

```js
let region = enhancer.getScanRegion();
```

**See also**

* [Region](interface/region.md)

## getFrame

Returns a `DCEFrame` object which contains the image data of the latest frame from the video input.

```typescript
getFrame(): DCEFrame;
```

**Parameters**

None.

**Return value**

A `DCEFrame` object which contains the image data of the frame and related information.

**Code Snippet**

```js
let frameData = enhancer.getFrame();
document.body.appendChild(frameData.canvas);
```

**See also**

* [DCEFrame](interface/dceframe.md)

## getFrameFromBuffer

Returns a `DCEFrame` object which contains the image data of the latest buffered frame.

```typescript
getFrameFromBuffer(): DCEFrame;
```

**Parameters**

None.

**Return value**

A `DCEFrame` object which contains the image data of the frame and related information.

**Code Snippet**

```js
let frameData = enhancer.getFrameFromBuffer();
document.body.appendChild(frameData.canvas);
```

**See also**

* [DCEFrame](interface/dceframe.md)

## startFetchingLoop

Starts a fetching loop that continuously put frames in a buffer.

```typescript
startFetchingLoop(): void;
```

**Parameters**

None.

**Return value**

None.

## stopFetchingLoop

Stops the fetching loop and clears the frames buffer.

```typescript
stopFetchingLoop(): void;
```

**Parameters**

None.

**Return value**

None.

## isFetchingLoopStarted

Returns the state of the fetching loop.

```typescript
isFetchingLoopStarted(): Boolean;
```

**Parameters**

None.

**Return value**

None.

## maxNumberOfFramesInBuffer

Sets or returns how many frames can be buffered.

```typescript
maxNumberOfFramesInBuffer: number;
```

## numberOfFramesInBuffer

Returns how many frames there are in the buffer.

```typescript
readonly numberOfFramesInBuffer: number;
```

## loopInterval

Returns or sets the start time of the next fetch operation.

```typescript
loopInterval: number;
```
<!--
## refreshInterval

Returns or sets how often the buffer is refreshed when the buffer is full. Allowed values are 
* -1: when the buffer is full, do nothing at the next loop; 
* 0: when the buffer is full, refresh it (fetch a new image and append it) at the next loop;
* a natural number: sets a timer that starts as soon as the buffer is full, when the timer expires, a new frame is fetched and appended to the image buffer

```typescript
refreshInterval: number;
```


## croppingRegions

Returns or sets a few regions that the DCE instance will enumerate when cropping consecutive frames.  These regions are based on the original video size.

```typescript
croppingRegions: Array<Region>;
```

**See also**

* [Region](interface/region.md)

## croppingRegionIndex

Returns or sets which of the cropping regions is to be used in cropping the next frame. If not specified, the next region in line will be applied.

```typescript
croppingRegionIndex: number;
```

-->

## singleFrameMode

Returns or sets whether to enable the singe-frame mode. When the single-frame mode is enabled, the video will not stream in the built-in UI of the library. Instead, the user can click the UI to invoke the system camera interface to catch a frame or select an existing image from the device storage.

To get the actual data, add a event handler to the event 'singleFrameAcquired'.

```typescript
singleFrameMode: boolean;
```

**Code Snippet**

```js
let pEnhancer = null;
(async () => {
    let enhancer = await (pEnhancer = pEnhancer || Dynamsoft.DCE.CameraEnhancer.createInstance());
    enhancer.on('singleFrameAcquired', frame => {
        document.body.appendChild(frameData.canvas);
    });
    enhancer.singleFrameMode = true;
    await enhancer.open();
})();
```
