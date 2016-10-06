# [getBufferSubDataAsync Picking Demo](https://kainino0x.github.io/getBufferSubDataAsync-Demo/)

This demo demonstrates the use of the proposed `getBufferSubDataAsync` method
in WebGL 2 and provides a performance comparison against synchronous picking
methods.

Requires WebGL 2.0 and, currently, a patched build of Chromium.

It is based on the Three.js demo
[interactive cubes (gpu)](https://threejs.org/examples/webgl_interactive_cubes_gpu.html).

## Performance

On Chrome 55.0.2880.0 + [patch](https://codereview.chromium.org/2379203002/), Ubuntu 14.04, NVIDIA Quadro K620, 367.35.

| Timing results                    | readPixels (sync) | readPixels (async) + getBufferSubData (sync) | readPixels (async) + getBufferSubDataAsync |
|:--------------------------------- | -----------------:| --------------------------------------------:| ------------------------------------------:|
| time in synchronous picking code  |          27-31 ms |                                     27-31 ms |                                     0-1 ms |
| pick triggered to render complete |          27-31 ms |                                     27-31 ms |                                      17 ms |
