---
description: Functions to build, interpolate, and SVG paths made of Bèzier curves
---

## Examples

```tsx
import {move, curve, serialize} from "react-native-redash";

const Example = () => {
  const path = [
    move(0, 0),
    curve({
      c1: {
        x: 1,
        y: 0
      },
      c2: {
        x: 1,
        y: 1
      },
      to:  {
        x: 1,
        y: 0.5
      }
    }),
    close()
  ];
  const d = serialize(path);
  return (
    <Svg viewBox="0 0 1 1">
      <Path d={d} fill="cyan" />
    </Svg>
  );
}
```

## `move(x, y)`
Returns a Bèzier curve command.

## `cuve({c1: {x, y}, c2: {x, y}, to: {x, y}})`

Returns a Bèzier curve command.

## `close()`

Returns a close command.

## `serialize(path)`

Serialize a path into an SVG path string.