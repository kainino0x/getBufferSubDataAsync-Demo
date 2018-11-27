# [Non-blocking getBufferSubData Picking Demo](https://kainino0x.github.io/getBufferSubDataAsync-Demo/)

This demonstrates the use of the new *nonblocking* use pattern for
`getBufferSubData` in WebGL 2.0 implementations and provides a performance
comparison against synchronous picking methods.

Requires WebGL 2.0. Performance improvements are expected to be greatest in Chromium.

This demo is based on the Three.js demo
[interactive cubes (gpu)](https://threejs.org/examples/webgl_interactive_cubes_gpu.html).

## Performance

On Debian, NVIDIA Quadro K620, 384.111, with:
* Chrome Stable xx.x.xxxx.xx (separate GPU process)
* Firefox Developer Edition xx.xxxx (no separate GPU process)

**TODO:** These numbers need to be re-captured after correcting the timing calls.

| Timing results                             | readPixels (sync) | readPixels (async) + getBufferSubData (sync) | readPixels (async) + fence + getBufferSubData |
|:------------------------------------------ | -----------------:| --------------------------------------------:| ---------------------------------------------:|
| Chrome:  blocking time in read operation   |           xxxx ms |                                      xxxx ms |                                       xxxx ms |
| Chrome:  pick triggered to render complete |           xxxx ms |                                      xxxx ms |                                       xxxx ms |
| Firefox: blocking time in read operation   |           xxxx ms |                                      xxxx ms |                                       xxxx ms |
| Firefox: pick triggered to render complete |           xxxx ms |                                      xxxx ms |                                       xxxx ms |
