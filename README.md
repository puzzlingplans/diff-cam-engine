# diff-cam-engine

Core engine for building motion detection web apps.

### Notes

`diff-cam-engine.js` is the main file. It provides a `DiffCamEngine` object that does all the heavy lifting. This includes accessing the webcam, capturing snapshots, and evaluating any motion that has taken place.

You'll almost certainly want to use the `adapter.js` shim, which is redistributed within this repo. It's also available here: https://github.com/webrtc/adapter.

Detailed documentation is coming soon. For now, check out `example.html` for a very basic example. If you're trying to run this locally, check out this guide: https://github.com/mrdoob/three.js/wiki/How-to-run-things-locally.
