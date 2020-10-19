---
description: Color interpolations and more
---

# Colors

## `Color`

TypeScript type to define an animation value as color.

```typescript
const color = useDerivedValue(() => mixColor(progress.value, "blue", "red"));
```

## `interpolateColor()`

Interpolate an animation value into a color. The color can be interpolated in the RGB or HSV color space \(default is RGB\).

```typescript
  const theta = useSharedValue(Math.PI);
  const backgroundColor = useDerivedValue(() => {
    return interpolateColor(
      theta.value,
      [0, Math.PI, Math.PI * 2],
      ["#ff3884", StyleGuide.palette.primary, "#38ffb3"]
      ColorSpace.HSV // default is RGB
    );
  });
```

## `mixColor()`

Identical to `interpolateColor()` but with an animation value that goes from 0 to 1.

```typescript
const backgroundColor = useDerivedValue(() =>  
  mixColor(progress.value, "#ff3884", "#38ffb3")
);
```

## `hsv2color()`

Convert an HSV into an RGB color.

## `colorForBackground()`

Returns black or white depending on the value of the background color.

