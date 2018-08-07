# [getBufferSubDataAsync Picking Demo](https://kainino0x.github.io/getBufferSubDataAsync-Demo/)

This demonstrates the use of the new *nonblocking* use pattern for
`getBufferSubData` in WebGL 2.0 implementations and provides a performance
comparison against synchronous picking methods.

Requires WebGL 2.0. Performance improvements are expected to be greatest in Chromium.

This demo is based on the Three.js demo
[interactive cubes (gpu)](https://threejs.org/examples/webgl_interactive_cubes_gpu.html).

## Performance

On Debian, NVIDIA Quadro K620, 384.111, with:
* Chrome Stable 68.0.3440.84 (separate GPU process)
* Firefox Developer Edition 62.0b14 (no separate GPU process)

| Timing results                             | readPixels (sync) | readPixels (async) + getBufferSubData (sync) | readPixels (async) + fence + getBufferSubData |
|:------------------------------------------ | -----------------:| --------------------------------------------:| ---------------------------------------------:|
| Chrome:  time in synchronous picking code  |           1.95 ms |                                      1.97 ms |                                       0.19 ms |
| Chrome:  pick triggered to render complete |           2.05 ms |                                      2.04 ms |                                       5.30 ms |
| Firefox: time in synchronous picking code  |           0.85 ms |                                      0.85 ms |                                       0.37 ms |
| Firefox: pick triggered to render complete |           2.40 ms |                                      2.40 ms |                                       5.80 ms |
