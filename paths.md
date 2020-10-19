---
description: 'Functions to build, interpolate, and SVG paths made of Bèzier curves'
---

# Paths

## Examples

```typescript
import {move, curve, serialize} from "react-native-redash";

const Example = () => {
  const path = createPath({ x: 0, y: 0});
  addCurve(path, {
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
  });
  close(path);
  const d = serialize(path);
  return (
    <Svg viewBox="0 0 1 1">
      <Path d={d} fill="cyan" />
    </Svg>
  );
}
```

## `createPath(path, {x, y})`

Create a new path

## `addCurse(path, {c1: {x, y}, c2: {x, y}, to: {x, y}})`

Add a Bèzier curve command to a path.

## `close(path)`

Add a close command to a path.

## `parse(path)`

**⚠️ this function cannot run on the UI thread. It must be executed on the JS thread**

Parse an SVG path into a sequence of Bèzier curves. The SVG is normalized to have absolute values and to be approximated to a sequence of Bèzier curves.

## `serialize(path)`

Serialize a path into an SVG path string.

## `interpolatePath()`

Interpolate between paths.

```jsx
const progress = useSharedValue(0);
// ⚠️ parse() cannot be executed on the UI thread
const p1 =
  parse("M150,0 C150,0 0,75 200,75 C75,200 200,225 200,225 C225,200 200,150 0,150 ");
const p2 = parse(
  "M150,0 C150,0 0,75 200,75 C75,200 200,225 200,225 C225,200 200,150 0,150 ");
const animatedProps = useAnimatedProps(() => {
  const aPath = interpolatePath(progress.value, [0, 1], [p1, p2]);
  const d = serialize(d);
  return {
    d
  };
});
return <Path animatedProps={animatedProps} />;
```

## `mixPath()`

Interpolate two paths with an animation value that goes from 0 to 1.

```jsx
const progress = useSharedValue(0);
// ⚠️ parse() cannot be executed on the UI thread
const p1 =
  parse("M150,0 C150,0 0,75 200,75 C75,200 200,225 200,225 C225,200 200,150 0,150 ");
const p2 = parse(
  "M150,0 C150,0 0,75 200,75 C75,200 200,225 200,225 C225,200 200,150 0,150 ");
const animatedProps = useAnimatedProps(() => {
  const aPath = mixPath(progress.value, p1, p2);
  const d = serialize(d);
  return {
    d
  };
});
return <Path animatedProps={animatedProps} />;
```

## `getYForX`

Return the `y` value of a path given its `x` coordinate

```jsx
const p1 = parse(
  "M150,0 C150,0 0,75 200,75 C75,200 200,225 200,225 C225,200 200,150 0,150"
);
// 75
getYForX(p1, 200))
// ~151
getYForX(p1, 50)
```

