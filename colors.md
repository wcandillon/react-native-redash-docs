---
description: Color interpolations and more
---

# Colors

## `mixColor()`

Identical to `interpolateColor()` but with an animation value that goes from 0 to 1.

```typescript
const backgroundColor = useDerivedValue(() =>  
  mixColor(progress.value, "#ff3884", "#38ffb3")
);
```

## `colorForBackground()`

Returns black or white depending on the value of the background color.
