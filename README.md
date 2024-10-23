## Mapbox GL Draw Rectangle Mode With Snap

A custom mode for MapboxGL Draw to draw rectangles that adds the functionality of keeping the rectangle's shape when adjusting a corner of the drawn rectangles.
This mode is compatible with @mapbox/mapbox-gl-draw@1.4.0 and above.
Original inspiration comes from this package, which hasn't been mantained for the last 4 years:
https://github.com/thegisdev/mapbox-gl-draw-rectangle-mode

This version has been updated from teamookla's version (https://github.com/teamookla/mapbox-gl-draw-rectangle-mode) to work with a snap mode library created mhsattarian (https://github.com/mhsattarian/mapbox-gl-draw-snap-mode?tab=readme-ov-file)

### Usage

```js
import MapBoxDraw, { modes as defaultModes } from '@mapbox/mapbox-gl-draw'
import SnapRectangleMode from 'mapbox-gl-draw-rectangle-snap-mode';
import {
  SnapDirectSelect,
  SnapLineMode,
  SnapModeDrawStyles,
  SnapPointMode,
  SnapPolygonMode,
} from 'mapbox-gl-draw-snap-mode'


const customOverrideModes = {
  draw_rectangle: SnapRectangleMode
  draw_point: SnapPointMode,
  draw_polygon: SnapPolygonMode,
  draw_line_string: SnapLineMode,
  direct_select: SnapDirectSelect,
  static: StaticMode,
}

const draw = new MapboxDraw({
  modes: { 
    ...defaultModes,
    ...customOverrideModes
  }
});

draw.changeMode('draw_rectangle');
```

Once a rectangle is created, 1 event is fired:
- `draw.create` with the created rectangle

### Build

`yarn build` will do it.

### License
MIT
