# diff-cam-engine

Core engine for building motion detection web apps.

### Usage

`diff-cam-engine.js` provides a `DiffCamEngine` object that does all the heavy lifting. This includes accessing the webcam, capturing snapshots, and evaluating any motion that has taken place.

You'll almost certainly want to use the `adapter.js` shim, which is available (and has instructions for direct linking) here: https://github.com/webrtc/adapter. Add it before `diff-cam-engine.js`.

With that in place, call `DiffCamEngine.init()` to initialize. This will set things up and ask the user for permission to access the webcam.

``` javascript
DiffCamEngine.init({
	// config options go here
});
```
Then call `start()` to begin the actual motion sensing. Important: do not call `start()` before `init()` has finished. It's a good idea to call `start()` from `initSuccessCallback()` (more on this later).

Call `stop()` to turn things off.

### Configuration

The following variables are passed into `init()` as an object of name/value pairs.

| Name | Default | Description |
| --- | --- | --- |
| video | internal &lt;video&gt; (not visible) | The &lt;video&gt; element for showing the live webcam stream |
| motionCanvas | internal &lt;canvas&gt; (not visible) | The &lt;canvas&gt; element for showing the visual motion heatmap |
| captureIntervalTime | 100 | Number of ms between capturing images from the stream |
| captureWidth | 640 | Width of captured images from stream |
| captureHeight | 480 | Height of capture images from stream |
| diffWidth | 64 | Width of (usually downsized) images used for diffing and showing motion |
| diffHeight | 48 | Height of (usually downsized) images used for diffing and showing motion |
| pixelDiffThreshold | 32 | Minimum difference in a pixel to be considered changed |
| scoreThreshold | 16 | Minimum number of changed pixels for an image to be considered as having motion |
| includeMotionBox | false | Flag to calculate and display on motionCanvas the bounding box of motion |
| includeMotionPixels | false | Flag to include data indicating all the changed pixels |

More documentation is coming soon. For now, check out my `diff-cam-scratchpad` repo for examples. If you're trying to run this locally, check out this guide: https://github.com/mrdoob/three.js/wiki/How-to-run-things-locally.
