# [MJT Engine](https://github.com/mjt-engine) Magica Voxels Module

Javascript/Typescript Parser for MagicaVoxel .vox file format and other MagicaVoxel utilities

https://github.com/ephtracy/voxel-model/blob/master/MagicaVoxel-file-format-vox.txt

This is a fork/rewrite of https://github.com/kevzettler/parse-magica-voxel 

The target is modern ES6 browsers (which should work fine with node, ts-node, etc.. as well)

This fork currently improves on the original by:
- removing node dependencies (presently using Buffer pollyfill, possibly migrate to ArrayBuffer)
- updates code to typescript (WIP)
- works with Magica 99.6

Plans (might happen if I need this):
- write .vox files out from JSON format

## Install

```
pnpm install github:mjt-engine/magica-voxels
```

## Usage
see [examples](/example)

```typescript

import { MagicaVoxels } from "@mjt-engine/magica-voxels";

const ab = await (await fetch("voxel/test.vox")).arrayBuffer();

const parsed = MagicaVoxels.parse(ab);
console.log({ parsed });

```

### Result
```
{
  "VOX ": 150,
  "PACK": 1,
  "SIZE": {
    "x": 20,
    "y": 21,
    "z": 20
  },
  "XYZI": [
   {x, y, z, c},
   //... more voxels
  ],
  "RGBA": [
   {r,g,b,a},
   //... more rgba values
  ],
}       
```

### Thanks

Big thanks to @kevzettler https://github.com/kevzettler https://www.kevzettler.com for the original project this is based on

## Blame

Matt Taylor https://mjt.dev

## License

MIT


## Documentation

For detailed documentation, please visit the [project documentation](https://mjt-engine.github.io/magica-voxels).